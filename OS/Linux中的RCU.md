## Linux中的RCU原理

1. RCU（Read-Copy Update）
   + 数据同步的一种方式
   + RCU适用于需要频繁的**读**取数据，而相应**写**数据并不多的情景
   + 例如在文件系统中：经常需要查找定位目录，而对目录的修改相对来说并不多
2. RCU实现**链表**中数据的读取
   + 目的：提高链表遍历**读取数据**的效率；
   + 方法：在读取数据时，不加锁，内存屏障，原子指令类开销，几乎是直接读;
3. RCU实现**链表**中数据的写操作
   + **允许一个线程对链表进行修改（修改的时候，需要加锁）**

### RCU实现过程中，需要解决的问题

1. 在读取过程中，另外一个线程**删除**了一个节点
   + 删除线程可以把这个节点从链表中移除，但它不能直接销毁这个节点;
   + 必须等到**所有的读取线程**读取完成以后，才进行销毁操作。
   + RCU中把这个过程称为宽限期（Grace period）。
2. 在读取过程中，另外一个线程**插入**了一个新节点
   + 而读线程读到了这个节点，那么需要**保证**读到的这个节点是**完整**的。
   + 这里涉及到了发布-订阅机制（Publish-Subscribe Mechanism）
3. 保证读取链表的**完整性**
   + 新增或者删除一个节点，不至于导致遍历一个链表从中间断开。
   + 但是RCU并**不保证**一定能读到新增的节点或者不读到要被删除的节点。
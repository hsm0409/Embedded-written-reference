# Embedded-written-reference
+ 2019-参加过的嵌入式笔试题目和解析分享
+ 电话邀约面试的时候（千万不要像第一次接到电话）：
  + 是可以和面试官商量时间的：竟可能将时间往后推，方便对复习有利；
  + 除了地点、时间、采用何种方式面试；侧面询问面试考察的方面，以及面试的流程。

Table of Contents
=================

   * [Embedded-written-reference](#embedded-written-reference)
      * [Content](#content)
   * [Table of Contents](#table-of-contents)
      * [ARM体系结构](#arm体系结构)
      * [Operation System](#operation-system)
         * [进程和线程](#进程和线程)
         * [OS Interrupt](#os-interrupt)
      * [Memory Management](#memory-management)
         * [用户空间与内核空间](#用户空间与内核空间)
         * [Cache 缓存一致性](#cache-缓存一致性)
         * [内存分配](#内存分配)
      * [Linux Kernel](#linux-kernel)
         * [linux kernel  start](#linux-kernel--start)
         * [Linux Kernel](#linux-kernel-1)
         * [shell](#shell)
      * [Linux 驱动开发](#linux-驱动开发)
         * [硬件相关知识](#硬件相关知识)
         * [linux 驱动模型](#linux-驱动模型)
      * [嵌入式和C的基础知识](#嵌入式和c的基础知识)
         * [嵌入式](#嵌入式)
         * [基础知识](#基础知识)
      * [C  ](#c)
      * [设计模式](#设计模式)
      * [网络](#网络)
      * [数据结构](#数据结构)
      * [机器学习](#机器学习)

## ARM体系结构

1. [ARM 体系结构的介绍?](https://luckywater.top/2019/08/02/ARM体系结构/)
2. [ARM体系结构下的MMU如何实现映射？](/OS/ARM体系结构下的MMU如何实现映射.md)
   + ARM通过几级页表实现存储空间映射？
3. [四大CPU体系结构:ARM、X86/Atom、MIPS、PowerPC](/OS/四大CPU体系结构.md)
   + MIPS 体系结构cpu地址空间划分
7. [OS无锁可以提高整个程序的性能，但是CPU需要对此提供支持，请以x86/ARM为例简述](/8.1Dji大疆/cpu对锁的支持.md)

## Operation System

### 进程和线程

3. [Linux 多任务, 进程, 线程，协程之间的关系？进程和程序的区别？](/8.1Dji大疆/Linux多任务进程线程之间的关系.md)
4. [Linux查询进程和线程数量?](/8.1Dji大疆/Linux查询进程和线程数量.md)
5. [Linux产生僵尸进程的原因？](https://luckywater.top/2019/04/22/system-process/)
4. [OS 进程间通信的7种方式？通信为何需要内核？](https://luckywater.top/2019/08/02/进程间通信的几种方式/)
5. [OS 如何实现进程间上下文切换的机制?](/8.1Dji大疆/OS如何实现进程间的切换.md)
6. [OS进程调度的算法？](/process/Linux进程调度的算法.md)
7. [OS **内核进程调度**函数schedule()的触发和执行时机？](/process/schedule()的触发和执行时机.md)

### OS Interrupt 

1. [ISR的定义？中断ISR处理过程的描述?](/8.1Dji大疆/OS中断处理过程的描述.md)
2. [Linux中断分层和中断嵌套的概念？软中断实现的机制？](/OS/Linux中断分层的概念.md)
3. [Linux中断信号源软中断, 软件中断 和硬件中断的区别？](/OS/Linux中断之间区别.md)
   + 软中断和函数调用区别？
4. [Linux进程上下文切换 VS 中断上下文切换？](/OS/Linux进程上下文切换和中断上下文切换.md)
   + 缺页中断和中断的区别？

OS同步和异步

1. [概念 -- 并发和竞态？阻塞和非阻塞I/O？同步和异步I/O？](/OS/几组概念.md)
   - I/O的五中模型？AIO的实现机制？
2. [OS中实现原子的操作？多种锁的区别？自旋锁和互斥锁？](/OS/OS信号量互斥体自旋锁的概念.md)
3. [RCU(读-复制-更新)的原理？](/OS/Linux中的RCU.md)
4. [linux**内核**中的 自旋锁 和 内核信号量？内核信号量和用户空间信号量？](/OS/linux内核中的锁和同步机制.md)
5. [OS 同步和互斥四种方法？临界区/互斥量/信号量/事 件？管程()？](/OS/OS同步机制的实现.md)
6. [Online Judge:  实现通过循环队列实现循环缓冲区.](https://github.com/quronghui/DataStructAndAlogrithmCode/blob/master/CompanyWrite/1_Dji/circularReadWrite.c)、

## Memory Management

### 用户空间与内核空间

1. [OS **用户模式与内核模式**定义，切换，通信?](https://luckywater.top/2019/08/02/linux用户和内核/)

   - 内核空间的划分？高端内存定义？

   + [系统调用的具体过程？read系统调用的过程？](/OS/linux中系统调用过程.md)

   + [Linux系统调用函数：copy_from_user的实现原理？和memcpy区别？内核中传递大量数据的方法？](/OS/Linux系统调用函数copy_from_user.md)

2. [linux 根据逻辑地址空间，计算页，页表，页表项？](/OS/linux计算页表项大小.md)

3. [linux **用户空间**内存分配? 底层mmap内存分配原理? ](/OS/linux内存管理.md)

4. [linux**内核空间**中内存分配？linux 多级分页目录结构？](/OS/linux内核中多级分页目录结构.md)

   + DMA的原理

5. [CPU , Cache，MMU ，内存之间的关系？](/OS/Linux内核和用户程序运行在物理地址还是虚拟地址.md)

### Cache 缓存一致性

1. [OS cache缓存一致性描述?](/8.1Dji大疆/OScache缓存一致性描述.md)
2. [OS cache(页面)多任务调度描述?](/8.1Dji大疆/OScache多任务调度描述.md)
3. [cache 缓存的意义？缺页中断的概念？](/OS/cache的解析.md)
4. [OS内存泄漏的理解](/OS/内存泄漏的理解.md)

### 内存分配

1. [C程序在运行的内存分配？五个段占用的空间大小？]( /8.1Dji大疆/OS简述一个执行程序在运行时的内存布局.md)
2. [C函数strcpy，memcpy，sprintf,  memset区别和具体实现](/8.1Dji大疆/C函数使用注意.md)
3. [OS**内存字节对齐** pragma pack()用法详解?](https://luckywater.top/2019/08/02/PragmaPack/)
   + 32位/64位的系统中, 各自的sizeof()是多少?
4. [OS大端和小端存储问题？OS如何判断并进行转化？](/8.1Dji大疆/大端小端存储问题.md)
5. 
6. [OS 嵌入式系统中共享资源的访问限制？]( /8.1Dji大疆/OS简述线程之间的同步互斥时占用空间的大小.md)

## Linux Kernel

### linux kernel  start

1. [U-boot 和 Bootloader引导内核的启动](/OS/Bootloader.md) 
2. [ARM结构下，Uboot如何给kernel传参数](/OS/Uboot如何给kernel传参数.md)
3. [Linux内核启动流程?](/OS/Linux内核启动流程.md)
4. [linux中netfilter的实现机制？是如何实现对特定数据包进行处理(如过滤，NAT之类的)及HOOK点的注册？](/OS/linux中netfilter的实现机制.md)
5. [ Linux抽象出framebuffer这个设备的作用？](/OS/Linux抽象出framebuffer这个设备的作用.md)
6. [linux两种错误：kernel panic 和 Oops段错误信息?](/OS/Oops.md)

### Linux Kernel

1. [linux 7种文件类型？](/OS/linux7种文件类型.md) 
2. [linux**文件系统的目录结构**，选项是/usr、/tmp、/etc目录的作用?](/8.1Dji大疆/linux目录结构.md)
3. [Linux的具体的命令, 文件和目录的5个操作命令?](/shell/linux文件操作的五个命令.md)
4. [Linux虚拟文件系统VFS的关键数据结构有哪些？VFS支持多文件系统互通？](/OS/Linux虚拟文件系统的关键数据结构有哪些.md)
5. [Linux 内核中常用的两个宏定义？offset 和 typeof？](/8.1Dji大疆/linux内核中常用的两个宏定义.md)
6. [Linux内核的五个子系统？](/OS/Linux内核的五个模块描述.md)

### shell

1. [linux内核版本号，编译器gcc版本号](/shell/linux内核版本号.md)
2. [echo 重定义 和 grep 正则表达式匹配？](/8.3网易/echo重定义和grep正则表达式匹配.md)
   - [grep匹配邮件地址](https://luckywater.top/2019/04/25/Regular-Expression/)
3. [Linux 文件和目录的权限？umask与文件目录的权限关系？](/8.3网易/LInux系统权限.md)
4. [Linux读取某个文件的某一行或者某几行, 使用sed](/shell/Linux读取某个文件的某一行或者某几行.md)
5. [Linux 磁盘整体情况](/shell/Linux磁盘整体情况.md)
6. [Makefile文件的编写?](/shell/Makefile.md)
7. [linux内核裁剪的方式?](/7.30诺瓦科技/linux内核裁剪的方式.md)
8. [tar解压一个压缩包，并将原先文件里面的内容覆盖？]
9. [find 命令的详解？在指点时间内查找修改过的文件？]
10. [Linux下定时执行脚本？]

## Linux 驱动开发

### 硬件相关知识

1. [嵌入式总线的详解（IIC, SPI, UART, USB, PCI , DMA）](https://luckywater.top/2019/07/29/SerialBus/)
4. [万用表, 示波器采集数据的要求?](7.30诺瓦科技/示波器采集数据的要求.md)
3. [JTag用途？](/OS/JTag用途.md)
4. [英文翻译: 关于时钟发生器的英文翻译?](/7.30诺瓦科技/关于时钟发生器的英文翻译.md)
5. [驱动开发参考](https://www.jianshu.com/p/716ed9cdb8f3)

### linux 驱动模型

1. [Linux总线驱动模型platform？](OS/Linux驱动模型platform.md)

2. [Linux字符驱动和块驱动模型？注册设备的入口函数？](/OS/Linux字符驱动和块驱动模型.md)

4. [驱动中的一些命令? insomd和rmmod注意情况](/OS/驱动中的一些查看命令.md)

5. [主设备号和次设备号的用途？字符设备的注册方法？](/OS/主设备号和次设备号的用途.md)

7. [文件操作中控制函数：ioctl和unlock_ioctl的区别](/OS/ioctl和unlock_ioctl的区别.md)

8. [linux 下的声卡驱动alsa框架](https://luckywater.top/2019/09/04/LinuxALSA/)

9. [linux 下的camera驱动V4L2框架](https://luckywater.top/2019/09/04/linux-camera-driver/)

10. [蓝牙的协议GATT](https://luckywater.top/2019/09/05/BLE/#more)

## 嵌入式和C的基础知识

### 嵌入式

1. [实时操作系统和非实时操作系统特点和区别?](/8.1Dji大疆/OS实时和非实时性.md)
3. [OS多任务嵌入式系统中，bit 运算](/8.1Dji大疆/OS嵌入式系统指定位反转.md)
4. [地址访问----嵌入式系统中，访问固定的内存地址?](/OS/访问固定的内存位置.md)
4. [地址的跳转 ---- C 通过函数指针，实现程序跳转到绝对地址0x100000处执行？](/C/C实现函数跳转到绝对地址0x100000处执行.md)
5. [单片机应用程序存放的位置？单片机应用程序的三种架构？](/C/单片机应用程序架构.md)
6. [IGBT是什么控制性原件？](/C/IGBT是什么控制性原件.md)
7. [看门狗程序是为了溢出而设置的复位点，放在哪个位置？](/C/看门狗程序的应用.md)
8. [单片机中程序计数器PC是16bit，其寻址范围是多少？](/C/PC寻址范围.md)

### 基础知识

1. [预处理器标识#error的目的是什么](/C/error的目的是什么.md)
2. [C 程序**编译链接**的四个阶段？静态库和动态库的编译链接？](/8.1Dji大疆/C语言编译执行的四个阶段.md)
3. [C函数中参数传递，参数返回的过程？](/8.1Dji大疆/简述C函数中参数传递问题.md)
4. [C函数参数传递的三种方式：传值, 指针, 引用？为什么要使用指针？](/C/指针和引用的区别.md)
5. [C : 当char类型变量进行赋值时, 超过其范围时怎么处理?](https://github.com/quronghui/DataStructAndAlogrithmCode/blob/master/CompanyWrite/1_Dji/charConvertint.c)
6. [C: 有符号的变量(负数)和无符号的变量(正数)相加？原码, 反码, 补码的理解？](/8.1Dji大疆/C有符号的变量和无符号的变量相加.md)
7. [C: 中关键字的种类？什么阶段使用？各自的用途？](/8.1Dji大疆/C关键词的描述.md)
   1. [static关键字作用描述？](/C/C简述static关键字对于工程模块化的作用.md)
   2. [volatile关键字的作用？](/OS/嵌入式的volatile变量.md)
   3. [C 关键字宏define，typedef用法？](/8.24HIK/C宏使用.md)
8. [C中全局变量和局部变量可以重名吗？](/8.24HIK/C中全局变量和局部变量可以重名.md)
9. [C 不同变量的生命周期?](/C/C变量的生命周期.md)
10. [C中常量的表示和定义？](/C/C中常量的表示.md)
11. [指针？数组？函数？指针数组，数组指针？函数指针数组？指针函数，函数指针？](/C/用变量a给出下面的定义.md)
    + [sizeof 计算占用的空间数](/code/sizeof_value.c)
12. [C 运算符的优先级？单目和双目运算符区别？](/C/C运算符的优先级.md)
13. [Token划分，自加运算符++？C什么是左值，什么是右值？](/C/Token划分.md)
14. [如何理解标准输入输出函数：stdin  stdout  stderr](/shell/如何理解三个标准文件.md)
    + fprintf and sprintf
15. [如何写C嵌入式的死循环](/C/如何写C嵌入式的死循环/md)
16. [C: 如何实现一个数的四舍五入?](/C/C实现一个数的四舍五入.md)
17. [对于一个频繁使用的短小函数，c/c++用的什么？内联函数？](/C/C对于一个频繁使用的短小函数.md)
18. [行优先存储和列优先存储？]
19. [break用的地方？]
20. [四种方法跳出多层循环？]
21. [extern 作用的详解？]
22. [C中的逻辑类型和集合类型？]
23. [adc采样中的两个滤波器的作用？]
24. [解释DH协议的工作原理？]
25. [关于find的查找命令正确的是？]
26. [linux下有哪些通配符？]
27. [函数重载的问题？]
28. [线性表用数组表示，假定删除任意一个元素的概率相同，则删除一个元素平均需要移动元素的个数？]

## C++

1. [C++ std::string 的编码格式？]
2. [make_shared 的用法描述？]

## 设计模式

1. [常用的设计模式？](/design_model/常用的设计模式.md)
2. [抽象工厂模式的理解？]
3. [观察者模式和发布/订阅模式的区别？]

## 网络

1. [OSI七层模型的协议？TCP/IP五层模型的硬件设备？路由协议？](/TCP/OSI七层中的硬件设备.md)
2. [TCP与UDP的区别？TCP三次握手和四次挥手？TCP数据分包？](/TCP/tcp和udp的区别.md)
3. [UDP如何保证可靠传输？基于UDP实现TCP？](/TCP/基于UDP实现可靠传输.md)
4. [TCP/IP物理层的具体内容是啥?](7.30诺瓦科技/tcp物理层的具体内容.md)
5. [DNS服务器是如何工作的?](/TCP/DNS服务器是如何工作的.md)
6. [TCP，HTTP，HTTPS之间的区别和联系？https怎么保证安全的？讲讲数字签名的过程？](/TCP/http和TCP之间的关联.md)
7. [建立Socket连接过程？--基于TCP/UDP](/TCP/Socket建立连接过程.md)
8. [IGMP ：组播中的MAC地址？](/TCP/IGMP组播中的MAC地址.md)

## 数据结构

1. [sort -- 排序算法的介绍和时间复杂度](https://luckywater.top/2019/05/22/Sort-ways/)
2. [Dijkstra最短路径算法的描述正确的是?](/8.3网易/Dijkstra最短路径算法的描述.md)
3. [tree -- 树和二叉树的相关考题？二叉树的度？二叉树描述？](/8.3网易/二叉树节点和度.md)
4. [tree  -- B, B-, B+树的定义，特性，联系与区别（红黑树）](/dataStruct/树的联系与区别.md)
5. [list -- 为一个链表设置一个head和tail, 链表的操作哪一个和长度相关?](/8.24HIK/list相关操作.md)
   - list -- 哪一种数据结构, 只能顺序访问?
6. [Graph -- 图的表示和存储](/dataStruct/图的表示和存储.md)
7. [数据结构中堆、栈和队列的理区别?](/dataStruct/数据结构中堆、栈和队列的理区别.md)
8. [n个元素入栈后，出栈的方式有多少个？](/dataStruct/n个元素的出栈顺序.md)

## 机器学习

1. [神经网络中引入非线性能力的是？](/neuralNet/神经网络中引入非线性能力的是.md)
2. [CNN的介绍]


---
title: Android技术面试题（Android QA）
sidebar: auto
sidebarDepth: 3
---

# Android技术面试题（Android QA）

::: tip 提示

Java/Android面试题目积累，题目来自互联网。

答案仅是个人见解，如有错误欢迎斧正。

:::

[TOC]



## :file_folder:Android 适配

###  :question: **Android 适配 - 版本适配** [#132](https://github.com/Sogrey/Android_QA/issues/132)
###  :question: **Android 适配 - UI适配** [#136](https://github.com/Sogrey/Android_QA/issues/136)
###  :question: **Android 性能优化** [##148](https://github.com/Sogrey/Android_QA/issues/148)


## :file_folder:Java基础

###  :question:一个".java"源文件中是否可以包括多个类（不是内部类）？有什么限制？[#21](https://github.com/Sogrey/Android_QA/issues/21)

> 可以。必须只有一个类名与文件名相同。

###  :question: GC是什么? 为什么要有GC [#22](https://github.com/Sogrey/Android_QA/issues/22)

> GC是垃圾收集的意思（Gabage Collection）,内存处理是编程人员容易出现问题的地方，
> 忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java提供的GC功能可以自动
> 监测对象是否超过作用域从而达到自动回收内存的目的，Java语言没有提供释放已分配内存
> 的显示操作方法。

###  :question: 垃圾回收器的基本原理是什么？垃圾回收器可以马上回收内存吗？有什么办法主动通知虚拟机进行垃圾回收 [#23](https://github.com/Sogrey/Android_QA/issues/23)

> 对于GC来说，当程序员创建对象时，GC就开始监控这个对象的地址、大小以及使用情况。通常，GC采用
> 有向图的方式记录和管理堆(heap)中的所有对象。通过这种方式确定哪些对象是"可达的"，哪些对象是"不可达的"。
> 当GC确定一些对象为"不可达"时，GC就有责任回收这些内存空间。可以。程序员可以手动执行System.gc()，
> 通知GC运行，但是Java语言规范并不保证GC一定会执行。

###  :question: 写出输出的结果.(考查运算符的优先级) [#24](https://github.com/Sogrey/Android_QA/issues/24)

``` java
class Demo{
	public static void main(String[] args){
		int x=0,y=1;
		if(++x==y-- & x++==1||--y==0)
			System.out.println("x="+x+",y="+y);//x = 2,y = 0;
		else
			System.out.println("y="+y+",x="+x);
	}
}
```

###  :question: 插入代码，实现n和m值的交换 [#25](https://github.com/Sogrey/Android_QA/issues/25)

``` java
int n = 5,m = 13;
//TODO 插入代码，实现n和m值的交换
System.out.println("n="+n+",m="+m);
```

###  :question: 如何手动实现整型数值60的二进制到十六进制的转换 [#26](https://github.com/Sogrey/Android_QA/issues/26)

###  :question: short s1 = 1; s1 = s1 + 1;有什么错? short s1 = 1; s1 += 1;有什么错 [#27](https://github.com/Sogrey/Android_QA/issues/27)

> short s1 = 1; s1 = s1 + 1; （s1+1运算结果是int型，需要强制转换类型）
> short s1 = 1; s1 += 1;（可以正确编译）

###  :question: Java有没有goto [#28](https://github.com/Sogrey/Android_QA/issues/28)

> java中的保留字，现在没有在java中使用

###  :question: 用最有效率的方法算出2乘以8等於几 [#29](https://github.com/Sogrey/Android_QA/issues/29)

> 2 << 3

###  :question: char型变量中能不能存贮一个中文汉字?为什么? [#30](https://github.com/Sogrey/Android_QA/issues/30)

> 是能够定义成为一个中文的，因为java中以unicode编码，一个char占16个字节，
> 所以放一个中文是没问题的

###  :question: float型float f=3.4是否正确? [#31](https://github.com/Sogrey/Android_QA/issues/31)

> 不正确。精度不准确,应该用强制类型转换，如下所示：float f=(float)3.4;

###  :question: String是最基本的数据类型吗 [#32](https://github.com/Sogrey/Android_QA/issues/32)

> 基本数据类型包括byte、int、char、long、float、double、boolean和short。
> java.lang.String类是final类型的，因此不可以继承这个类、不能修改这个类。为了提高效率节省空间，我们应该用StringBuffer类

###  :question: 数组a[n],用java代码将数组元素顺序颠倒 [#33](https://github.com/Sogrey/Android_QA/issues/33)

###  :question: 从键盘分别输入年、月、日，判断这一天是当年的第几天。[#34](https://github.com/Sogrey/Android_QA/issues/34)

###  :question: 输入两个正整数m和n，求其最大公约数和最小公倍数 [#35](https://github.com/Sogrey/Android_QA/issues/35)

###  :question: 3000米长的绳子，每天减一半。问多少天这个绳子会小于5米？不考虑小数。 [#36](https://github.com/Sogrey/Android_QA/issues/36)

###  :question: 编写程序，判断给定的某个年份是否是闰年。 [#37](https://github.com/Sogrey/Android_QA/issues/37)

###  :question: 利用程序输出如下图形: [#38](https://github.com/Sogrey/Android_QA/issues/38)

```
   *
   * * *
   * * * * *
   * * * * * * *
   * * * * *
   * * *
   *
```

###  :question: 一个数如果恰好等于它的因子之和，这个数就称为"完数"。（因子：除去这个数本身正的约数）[#39](https://github.com/Sogrey/Android_QA/issues/39)
例如6=1＋2＋3.编程 找出1000以内的所有完数

###  :question: 输出所有的水仙花数，所谓水仙花数是指一个3位数，其各个位上数字立方和等于其本身。[#40](https://github.com/Sogrey/Android_QA/issues/40)
例如： 153 = 1*1*1 + 3*3*3 + 5*5*5 

###  :question: 打印九九乘法表 [#41](https://github.com/Sogrey/Android_QA/issues/41)

###  :question: String s = new String("xyz");创建了几个String Object [#48](https://github.com/Sogrey/Android_QA/issues/48)

> 两个，一个字符对象，一个字符对象引用对象

###  :question: String与StringBuffer的区别。 [#49](https://github.com/Sogrey/Android_QA/issues/49)

> String的长度是不可变的，StringBuffer的长度是可变的。如果你对字符串中的内容经常进行操作，
> 特别是内容要修改时，那么使用StringBuffer，如果最后需要String，那么使用StringBuffer的toString()方法

###  :question: Collection 和 Collections的区别 [#50](https://github.com/Sogrey/Android_QA/issues/50)

> Collection是集合类的上级接口，继承与他的接口主要有Set 和List.
> Collections是针对集合类的一个帮助类，他提供一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作

### ❓ Integer与int的区别 [#122](<https://github.com/Sogrey/Android_QA/issues/122>)

###  :question: Set里的元素是不能重复的，那么用什么方法来区分重复与否呢? 是用==还是equals()? 它们有何区别 [#51](https://github.com/Sogrey/Android_QA/issues/51)

> Set里的元素是不能重复的，那么用iterator()方法来区分重复与否。equals()是判读两个Set是否相等
>     equals()和==方法决定引用值是否指向同一对象equals()在类中被覆盖，为的是当两个分离的对象的内容
>     和类型相配的话，返回真值

###  :question: 两个对象值相同(x.equals(y) == true)，但却可有不同的hash code，这句话对不对 [#52](https://github.com/Sogrey/Android_QA/issues/52)

> 不对，有相同的hash code

###  :question: 说出ArrayList,Vector, LinkedList的存储性能和特性 [#53](https://github.com/Sogrey/Android_QA/issues/53)

> ArrayList和Vector都是使用数组方式存储数据，此数组元素数大于实际存储的数据以便增加和
> 插入元素，它们都允许直接按序号索引元素，但是插入元素要涉及数组元素移动等内存操作，所以
> 索引数据快而插入数据慢，Vector由于使用了synchronized方法（线程安全），通常性能上较ArrayList
> 差，而LinkedList使用双向链表实现存储，按序号索引数据需要进行前向或后向遍历，但是插入数据时
> 只需要记录本项的前后项即可，所以插入速度较快。

###  :question:  HashMap和Hashtable的区别 [#54](https://github.com/Sogrey/Android_QA/issues/54)

> HashMap是Hashtable的轻量级实现（非线程安全的实现），他们都完成了Map接口，主要区别在于HashMap
> 允许空（null）键值（key）,由于非线程安全，效率上可能高于Hashtable。
>     HashMap允许将null作为一个entry的key或者value，而Hashtable不允许。
>     HashMap把Hashtable的contains方法去掉了，改成containsvalue和containsKey。因为contains方法容易让
> 人引起误解。 
>     Hashtable继承自Dictionary类，而HashMap是Java1.2引进的Map interface的一个实现。
>     最大的不同是，Hashtable的方法是Synchronize的，而HashMap不是，在多个线程访问Hashtable时，不需要
> 自己为它的方法实现同步，而HashMap 就必须为之提供外同步。 
>     Hashtable和HashMap采用的hash/rehash算法都大概一样，所以性能不会有很大的差异。

###  :question: ArrayList和Vector的区别,HashMap和Hashtable的区别 [#55](https://github.com/Sogrey/Android_QA/issues/55)

> 就ArrayList与Vector主要从二方面来说.
> 一.同步性:Vector是线程安全的，也就是说是同步的，而ArrayList是线程序不安全的，不是同步的
> 二.数据增长:当需要增长时,Vector默认增长为原来一培，而ArrayList却是原来的一半
> 就HashMap与HashTable主要从三方面来说。
> 一.历史原因:Hashtable是基于陈旧的Dictionary类的，HashMap是Java 1.2引进的Map接口的一个实现
> 二.同步性:Hashtable是线程安全的，也就是说是同步的，而HashMap是线程序不安全的，不是同步的
> 三.值：只有HashMap可以让你将空值作为一个表的条目的key或value

### :question: List、Map、Set三个接口，存取元素时，各有什么特点？[#126](<https://github.com/Sogrey/Android_QA/issues/126>)

###  :question: 哪个选项和show函数重载  [#56](https://github.com/Sogrey/Android_QA/issues/56)

``` java
class Demo{
    void show(int a,int b,float c){}
}

A.void show(int a,float c,int b){}

B,void show(int a,int b,float c){}

C.int show(int a,float c,int b){return a;}

D.int show(int a,float c){return a;}
```

###  :question: 面向对象的特点  [#57](https://github.com/Sogrey/Android_QA/issues/57)

> 面向对象有三大特点：封装、继承、多态。(如果要回答四个，可加上 抽象性 这一特点)
> - 1.继承：
>   继承是一种联结类的层次模型，并且允许和鼓励类的重用，它提供了一种明确表述共性的方法。对象的一个新类可以从现有的类中派生，这个过程称为类继承。新类继承了原始类的特性，新类称为原始类的派生类（子类），而原始类称为新类的基类（父类）。派生类可以从它的基类那里继承方法和实例变量，并且类可以修改或增加新的方法使之更适合特殊的需要。
> - 2.封装：
>   封装是把过程和数据包围起来，对数据的访问只能通过已定义的界面。面向对象计算始于这个基本概念，即现实世界可以被描绘成一系列完全自治、封装的对象，这些对象通过一个受保护的接口访问其他对象。
> - 3. 多态性：
>   多态性是指允许不同类的对象对同一消息作出响应。多态性包括参数化多态性和包含多态性。多态性语言具有灵活、抽象、行为共享、代码共享的优势，很好的解决了应用程序函数同名问题。
> - 4.抽象：
>   抽象就是忽略一个主题中与当前目标无关的那些方面，以便更充分地注意与当前目标有关的方面。抽象并不打算了解全部问题，而只是选择其中的一部分，暂时不用部分细节。抽象包括两个方面，一是过程抽象，二是数据抽象。

###  :question: 方法重载(overload)必须满足________。[#58](https://github.com/Sogrey/Android_QA/issues/58)

> A. 在不同class中定义的方法     B.在同一类型中定义的方法
> C. 方法名必须相同                     D.返回类型必须相同
> E. 参数一定不同                         F.参数可以相同

###  :question: 当一个对象被当作参数传递到一个方法后，此方法可改变这个对象的属性，并可返回变化后的结果，那么这里到底是值传递还是引用传递? [#59](https://github.com/Sogrey/Android_QA/issues/59)

> 是值传递。Java 编程语言只有值传递参数。当一个对象实例作为一个参数被传递到方法中时，参数的值就是对该对象的引用。对象的内容可以在被调用的方法中改变，但对象的引用是永远不会改变的

###  :question: java中有几种方法可以实现一个线程？用什么关键字修饰同步方法? stop()和suspend()方法为何不推荐使用？[#60](https://github.com/Sogrey/Android_QA/issues/60)

> 有两种实现方法，分别是继承Thread类与实现Runnable接口
> 用synchronized关键字修饰同步方法
> 反对使用stop()，是因为它不安全。它会解除由线程获取的所有锁定，而且如果对象处于一种不连贯状态，
> 那么其他线程能在那种状态下检查和修改它们。结果很难检查出真正的问题所在。suspend()方法容易发生死锁。
> 调用suspend()的时候，目标线程会停下来，但却仍然持有在这之前获得的锁定。此时，其他任何线程都不能访
> 问锁定的资源，除非被"挂起"的线程恢复运行。对任何线程来说，如果它们想恢复目标线程，同时又试图
> 使用任何一个锁定的资源，就会造成死锁。所以不应该使用suspend()，而应在自己的Thread类中置入一个标志，
> 指出线程应该活动还是挂起。若标志指出线程应该挂起，便用wait()命其进入等待状态。若标志指出线程应当
> 恢复，则用一个notify()重新启动线程。

###  :question: sleep() 和 wait() 有什么区别? [#61](https://github.com/Sogrey/Android_QA/issues/61)

> sleep是线程类（Thread）的方法，导致此线程暂停执行指定时间，给执行机会给其他线程，但是监控状态
> 依然保持，到时后会自动恢复。调用sleep不会释放对象锁。
> wait是Object类的方法，对此对象调用wait方法导致本线程放弃对象锁，进入等待此对象的等待锁定池，只有针对
> 此对象发出notify方法（或notifyAll）后本线程才进入对象锁定池准备获得对象锁进入运行状态。

###  :question: 同步和异步有何异同，在什么情况下分别使用他们？举例说明。[#62](https://github.com/Sogrey/Android_QA/issues/62)

> 如果数据将在线程间共享。例如正在写的数据以后可能被另一个线程读到，或者正在读的数据可能已经被另一个
> 线程写过了，那么这些数据就是共享数据，必须进行同步存取。
> 当应用程序在对象上调用了一个需要花费很长时间来执行的方法，并且不希望让程序等待方法的返回时，就应该使用
> 异步编程，在很多情况下采用异步途径往往更有效率。

###  :question: 启动一个线程是用run()还是start()? [#63](https://github.com/Sogrey/Android_QA/issues/63)

> 启动一个线程是调用start()方法，使线程所代表的虚拟处理机处于可运行状态，这意味着它可以由JVM调度
> 并执行。这并不意味着线程就会立即运行。run()方法可以产生必须退出的标志来停止一个线程。

###  :question: 当一个线程进入一个对象的一个synchronized方法后，其它线程是否可进入此对象的其它方法? [#64](https://github.com/Sogrey/Android_QA/issues/64)

> 不能，一个对象的一个synchronized方法只能由一个线程访问。

###  :question: 请说出你所知道的线程同步的方法。 [#65](https://github.com/Sogrey/Android_QA/issues/65)

> wait():使一个线程处于等待状态，并且释放所持有的对象的lock。
> sleep():使一个正在运行的线程处于睡眠状态，是一个静态方法，调用此方法要捕捉InterruptedException异常。
> notify():唤醒一个处于等待状态的线程，注意的是在调用此方法的时候，并不能确切的唤醒某一个等待状态的
> 线程，而是由JVM确定唤醒哪个线程，而且不是按优先级。
> Allnotity():唤醒所有处入等待状态的线程，注意并不是给所有唤醒线程一个对象的锁，而是让它们竞争。

###  :question: 多线程有几种实现方法,都是什么?同步有几种实现方法,都是什么?  [#66](https://github.com/Sogrey/Android_QA/issues/66)

> 多线程有两种实现方法，分别是继承Thread类与实现Runnable接口 
> 同步的实现方面有两种，分别是synchronized,wait与notify

###  :question: 线程的基本概念、线程的基本状态以及状态之间的关系 [#67](https://github.com/Sogrey/Android_QA/issues/67)

> 线程指在程序执行过程中，能够执行程序代码的一个执行单位，每个程序至少都有一个线程，也就是程序本身。
> Java中的线程有四种状态分别是：运行、就绪、挂起、结束

###  :question: 简述synchronized和java.util.concurrent.locks.Lock的异同 ？[#68](https://github.com/Sogrey/Android_QA/issues/68)

> 主要相同点：Lock能完成synchronized所实现的所有功能
> 主要不同点：Lock有比synchronized更精确的线程语义和更好的性能。synchronized会自动释放锁，而Lock一定要求程序员手工释放，并且必须在finally从句中释放。 

###  :question: 判断题 来一波 [#69](https://github.com/Sogrey/Android_QA/issues/69)

```
1.C 和 Java 都是多线程语言。（x） 
2.如果线程死亡，它便不能运行。（√）
3.在 Java 中，高优先级的可运行线程会抢占低优先级线程。（√） 
4.程序开发者必须创建一个线程去管理内存的分配。（x） 
5.一个线程在调用它的 start 方法，之前，该线程将一直处于出生期。（√） 
6.当调用一个正在进行线程的 stop()方法时，该线程便会进入休眠状态。（x） 
7.如果线程的 run 方法执行结束或抛出一个不能捕获的例外，线程便进入等待状态。（x） 
8.一个线程可以调用 yield 方法使其他线程有机会运行。（√） 
```

###  :question: 选择题  [#70](https://github.com/Sogrey/Android_QA/issues/70)

###  :question: Java为什么要引入线程机制，线程、程序、进程之间的关系是怎样的。[#71](https://github.com/Sogrey/Android_QA/issues/71)

> 线程可以彼此独立的执行，它是一种实现并发机制的有效手段，可以同时使用多个线程来完成不同的任务，
> 并且一般用户在使用多线程时并不考虑底层处理的细节。
> 程序是一段静态的代码，是软件执行的蓝本。进程是程序的一次动态执行过程，即是处于运行过程中的程序。
> 线程是比进程更小的程序执行单位，一个进程可以启动多个线程同时运行，不同线程之间可以共享相同的内
> 存区域和数据。多线程程序是运行时间后嗣可能出现在一个进程之内的、有一个以上线程同时运行的情况的程序。

###  :question: Runnable接口包括哪些抽象方法？Thread类有哪些主要域和方法？[#72](https://github.com/Sogrey/Android_QA/issues/72)

> Runnable接口中仅有run()抽象方法。
> Thread类主要域有：MAX_PRIORITY,MIN_PRIORITY,NORM_PRIORITY。
> 主要方法有start(),run(),sleep(),currentThread(),setPriority(),getPriority(),join()等。

###  :question: 创建线程有哪两种方式？试写出每种的具体的流程。比较两种创建方式的不同，哪个更优。[#73](https://github.com/Sogrey/Android_QA/issues/73)

###  :question: 利用多线程设计一个程序，同时输出 50 以内的奇数和偶数，以及当前运行的线程名。[#74](https://github.com/Sogrey/Android_QA/issues/74)

###  :question: 我比较两个String总是false，但是它们明明都是"abc" ！[#75](https://github.com/Sogrey/Android_QA/issues/75) 

> 比较String一定要使用equals或equalsIgnoreCase方法，不要使用 == ！ 
> 　　==比较的是两个引用（变量）是否指向了同一个对象，而不是比较其内容。

###  :question: int 和 Integer 有什么区别 [#77](https://github.com/Sogrey/Android_QA/issues/77)

> Java 提供两种不同的类型：引用类型和原始类型（或内置类型）。
> Int是java的原始数据类型，Integer是java为int提供的封装类。

###  :question: 重载（overload)和重写(overried，有的书也叫做“覆盖”）的区别？Overload的方法是否可以改变返回值的类型？[#78](https://github.com/Sogrey/Android_QA/issues/78)

> 方法的重写Overriding和重载Overloading是Java多态性的不同表现。重写Overriding是父类与子类之间多态性的一种表现，重载Overloading是一个类中多态性的一种表现。如果在子类中定义某方法与其父类有相同的名称和参数，我们说该方法被重写 (Overriding)。子类的对象使用这个方法时，将调用子类中的定义，对它而言，父类中的定义如同被"屏蔽"了。如果在一个类中定义了多个同名的方法，它们或有不同的参数个数或有不同的参数类型，则称为方法的重载(Overloading)。Overloaded的方法是可以改变返回值的类型

###  :question: abstract class 和interface 有什么区别? [#79](https://github.com/Sogrey/Android_QA/issues/79)

###  :question: abstract 的method 是否可同时是static，是否可同时是native，是否可同时是synchronized？[#80](https://github.com/Sogrey/Android_QA/issues/80)

> 都不能

###  :question: 是否可以从一个static方法内部发出对非static方法的调用？[#81](https://github.com/Sogrey/Android_QA/issues/81)

> 不可以,如果其中包含对象的method()；不能保证对象初始化.

###  :question: 接口是否可继承接口? 抽象类是否可实现(implements)接口? 抽象类是否可继承实体类(concrete class)? [#82](https://github.com/Sogrey/Android_QA/issues/82)

> 接口可以继承接口。抽象类可以实现(implements)接口，
> 抽象类可继承实体类，但实体类必须不能是如下两种情况之一：   
> 1，final修饰符修饰的类是不能的
> 2，如果此实体类有且仅有私有的构造函数也是不能的。

###  :question: Anonymous Inner Class (匿名内部类) 是否可以extends(继承)其它类，是否可以implements(实现)interface(接口) [#83](https://github.com/Sogrey/Android_QA/issues/83)

> 匿名的内部类是没有名字的内部类。不能extends(继承) 其它类，但一个内部类可以作为一个接口，由另一个内部类实现

###  :question: Static Nested Class 和 Inner Class的不同 [#84](https://github.com/Sogrey/Android_QA/issues/84)

> Nested Class （一般是C++的说法），Inner Class (一般是JAVA的说法)。
> Java内部类与C++嵌套类最大的不同就在于是否有指向外部的引用上。
> 注： 静态内部类（Inner Class）意味着
> 1创建一个static内部类的对象，不需要一个外部类对象，2不能从一个static内部类的一个对象访问一个外部类对象

###  :question: 谈谈final, finally, finalize的区别 [#85](https://github.com/Sogrey/Android_QA/issues/85)

> final—修饰符（关键字）如果一个类被声明为final，意味着它不能再派生出新的子类，不能作为父类被继承。
> 因此一个类不能既被声明为 abstract的，又被声明为final的。将变量或方法声明为final，可以保证它们在使用中不被改变。
> 被声明为final的变量必须在声明时给定初值，而在以后的引用中只能读取，不可修改。被声明为final的方法也同样只能使用，不能重载
> finally—再异常处理时提供 finally 块来执行任何清除操作。如果抛出一个异常，那么相匹配的 catch 子句就会执行，然后控制就会进入 finally 块（如果有的话）
> finalize—方法名。Java 技术允许使用 finalize() 方法在垃圾收集器将对象从内存中清除出去之前做必要的清理工作。
> 这个方法是由垃圾收集器在确定这个对象没有被引用时对这个对象调用的。它是在 Object 类中定义的，因此所有的类都继承了它。子类覆盖 finalize() 方法以整理系统资源或者执行其他清理工作。finalize() 方法是在垃圾收集器删除对象之前对这个对象调用的

### :question: Serializable和Parcelable的区别  [#116](https://github.com/Sogrey/Android_QA/issues/116)

> 1.P 消耗内存小
>
> 2.网络传输用S 程序内使用P
>
> 3.S将数据持久化方便
>
> 4.S使用了反射 容易触发垃圾回收 比较慢

###  :question: java中有几种类型的流？JDK为每种类型的流提供了一些抽象类以供继承，请说出他们分别是哪些类？[#86](https://github.com/Sogrey/Android_QA/issues/86)

> 字节流，字符流。
> 字节流继承于InputStream OutputStream，
> 字符流继承于Reader Writer。在java.io包中还有许多其他的流，主要是为了提高性能和使用方便。

###  :question: 什么是java序列化，如何实现java序列化？[#87](https://github.com/Sogrey/Android_QA/issues/87)

> 序列化就是一种用来处理对象流的机制，所谓对象流也就是将对象的内容进行流化。
> 可以对流化后的对象进行读写操作，也可将流化后的对象传输于网络之间。
> 序列化是为了解决在对对象流进行读写操作时所引发的问题。
> 序列化的实现：将需要被序列化的类实现Serializable接口，该接口没有需要实现的方法，implements Serializable只是为了标注该对象是可被序列化的，然后使用一个输出流(如：FileOutputStream)来构造一个ObjectOutputStream(对象流)对象，接着，使用ObjectOutputStream对象的writeObject(Object obj)方法就可以将参数为obj的对象写出(即保存其状态)，要恢复的话则用输入流。

###  :question: Java中有几种类型的流？JDK为每种类型的流提供了一些抽象类以供继承，请指出它们分别是哪些类？[#88](https://github.com/Sogrey/Android_QA/issues/88)

> Java中按所操作的数据单元的不同，分为字节流和字符流。
> 字节流继承于InputStream和OutputStream类，字符流继承于Reader和Writer。
> 按流的流向的不同，分为输入流和输出流。
> 按流的角色来分，可分为节点流和处理流。缓冲流、转换流、对象流和打印流等都属于处理流，使得输入/输出更简单，执行效率更高。

### ❓ 字节流与字符流的区别 [#127](<https://github.com/Sogrey/Android_QA/issues/127>)

###  :question: 描述一下JVM加载class文件的原理机制? [#89](https://github.com/Sogrey/Android_QA/issues/89)

> JVM中类的装载是由ClassLoader和它的子类来实现的,Java ClassLoader 
> 是一个重要的Java运行时系统组件。它负责在运行时查找和装入类文件的类。

###  :question: Java 的通信编程，编程题(或问答)，用JAVA SOCKET编程，读服务器几个字符，再写入本地显示？ [#90](https://github.com/Sogrey/Android_QA/issues/90)

###  :question: java线程的sleep(),wait(),notify(),yield()方法的区别？[#91](https://github.com/Sogrey/Android_QA/issues/91)

> - sleep()使线程休眠一段时间，一段时间结束后，线程进入可执行状态，但并不是立即执行，只是在被排程器调用的时候才执行。在休眠期间，并不释放所持有的“锁”；
> - wait()使线程休眠一段时间，若设置参数，时间到时，线程就自动进入可执行状态。若没有，则需要notify()方法去调用。注意：wait()方法和notify()方法都时针对this对象的，调用wait()方法后，会释放加在对象上的“锁”。
> - yield()使线程放弃执行的权利，进入可执行状态，也就意味着线程在yield()方法后，有可能又执行。使用yield()方法，线程并不释放自己锁持有的“锁”。

### ❓ 在JAVA中如何跳出当前的多重嵌套循环？[#121](<https://github.com/Sogrey/Android_QA/issues/121>)

### ❓ 静态变量和实例变量的区别？[#125](<https://github.com/Sogrey/Android_QA/issues/125>)

### ❓ heap和stack有什么区别。[#128](<https://github.com/Sogrey/Android_QA/issues/128>)

### ❓ 什么时候用assert。 [#129](<https://github.com/Sogrey/Android_QA/issues/129>)
### ❓ 如何控制某个方法允许并发访问线程的个数？ [#151](<https://github.com/Sogrey/Android_QA/issues/151>)
### ❓ List 如何一边遍历，一边删除？ [#152](<https://github.com/Sogrey/Android_QA/issues/152>)

## :file_folder: Android

###  :question: Android的四大组件是哪些，它们的作用？[#1](https://github.com/Sogrey/Android_QA/issues/1)

###  :question: 请介绍下Android中常用的五种布局。[#2](https://github.com/Sogrey/Android_QA/issues/2)

###  :question: android中的动画有哪几类，它们的特点和区别是什么 [#3](https://github.com/Sogrey/Android_QA/issues/3)

###  :question: android 中有哪几种解析xml的类？官方推荐哪种？以及它们的原理和区别。[#4](https://github.com/Sogrey/Android_QA/issues/4)

###  :question: ListView的优化方案 [#5](https://github.com/Sogrey/Android_QA/issues/5)

###  :question: 请介绍下Android的数据存储方式。[#6](https://github.com/Sogrey/Android_QA/issues/6)

###  :question: activity的启动模式有哪些？是什么含义？[#7](https://github.com/Sogrey/Android_QA/issues/7)

###  :question: 请描述一下Activity的生命周期 [#8](https://github.com/Sogrey/Android_QA/issues/8)

###  :question: 两个Activity之间跳转时必然会执行的是哪几个方法 [#9](https://github.com/Sogrey/Android_QA/issues/9)

###  :question: 横竖屏幕切换时候activity的生命周期 [#10](https://github.com/Sogrey/Android_QA/issues/10)

###  :question: 如何将一个activity设置为窗口的样式 [#11](https://github.com/Sogrey/Android_QA/issues/11)

### ❓ 理解Activity，View,Window三者关系 [#112](https://github.com/Sogrey/Android_QA/issues/112)

###  :question: 两个activity之间怎样传递数据 [#12](https://github.com/Sogrey/Android_QA/issues/12)

###  :question: **简单介绍下android的5大布局** [#109](<https://github.com/Sogrey/Android_QA/issues/109>)

###  :question: 怎么让viewpager不滑动？ [#147](<https://github.com/Sogrey/Android_QA/issues/147>)

###  :question: IntentService有何优点? [#16](https://github.com/Sogrey/Android_QA/issues/16)

###  :question: 如果后台的Activity由于某原因被系统回收了，如何在被系统回收之前保存当前状态？[#17](https://github.com/Sogrey/Android_QA/issues/17)

###  :question:  Activity怎么和service绑定，怎么在activity中启动自己对应的service？[#92](https://github.com/Sogrey/Android_QA/issues/92)

###  :question: 什么是Service以及描述下它的生命周期。Service有哪些启动方法，有什么区别，怎样停用Service？[#93](https://github.com/Sogrey/Android_QA/issues/93)

###  :question: 不用service，B页面为音乐播放，从A跳转到B，再返回，如何使音乐继续播放？[#94](https://github.com/Sogrey/Android_QA/issues/94)

###  :question: 什么是IntentService？有何优点？[#95](https://github.com/Sogrey/Android_QA/issues/95)

###  :question: 为什么要用ContentProvider？它和sql的实现上有什么差别？[#96](https://github.com/Sogrey/Android_QA/issues/96)

### ❓ invalidate和postInvalidate的区别及使用 [#123](<https://github.com/Sogrey/Android_QA/issues/123>)

###  :question: **android线程的好处** [#110](https://github.com/Sogrey/Android_QA/issues/110)

### :question:为什么在子线程无法更新 UI 操作？ [#138](https://github.com/Sogrey/Android_QA/issues/138)

### :question:Handler的原理 [#113](https://github.com/Sogrey/Android_QA/issues/113)

### :question: View，ViewGroup事件分发 [#114](https://github.com/Sogrey/Android_QA/issues/114)

### :question: 自定义控件View的绘制流程 [#115](https://github.com/Sogrey/Android_QA/issues/115)

###  :question: 简单描述下Android 数字签名。[#98](https://github.com/Sogrey/Android_QA/issues/98)

### :question: 说说mvc模式的原理，它在android中的运用,android的官方建议应用程序的开发采用mvc模式。何谓mvc？[#117](https://github.com/Sogrey/Android_QA/issues/117)

### ❓ AIDL的全称是什么？如何工作？能处理哪些类型的数据？[#118](https://github.com/Sogrey/Android_QA/issues/118)

### ❓ 系统上安装了多种浏览器，能否指定某浏览器访问指定页面？[#119](https://github.com/Sogrey/Android_QA/issues/119)

### ❓ 低版本SDK如何实现高版本api？[#124](https://github.com/Sogrey/Android_QA/issues/124)

###  :question: 谈谈Android的优点和不足之处。[#97](https://github.com/Sogrey/Android_QA/issues/97)

###  :question: **android系统的优势和不足** [#18](https://github.com/Sogrey/Android_QA/issues/18)

## :file_folder: 数据库

###  :question: 如何将SQLite数据库(dictionary.db文件)与apk文件一起发布 [#19](<https://github.com/Sogrey/Android_QA/issues/19>)

###  :question: 如何将打开res raw目录中的数据库文件? [#20](<https://github.com/Sogrey/Android_QA/issues/20>)

## :file_folder: 异常

###  :question: 什么是ANR 如何避免它？[#13](https://github.com/Sogrey/Android_QA/issues/13)

###  :question: 什么情况会导致Force Close ？如何避免？能否捕获导致其的异常？[#14](https://github.com/Sogrey/Android_QA/issues/14)

###  :question: **Android本身的api并未声明会抛出异常，则其在运行时有无可能抛出runtime异常，你遇到过吗？诺有的话会导致什么问题？如何解决？** [#15](https://github.com/Sogrey/Android_QA/issues/15)

###  :question: error和exception有什么区别 [#42](https://github.com/Sogrey/Android_QA/issues/42)

###  :question: 给我一个你最常见到的runtime exception [#43](https://github.com/Sogrey/Android_QA/issues/43)

###  :question: try {}里有一个return语句，那么紧跟在这个try后的finally {}里的code会不会被执行，什么时候被执行，在return前还是后 [#44](https://github.com/Sogrey/Android_QA/issues/44)

###  :question: 运行时异常与一般异常有何异同 [#45](https://github.com/Sogrey/Android_QA/issues/45)

###  :question: Java中的异常处理机制的简单原理和应用 [#46](https://github.com/Sogrey/Android_QA/issues/46)

###  :question: JAVA语言如何进行异常处理，关键字：throws,throw,try,catch,finally分别代表什么意义？在try块中可以抛出异常吗？ [#47](https://github.com/Sogrey/Android_QA/issues/47)

### :question: 导致内存泄露的原因有哪些？ [#111](<https://github.com/Sogrey/Android_QA/issues/111>)

### :question: 造成内存泄露原因有什么？ [#146](<https://github.com/Sogrey/Android_QA/issues/146>)
### ❓ 你在开发中碰到过 ClassNotFoundException 和 NoClassDefFoundError 吗？它们有什么区别？[#150](<https://github.com/Sogrey/Android_QA/issues/150>)

## :file_folder: Android与JS交互

### :question: Android与js是如何交互的？ [#149](<https://github.com/Sogrey/Android_QA/issues/149>)


## :file_folder: 算法与编程

###  :question: 编写一个程序，将a.txt文件中的单词与b.txt文件中的单词交替合并到c.txt文件中，a.txt文件中的单词用回车符分隔，b.txt文件中用回车或空格进行分隔。[#99](https://github.com/Sogrey/Android_QA/issues/99)

###  :question: 编写一个程序，将d:\java目录下的所有.java文件复制到d:\jad目录下，并将原来文件的扩展名从.java改为.jad。[#100](https://github.com/Sogrey/Android_QA/issues/100)

###  :question: 编写一个截取字符串的函数，输入为一个字符串和字节数，输出为按字节截取的字符串，但要保证汉字不被截取半个，如“我ABC”，4，应该截取“我AB”，输入“我ABC汉DEF”，6，应该输出“我ABC”，而不是“我ABC+汉的半个”。[#101](https://github.com/Sogrey/Android_QA/issues/101)

###  :question: 有一个字符串，其中包含中文字符、英文字符和数字字符，请统计和打印出各个字符的个数。[#102](https://github.com/Sogrey/Android_QA/issues/102)

###  :question: 从类似如下的文本文件中读取出所有的姓名，并打印出重复的姓名和重复的次数，并按重复次数排序 [#103](https://github.com/Sogrey/Android_QA/issues/103)

###  :question: 写一个Singleton出来。[#104](https://github.com/Sogrey/Android_QA/issues/104)

###  :question: 一个整数，大于0，不用循环和本地变量，按照n，2n，4n，8n的顺序递增，当值大于5000时，把值按照指定顺序输出来。[#105](https://github.com/Sogrey/Android_QA/issues/105)

###  :question: 第1个人10，第2个比第1个人大2岁，依次递推，请用递归方式计算出第8个人多大？[#106](https://github.com/Sogrey/Android_QA/issues/106)

###  :question: 排序都有哪几种方法？请列举。用JAVA实现一个快速排序。 [#107](https://github.com/Sogrey/Android_QA/issues/107)

###  :question: 金额转换，阿拉伯数字的金额转换成中国传统的形式如：（￥1011）－>（一千零一拾一元整）输出。[#108](https://github.com/Sogrey/Android_QA/issues/108)

### :question: 有一个一维整型数组int[] data保存的是一张宽为width,高为height的图片像素值信息。请写一个算法，将该图片所有的白色不透明(0xffffffff)像素点的透明度调整为50%。[#120](https://github.com/Sogrey/Android_QA/issues/120)

### :question: ​有数组a[n]，用java代码将数组元素顺序颠倒 [#130](<https://github.com/Sogrey/Android_QA/issues/130>)

## :file_folder: Kotlin相关

### :question: 什么是Kotlin？ [#140](<https://github.com/Sogrey/Android_QA/issues/140>)

### :question: Kotlin支持哪种类型的编程？ [#141](<https://github.com/Sogrey/Android_QA/issues/141>)

### :question: Kotlin有哪些不同类型的构造函数？ [#142](<https://github.com/Sogrey/Android_QA/issues/142>)

### :question: Kotlin的结构表达有哪些？  [#143](<https://github.com/Sogrey/Android_QA/issues/143>)
### :question: 请简述Val和Var之间的区别？   [#144](<https://github.com/Sogrey/Android_QA/issues/144>)



---

## :file_folder: 其他面经库

- [Java基础知识面试题（2020最新版）](https://blog.csdn.net/ThinkWon/article/details/104390612?utm_source=sogrey.top)

- **Mr-YangCheng/ForAndroidInterview**
<div class="github-widget" data-repo="Mr-YangCheng/ForAndroidInterview"></div>

- **Shouheng88/Android-notes**
<div class="github-widget" data-repo="Shouheng88/Android-notes"></div>

- **whatshappen/Android_Question**
<div class="github-widget" data-repo="whatshappen/Android_Question"></div>

- **derekargueta/Android-Interview-Questions**
<div class="github-widget" data-repo="derekargueta/Android-Interview-Questions"></div>

- **JackyAndroid/AndroidInterview-Q-A**
<div class="github-widget" data-repo="JackyAndroid/AndroidInterview-Q-A"></div>

- **stormzhang/android-interview-questions-cn**
<div class="github-widget" data-repo="stormzhang/android-interview-questions-cn"></div>

- **Advanced-Frontend/Daily-Interview-Question**
<div class="github-widget" data-repo="Advanced-Frontend/Daily-Interview-Question"></div>

- **sucese/android-interview-guide**
<div class="github-widget" data-repo="sucese/android-interview-guide"></div>

- **feelschaotic/AndroidKnowledgeSystem** 你想要的最全 Android 进阶路线知识图谱+干货资料收集
<div class="github-widget" data-repo="feelschaotic/AndroidKnowledgeSystem"></div>

<div><script type="text/javascript" src="https://git.hust.cc/GitHub-Repo-Widget.js/GithubRepoWidget.js"></script></div>

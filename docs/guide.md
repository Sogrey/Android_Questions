---
title: Android技术面试题（Android QA）
sidebar: auto
sidebarDepth: 3
---

# Android技术面试题（Android QA）

::: tip 提示

Android面试题目积累，题目来自互联网。

答案仅是个人见解，如有错误欢迎斧正。

:::

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

###  :question: 数组a[n]，用java代码将数组元素顺序颠倒 [#33](https://github.com/Sogrey/Android_QA/issues/33)

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

## :file_folder: Android

###  :question: Android的四大组件是哪些，它们的作用？[#1](https://github.com/Sogrey/Android_QA/issues/1)

> - Activity：Activity是Android程序与用户交互的窗口，是Android构造块中最基本的一种，它需要为保持各界面的状态，做很多持久化的事情，妥善管理生命周期以及一些跳转逻辑
> - service：后台服务于Activity，封装有一个完整的功能逻辑实现，接受上层指令，完成相关的事物，定义好需要接受的Intent提供同步和异步的接口
> - Content Provider：是Android提供的第三方应用数据的访问方案，可以派生Content Provider类，对外提供数据，可以像数据库一样进行选择排序，屏蔽内部数据的存储细节，向外提供统一的借口模型，大大简化上层应用，对数据的整合提供了更方便的途径
> - BroadCast Receiver：接受一种或者多种Intent作触发事件，接受相关消息，做一些简单处理，转换成一条Notification，统一了Android的事件广播模型

###  :question: 请介绍下Android中常用的五种布局。[#2](https://github.com/Sogrey/Android_QA/issues/2)

> 常用五种布局方式，分别是：FrameLayout（框架布局），LinearLayout （线性布局），AbsoluteLayout（绝对布局），RelativeLayout（相对布局），TableLayout（表格布局）。
>
> - FrameLayout：所有东西依次都放在左上角，会重叠，这个布局比较简单，也只能放一点比较简单的东西。
> - LinearLayout：线性布局，每一个LinearLayout里面又可分为垂直布局（android:orientation="vertical"）和水平布局（android:orientation="horizontal" ）。当垂直布局时，每一行就只有一个元素，多个元素依次垂直往下；水平布局时，只有一行，每一个元素依次向右排列。
> - AbsoluteLayout：绝对布局用X,Y坐标来指定元素的位置，这种布局方式也比较简单，但是在屏幕旋转时，往往会出问题，而且多个元素的时候，计算比较麻烦。
> - RelativeLayout：相对布局可以理解为某一个元素为参照物，来定位的布局方式。主要属性有：相对于某一个元素android:layout_below、      android:layout_toLeftOf相对于父元素的地方android:layout_alignParentLeft、android:layout_alignParentRigh；
> - TableLayout：表格布局，每一个TableLayout里面有表格行TableRow，TableRow里面可以具体定义每一个元素。每一个布局都有自己适合的方式，这五个布局元素可以相互嵌套应用，做出美观的界面。

###  :question: android中的动画有哪几类，它们的特点和区别是什么 [#3](https://github.com/Sogrey/Android_QA/issues/3)

> 两种，一种是Tween动画、还有一种是Frame动画。
>
> - Tween动画，这种实现方式可以使视图组件移动、放大、缩小以及产生透明度的变化;
> - Frame动画，传统的动画方法，通过顺序的播放排列好的图片来实现，类似电影。

###  :question: android 中有哪几种解析xml的类？官方推荐哪种？以及它们的原理和区别。[#4](https://github.com/Sogrey/Android_QA/issues/4)

> XML解析主要有三种方式，SAX、DOM、PULL。
>
> 常规在PC上开发我们使用Dom相对轻松些，但一些性能敏感的数据库或手机上还是主要采用SAX方式，SAX读取是单向的，优点:不占内存空间、解析属性方便，但缺点就是对于套嵌多个分支来说处理不是很方便。而DOM方式会把整个XML文件加载到内存中去，这里Android开发网提醒大家该方法在查找方面可以和XPath很好的结合如果数据量不是很大推荐使用，而PULL常常用在J2ME对于节点处理比较好，类似SAX方式，同样很节省内存，在J2ME中我们经常使用的KXML库来解析。

###  :question: ListView的优化方案 [#5](https://github.com/Sogrey/Android_QA/issues/5)

>  1、如果自定义适配器，那么在getView方法中要考虑方法传进来的参数contentView是否为null，如果为null就创建contentView并返回，如果不为null则直接使用。在这个方法中尽可能少创建view。
>
>   2、给contentView设置tag（setTag（）），传入一个viewHolder对象，用于缓存要显示的数据，可以达到图像数据异步加载的效果。
>
>   3、如果listview需要显示的item很多，就要考虑分页加载。比如一共要显示100条或者更多的时候，我们可以考虑先加载20条，等用户拉到列表底部的时候再去加载接下来的20条。

###  :question: 请介绍下Android的数据存储方式。[#6](https://github.com/Sogrey/Android_QA/issues/6)

> 使用SharedPreferences存储数据；文件存储数据；SQLite数据库存储数据；使用ContentProvider存储数据；网络存储数据；

###  :question: activity的启动模式有哪些？是什么含义？[#7](https://github.com/Sogrey/Android_QA/issues/7)

> 在android里，有4种activity的启动模式，分别为：
>
> - “standard” (默认)
>
> - “singleTop”
>
> - “singleTask”
>
> - “singleInstance”
>
> 具体区别见 [#7](https://github.com/Sogrey/Android_QA/issues/7)

###  :question: 请描述一下Activity的生命周期 [#8](https://github.com/Sogrey/Android_QA/issues/8)

> - onCreate(Bundle savedInstanceState)：创建Activity时调用，设置在该方法中，还以Bundle的形式提供对以前存储的任何状态的访问。
> - onStart（）：activity变为在屏幕上对用户可见时调用
> - onResume（）：activity开始与用户交互时调用（无论是启动还是重新启动一个activity，该方法总是被调用）
> - onPause（）：activity被暂停或者收回cpu和其他资源时调用，该方法用于保存活动状态的，也是保护现场，压栈吧
> - onStop（）：activity被停止并转为不可见阶段及后续的生命周期事件时调用。
> - onRestart（）：重新启动activity时调用，该活动仍在栈中，而不是启动新的activity
> - onDestroy（）：activity被完全从系统内存中移除时调用  

###  :question: 两个Activity之间跳转时必然会执行的是哪几个方法 [#9](https://github.com/Sogrey/Android_QA/issues/9)

> - onCreate（）：在activity生命周期开始时调用
> - onRestoreInstanceState（）：用来恢复UI状态
> - onRestart（）：当activity重新启动时调用
> - onStart（）：当activity对用户即将可见时调用
> - onResume（）：当activity与用户交互时，绘制界面
> - onSaveInstanceState（）：当activity即将移除栈顶保留UI状态时被调用
> - onPause（）：暂停当前活动的activity，提交持久数据的改变，停止动画和其他占用CPu资源的东西，由于下一个activity在这个方法返回之前不会resume，所以这个方法的代码执行要快
> - onStop（）：activity不再可见时调用
> - onDestroy（）：在activity销毁栈时被调用的最后一个方法  

###  :question: 横竖屏幕切换时候activity的生命周期 [#10](https://github.com/Sogrey/Android_QA/issues/10)

> ①不设置activity的android:configChanges时，切屏会重新调用各个生命周期，切横屏时会执行一次，且竖屏时会执行两次
>
> ②设置activity的android:configChanges=”orientation"时，切屏还是会调用各个生命周期，切横屏，竖屏时只会执行一次
>
> ③设置activity的android:configChanges="orientation|keyboardHidden"时，切屏不会重新调用各个生命周期，只会执行onConfigurationChanged方法

###  :question: 如何将一个activity设置为窗口的样式 [#11](https://github.com/Sogrey/Android_QA/issues/11)

> ①在你的style.xml文件中可以新建一如下的类似Dialog的style：
>
> ``` xml
> <style name="Theme.FloatActivity" parent="android:style/Theme.Dialog></style>
> ```
>
> ②在AndroidManifest.xml中在你需要显示为窗口的activity中添加如下属性：
>
> ``` xml
> android:theme="@style/Theme.FloatActivity"
> ```
>
> 也可以直接添加对应需要展示为Dialog style的activity的android:theme属性值为：
>
> ```
> android:theme="@android:style/Theme.Dialog"  
> ```

### ❓ 理解Activity，View,Window三者关系 [#112](https://github.com/Sogrey/Android_QA/issues/112)

###  :question: 两个activity之间怎样传递数据 [#12](https://github.com/Sogrey/Android_QA/issues/12)

>   在Intent的对象中增加要传递的参数即可
>
>   在Intent对象的请求中加入键值对，对应名字`.putExtra`（“键值对的名字","键值对的值");在另一个activity中将Intent的请求中的数据取出来：
>
>   ``` java
>   Intent intent= getIntent（）；
>   String value = intent.getStringExtra("testIntent") ;
>   ```

###  :question: **简单介绍下android的5大布局** [#109](<https://github.com/Sogrey/Android_QA/issues/109>)

> 覆盖线性布局（LinearLayout）：按照垂直或者水平方向布局的组件。
>
> 帧布局（FrameLayout）：组件从屏幕左上方布局组件。
>
> 表格布局（TableLayout）：按照行列方式布局组件。
>
> 相对布局（RelativeLayout）：相对其它组件的布局方式。
>
>  绝对布局（AbsoluteLayout）：按照绝对坐标来布局组件。

###  :question: IntentService有何优点? [#16](https://github.com/Sogrey/Android_QA/issues/16)

> Acitivity的进程，当处理Intent的时候，会产生一个对应的Service； Android的进程处理器现在会尽可能的不kill掉你；非常容易使用

###  :question: 如果后台的Activity由于某原因被系统回收了，如何在被系统回收之前保存当前状态？[#17](https://github.com/Sogrey/Android_QA/issues/17)

> 重写onSaveInstanceState()方法，在此方法中保存需要保存的数据，该方法将会在activity被回收之前调用。通过重写onRestoreInstanceState()方法可以从中提取保存好的数据

###  :question:  Activity怎么和service绑定，怎么在activity中启动自己对应的service？[#92](https://github.com/Sogrey/Android_QA/issues/92)

> startService() 一旦被创建  调用者无关   没法使用service里面的方法 
>
> bindService () 把service 与调用者绑定 ,如果调用者被销毁, service会销毁
>
> bindService() 我们可以使用service 里面的方法
>
> bindService().  让activity能够访问到 service里面的方法构建一个intent对象,
>
> Intent service = new Intent(this,MyService.class);
>
>  通过bindService的方法去启动一个服务,
>
>  bindService(intent, new MyConn(), BIND_AUTO_CREATE);
>
> ServiceConnection 对象(重写onServiceConnected和OnServiceDisconnected方法) 和BIND_AUTO_CREATE.

###  :question: 什么是Service以及描述下它的生命周期。Service有哪些启动方法，有什么区别，怎样停用Service？[#93](https://github.com/Sogrey/Android_QA/issues/93)

###  :question: 不用service，B页面为音乐播放，从A跳转到B，再返回，如何使音乐继续播放？[#94](https://github.com/Sogrey/Android_QA/issues/94)

> 遇到问题, 可以随机应变,灵活发挥,多考虑些细节,比如说这个题就可以这样说,说说你对startActivityForResult的理解()
>
> A开启B的时候,用startActivityForResult()方法, B返回的时候把播放的状态信息返回给A ,A继续播放音乐. 

###  :question: 什么是IntentService？有何优点？[#95](https://github.com/Sogrey/Android_QA/issues/95)

> 普通的service ,默认运行在ui main 主线程
>
> Sdk给我们提供的方便的,带有异步处理的service类,
>
> 必须有无参构造方法
>
> ​	OnHandleIntent() 处理耗时的操作

###  :question: 为什么要用ContentProvider？它和sql的实现上有什么差别？[#96](https://github.com/Sogrey/Android_QA/issues/96)

> 屏蔽数据存储的细节,对用户透明,用户只需要关心操作数据的uri就可以了不同app之间共享,操作数据Sql也有增删改查的方法.  但是contentprovider 还可以去增删改查本地文件. xml文件的读取,更改,网络数据读取更改 

### ❓ invalidate和postInvalidate的区别及使用 [#123](<https://github.com/Sogrey/Android_QA/issues/123>)

###  :question: **android线程的好处** [#110](https://github.com/Sogrey/Android_QA/issues/110)

> **1、Android有两种方式处理线程：**
>
> 比较耗时的操作放在后台服务，通过通知机制通知用户使用的活动（activity）；在后台线程中处理耗时的操作
>
> **2、使用Handler**
>
> 创建后台线程最友好的办法是创建一个Handler子类的实例。只需一个Handler对应一个Activity。自定义的后台线程可与Handler通信，Handler将与UI线程一起工作。和Handler通信，需要两个选项，message和runnable对象。
>
> **3、Message** 
>
> 发送Message到Handler，第一步调用obtainMessage()，从池中得到Message对象。
>
> 然后，可通过消息队列将Message发送给Handler，通过sendMessage…()方法族：
>
> sendMessage() 立即发送Message到消息队列
>
> sendMessageAtFrontOfQueue() 立即发送Message到队列，而且是放在队列的最前面
>
> sendMessageAtTime() 设置时间，发送Message到队列
>
> sendMessageDelayed() 在延时若干毫秒后，发送Message到队列
>
> 为了处理Message，Handler需要实现handleMessage()，当Message出现在队列中时，会调用handleMessage()方法。另外，Handler可在需要时更新UI。

### :question:Handler的原理 [#113](https://github.com/Sogrey/Android_QA/issues/113)

> 它的作用就是实现线程之间的通信。
>
>  handler整个流程中，主要有四个对象，handler，Message,MessageQueue,Looper。当应用创建的时候，就会在主线程中创建handler对象，
>
>  我们通过要传送的消息保存到Message中，handler通过调用sendMessage方法将Message发送到MessageQueue中，Looper对象就会不断的调用loop()方法
>
>  不断的从MessageQueue中取出Message交给handler进行处理。从而实现线程之间的通信。

### :question: View，ViewGroup事件分发 [#114](https://github.com/Sogrey/Android_QA/issues/114)

### :question: 自定义控件View的绘制流程 [#115](https://github.com/Sogrey/Android_QA/issues/115)

###  :question: 简单描述下Android 数字签名。[#98](https://github.com/Sogrey/Android_QA/issues/98)

### :question: 说说mvc模式的原理，它在android中的运用,android的官方建议应用程序的开发采用mvc模式。何谓mvc？[#117](https://github.com/Sogrey/Android_QA/issues/117)

### ❓ AIDL的全称是什么？如何工作？能处理哪些类型的数据？[#118](https://github.com/Sogrey/Android_QA/issues/118)

### ❓ 系统上安装了多种浏览器，能否指定某浏览器访问指定页面？[#119](https://github.com/Sogrey/Android_QA/issues/119)

### ❓ 低版本SDK如何实现高版本api？[#124](https://github.com/Sogrey/Android_QA/issues/124)

###  :question: 谈谈Android的优点和不足之处。[#97](https://github.com/Sogrey/Android_QA/issues/97)

> 优点：
>
> 1、开放性,开源 ophone  阿里云( 完全兼容android)
>
> 2、挣脱运营商束缚 
>
> 3、丰富的硬件选择 mtk android 
>
> 4、不受任何限制的开发商
>
> 5、无缝结合的Google应用
>
>  
>
> 缺点：
>
> 1、安全问题、隐私问题 
>
> 2、碎片化
>
> 3、过分依赖开发商，缺乏标准配置

###  :question: **android系统的优势和不足** [#18](https://github.com/Sogrey/Android_QA/issues/18)

> Android平台手机 5大优势：
>
> 一、开放性
>
> 在优势方面，Android平台首先就是其开发性，开发的平台允许任何移动终端厂商加入到Android联盟中来。显著的开放性可以使其拥有更多的开发者，随着用户和应用的日益丰富，一个崭新的平台也将很快走向成熟。开放性对于Android的发展而言，有利于积累人气，这里的人气包括消费者和厂商，而对于消费者来讲，随大的受益正是丰富的软件资源。开放的平台也会带来更大竞争，如此一来，消费者将可以用更低的价位购得心仪的手机。
>
> 二、挣脱运营商的束缚
>
> 在过去很长的一段时间，特别是在欧美地区，手机应用往往受到运营商制约，使用什么功能接入什么网络，几乎都受到运营商的控制。从去年iPhone 上市 ，用户可以更加方便地连接网络，运营商的制约减少。随着EDGE、HSDPA这些2G至3G移动网络的逐步过渡和提升，手机随意接入网络已不是运营商口中的笑谈，当你可以通过手机IM软件方便地进行即时聊天时，再回想不久前天价的彩信和图铃下载业务，是不是像噩梦一样？互联网巨头Google推动的Android终端天生就有网络特色，将让用户离互联网更近。
>
> 三、丰富的硬件选择
>
> 这一点还是与Android平台的开放性相关，由于Android的开放性，众多的厂商会推出千奇百怪，功能特色各具的多种产品。功能上的差异和特色，却不会影响到数据同步、甚至软件的兼容，好比你从诺基亚 Symbian风格手机 一下改用苹果 iPhone ，同时还可将Symbian中优秀的软件带到iPhone上使用、联系人等资料更是可以方便地转移，是不是非常方便呢？
>
> 四、不受任何限制的开发商
>
> Android平台提供给第三方开发商一个十分宽泛、自由的环境，不会受到各种条条框框的阻扰，可想而知，会有多少新颖别致的软件会诞生。但也有其两面性，血腥、暴力、情色方面的程序和游戏如可控制正是留给Android难题之一。
>
> 五、无缝结合的Google应用
>
> 如今叱诧互联网的Google已经走过10年度历史，从搜索巨人到全面的互联网渗透，Google服务如地图、邮件、搜索等已经成为连接用户和互联网的重要纽带，而Android平台手机将无缝结合这些优秀的Google服务。
>
> 再说Android的5大不足：
>
> 一、安全和隐私
>
> 由于手机 与互联网的紧密联系，个人隐私很难得到保守。除了上网过程中经意或不经意留下的个人足迹，Google这个巨人也时时站在你的身后，洞穿一切，因此，互联网的深入将会带来新一轮的隐私危机。
>
> 二、首先开卖Android手机的不是最大运营商
>
> 众所周知，T-Mobile在23日，于美国纽约发布 了Android首款手机G1。但是在北美市场，最大的两家运营商乃AT&T和Verizon，而目前所知取得Android手机销售权的仅有 T-Mobile和Sprint，其中T-Mobile的3G网络相对于其他三家也要逊色不少，因此，用户可以买账购买G1，能否体验到最佳的3G网络服务则要另当别论了！
>
> 三、运营商仍然能够影响到Android手机
>
> 在国内市场，不少用户对购得移动定制机不满，感觉所购的手机被人涂画了广告一般。这样的情况在国外市场同样出现。Android手机的另一发售运营商Sprint就将在其机型中内置其手机商店程序。
>
> 四、同类机型用户减少
>
> 在不少手机论坛都会有针对某一型号的子论坛，对一款手机的使用心得交流，并分享软件资源。而对于Android平台手机，由于厂商丰富，产品类型多样，这样使用同一款机型的用户越来越少，缺少统一机型的程序强化。举个稍显不当的例子，现在山寨机泛滥，品种各异，就很少有专门针对某个型号山寨机的讨论和群组，除了哪些功能异常抢眼、颇受追捧的机型以外。
>
> 五、过分依赖开发商缺少标准配置
>
> 在使用PC端的Windows Xp系统的时候，都会内置微软Windows Media Player这样一个浏览器程序，用户可以选择更多样的播放器，如Realplay或暴风影音等。但入手开始使用默认的程序同样可以应付多样的需要。在 Android平台中，由于其开放性，软件更多依赖第三方厂商，比如Android系统的SDK中就没有内置音乐 播放器，全部依赖第三方开发，缺少了产品的统一性。


###  :question: **android 适配** [#132](https://github.com/Sogrey/Android_QA/issues/132)


## :file_folder: 数据库

###  :question: 如何将SQLite数据库(dictionary.db文件)与apk文件一起发布 [#19](<https://github.com/Sogrey/Android_QA/issues/19>)

> 可以将dictionary.db文件复制到Eclipse Android工程中的res raw目录中。所有在res raw目录中的文件不会被压缩，这样可以直接提取该目录中的文件。可以将dictionary.db文件复制到res raw目录中

###  :question: 如何将打开res raw目录中的数据库文件? [#20](<https://github.com/Sogrey/Android_QA/issues/20>)

> 在Android中不能直接打开res raw目录中的数据库文件，而需要在程序第一次启动时将该文件复制到手机内存或SD卡的某个目录中，然后再打开该数据库文件。
>
> 复制的基本方法是使用getResources().openRawResource方法获得res raw目录中资源的 InputStream对象，然后将该InputStream对象中的数据写入其他的目录中相应文件中。在Android SDK中可以使用SQLiteDatabase.openOrCreateDatabase方法来打开任意目录中的SQLite数据库文件。

## :file_folder: 异常

###  :question: 什么是ANR 如何避免它？[#13](https://github.com/Sogrey/Android_QA/issues/13)

> ANR：Application Not Responding。在Android中，活动管理器和窗口管理器这两个系统服务负责监视应用程序的响应，当用户操作的在5s内应用程序没能做出反应，BroadcastReceiver在10秒内没有执行完毕，就会出现应用程序无响应对话框，这既是ANR。
>
> 避免方法：Activity应该在它的关键生命周期方法（如onCreate()和onResume()）里尽可能少的去做创建操作。潜在的耗时操作，例如网络或数据库操作，或者高耗时的计算如改变位图尺寸，应该在子线程里（或者异步方式）来完成。主线程应该为子线程提供一个Handler，以便完成时能够提交给主线程。

###  :question: 什么情况会导致Force Close ？如何避免？能否捕获导致其的异常？[#14](https://github.com/Sogrey/Android_QA/issues/14)

> 程序出现异常，比如nullpointer。
>
> 避免：编写程序时逻辑连贯，思维缜密。能捕获异常，在logcat中能看到异常信息

###  :question: **Android本身的api并未声明会抛出异常，则其在运行时有无可能抛出runtime异常，你遇到过吗？诺有的话会导致什么问题？如何解决？** [#15](https://github.com/Sogrey/Android_QA/issues/15)

> 会，比如nullpointerException。我遇到过，比如textview.setText()时，textview没有初始化。会导致程序无法正常运行出现forceclose。打开控制台查看logcat信息找出异常信息并修改程序。

###  :question: error和exception有什么区别 [#42](https://github.com/Sogrey/Android_QA/issues/42)

> - error 表示恢复不是不可能但很困难的情况下的一种严重问题。比如说内存溢出。不可能指望程序能处理这样的情况
>
> - exception 表示一种设计或实现问题。也就是说，它表示如果程序运行正常，从不会发生的情况

###  :question: 给我一个你最常见到的runtime exception [#43](https://github.com/Sogrey/Android_QA/issues/43)

> 常见的运行时异常有如下这些ArithmeticException, ArrayStoreException, 
> BufferOverflowException, BufferUnderflowException, CannotRedoException, 
> CannotUndoException, ClassCastException, CMMException, ConcurrentModificationException,
> DOMException, EmptyStackException, IllegalArgumentException, IllegalMonitorStateException, 
> IllegalPathStateException, IllegalStateException, ImagingOpException, 
> IndexOutOfBoundsException, MissingResourceException, NegativeArraySizeException, 
> NoSuchElementException, NullPointerException, ProfileDataException, ProviderException, 
> RasterFormatException, SecurityException, SystemException, UndeclaredThrowableException, 
> UnmodifiableSetException, UnsupportedOperationException

###  :question: try {}里有一个return语句，那么紧跟在这个try后的finally {}里的code会不会被执行，什么时候被执行，在return前还是后 [#44](https://github.com/Sogrey/Android_QA/issues/44)

> 会执行，在return前执行

###  :question: 运行时异常与一般异常有何异同 [#45](https://github.com/Sogrey/Android_QA/issues/45)

> 异常表示程序运行过程中可能出现的非正常状态，运行时异常表示虚拟机的通常操作
> 中可能遇到的异常，是一种常见运行错误。java编译器要求方法必须声明抛出可能发生的
> 非运行时异常，但是并不要求必须声明抛出未被捕获的运行时异常。

###  :question: Java中的异常处理机制的简单原理和应用 [#46](https://github.com/Sogrey/Android_QA/issues/46)

> 当JAVA程序违反了JAVA的语义规则时，JAVA虚拟机就会将发生的错误表示为一个异常。
> 违反语义规则包括2种情况。一种是JAVA类库内置的语义检查。例如数组下标越界,会引发
> IndexOutOfBoundsException;访问null的对象时会引发NullPointerException。另一种情况
> 就是JAVA允许程序员扩展这种语义检查，程序员可以创建自己的异常，并自由选择在何时
> 用throw关键字引发异常。所有的异常都是java.lang.Thowable的子类。

###  :question: JAVA语言如何进行异常处理，关键字：throws,throw,try,catch,finally分别代表什么意义？在try块中可以抛出异常吗？ [#47](https://github.com/Sogrey/Android_QA/issues/47)

> Java通过面向对象的方法进行异常处理，把各种不同的异常进行分类，并提供了良好的接口。在Java中，每个异常都是一个对象，它是Throwable类或其它子类的实例。当一个方法出现异常后便抛出一个异常对象，该对象中包含有异常信息，调用这个对象的方法可以捕获到这个异常并进行处理。Java的异常处理是通过5个关键词来实现的：try、catch、throw、throws和finally。一般情况下是用try来执行一段程序，如果出现异常，系统会抛出（throws）一个异常，这时候你可以通过它的类型来捕捉（catch）它，或最后（finally）由缺省处理器来处理。
> 用try来指定一块预防所有"异常"的程序。紧跟在try程序后面，应包含一个catch子句来指定你想要捕捉的"异常"的类型。
> throw语句用来明确地抛出一个"异常"。
> throws用来标明一个成员函数可能抛出的各种"异常"。
> Finally为确保一段代码不管发生什么"异常"都被执行一段代码。
> 可以在一个成员函数调用的外面写一个try语句，在这个成员函数内部写另一个try语句保护其他代码。每当遇到一个try语句，"异常"的框架就放到堆栈上面，直到所有的try语句都完成。如果下一级的try语句没有对某种"异常"进行处理，堆栈就会展开，直到遇到有处理这种"异常"的try语句。

### :question: ​导致内存泄露的原因有哪些？ [#111](<https://github.com/Sogrey/Android_QA/issues/111>)



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

---

## :file_folder: 其他面经库

**Mr-YangCheng/ForAndroidInterview**
<div class="github-widget" data-repo="Mr-YangCheng/ForAndroidInterview"></div>
**Shouheng88/Android-notes**
<div class="github-widget" data-repo="Shouheng88/Android-notes"></div>
**whatshappen/Android_Question**
<div class="github-widget" data-repo="whatshappen/Android_Question"></div>
**derekargueta/Android-Interview-Questions**
<div class="github-widget" data-repo="derekargueta/Android-Interview-Questions"></div>
**JackyAndroid/AndroidInterview-Q-A**
<div class="github-widget" data-repo="JackyAndroid/AndroidInterview-Q-A"></div>
**stormzhang/android-interview-questions-cn**
<div class="github-widget" data-repo="stormzhang/android-interview-questions-cn"></div>
**Advanced-Frontend/Daily-Interview-Question**
<div class="github-widget" data-repo="Advanced-Frontend/Daily-Interview-Question"></div>
<div><script type="text/javascript" src="https://git.hust.cc/GitHub-Repo-Widget.js/GithubRepoWidget.js"></script></div>


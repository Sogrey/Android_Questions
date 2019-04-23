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

## Java基础

### 一个".java"源文件中是否可以包括多个类（不是内部类）？有什么限制？[#21](https://github.com/Sogrey/Android_QA/issues/21)

> 可以。必须只有一个类名与文件名相同。

### GC是什么? 为什么要有GC [#22](https://github.com/Sogrey/Android_QA/issues/22)

> GC是垃圾收集的意思（Gabage Collection）,内存处理是编程人员容易出现问题的地方，
> 忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java提供的GC功能可以自动
> 监测对象是否超过作用域从而达到自动回收内存的目的，Java语言没有提供释放已分配内存
> 的显示操作方法。

### 垃圾回收器的基本原理是什么？垃圾回收器可以马上回收内存吗？有什么办法主动通知虚拟机进行垃圾回收 [#23](https://github.com/Sogrey/Android_QA/issues/23)

> 对于GC来说，当程序员创建对象时，GC就开始监控这个对象的地址、大小以及使用情况。通常，GC采用
> 有向图的方式记录和管理堆(heap)中的所有对象。通过这种方式确定哪些对象是"可达的"，哪些对象是"不可达的"。
> 当GC确定一些对象为"不可达"时，GC就有责任回收这些内存空间。可以。程序员可以手动执行System.gc()，
> 通知GC运行，但是Java语言规范并不保证GC一定会执行。

### 写出输出的结果.(考查运算符的优先级) [#24](https://github.com/Sogrey/Android_QA/issues/24)

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

### 插入代码，实现n和m值的交换 [#25](https://github.com/Sogrey/Android_QA/issues/25)

``` java
int n = 5,m = 13;
//TODO 插入代码，实现n和m值的交换
System.out.println("n="+n+",m="+m);
```

### 如何手动实现整型数值60的二进制到十六进制的转换 [#26](https://github.com/Sogrey/Android_QA/issues/26)

### short s1 = 1; s1 = s1 + 1;有什么错? short s1 = 1; s1 += 1;有什么错 [#27](https://github.com/Sogrey/Android_QA/issues/27)

> short s1 = 1; s1 = s1 + 1; （s1+1运算结果是int型，需要强制转换类型）
> short s1 = 1; s1 += 1;（可以正确编译）

### Java有没有goto [#28](https://github.com/Sogrey/Android_QA/issues/28)

> java中的保留字，现在没有在java中使用

### 用最有效率的方法算出2乘以8等於几 [#29](https://github.com/Sogrey/Android_QA/issues/29)

> 2 << 3

### char型变量中能不能存贮一个中文汉字?为什么? [#30](https://github.com/Sogrey/Android_QA/issues/30)

> 是能够定义成为一个中文的，因为java中以unicode编码，一个char占16个字节，
> 所以放一个中文是没问题的

### float型float f=3.4是否正确? [#31](https://github.com/Sogrey/Android_QA/issues/31)

> 不正确。精度不准确,应该用强制类型转换，如下所示：float f=(float)3.4;

### String是最基本的数据类型吗 [#32](https://github.com/Sogrey/Android_QA/issues/32)

> 基本数据类型包括byte、int、char、long、float、double、boolean和short。
> java.lang.String类是final类型的，因此不可以继承这个类、不能修改这个类。为了提高效率节省空间，我们应该用StringBuffer类

### 数组a[n]，用java代码将数组元素顺序颠倒 [#33](https://github.com/Sogrey/Android_QA/issues/33)

### 从键盘分别输入年、月、日，判断这一天是当年的第几天。[#34](https://github.com/Sogrey/Android_QA/issues/34)

### 输入两个正整数m和n，求其最大公约数和最小公倍数 [#35](https://github.com/Sogrey/Android_QA/issues/35)

### 3000米长的绳子，每天减一半。问多少天这个绳子会小于5米？不考虑小数。 [#36](https://github.com/Sogrey/Android_QA/issues/36)

### 编写程序，判断给定的某个年份是否是闰年。 [#37](https://github.com/Sogrey/Android_QA/issues/37)

### 利用程序输出如下图形: [#38](https://github.com/Sogrey/Android_QA/issues/38)

```
   *
   * * *
   * * * * *
   * * * * * * *
   * * * * *
   * * *
   *
```

### 一个数如果恰好等于它的因子之和，这个数就称为"完数"。（因子：除去这个数本身正的约数）[#39](https://github.com/Sogrey/Android_QA/issues/39)
例如6=1＋2＋3.编程 找出1000以内的所有完数

### 输出所有的水仙花数，所谓水仙花数是指一个3位数，其各个位上数字立方和等于其本身。[#40](https://github.com/Sogrey/Android_QA/issues/40)
例如： 153 = 1*1*1 + 3*3*3 + 5*5*5 

### 打印九九乘法表 [#41](https://github.com/Sogrey/Android_QA/issues/41)

### String s = new String("xyz");创建了几个String Object [#48](https://github.com/Sogrey/Android_QA/issues/48)

> 两个，一个字符对象，一个字符对象引用对象

### String与StringBuffer的区别。 [#49](https://github.com/Sogrey/Android_QA/issues/49)

> String的长度是不可变的，StringBuffer的长度是可变的。如果你对字符串中的内容经常进行操作，
> 特别是内容要修改时，那么使用StringBuffer，如果最后需要String，那么使用StringBuffer的toString()方法

## 核心

### Android的四大组件是哪些，它们的作用？[#1](https://github.com/Sogrey/Android_QA/issues/1)

> - Activity：Activity是Android程序与用户交互的窗口，是Android构造块中最基本的一种，它需要为保持各界面的状态，做很多持久化的事情，妥善管理生命周期以及一些跳转逻辑
> - service：后台服务于Activity，封装有一个完整的功能逻辑实现，接受上层指令，完成相关的事物，定义好需要接受的Intent提供同步和异步的接口
> - Content Provider：是Android提供的第三方应用数据的访问方案，可以派生Content Provider类，对外提供数据，可以像数据库一样进行选择排序，屏蔽内部数据的存储细节，向外提供统一的借口模型，大大简化上层应用，对数据的整合提供了更方便的途径
> - BroadCast Receiver：接受一种或者多种Intent作触发事件，接受相关消息，做一些简单处理，转换成一条Notification，统一了Android的事件广播模型

### 请介绍下Android中常用的五种布局。[#2](https://github.com/Sogrey/Android_QA/issues/2)

> 常用五种布局方式，分别是：FrameLayout（框架布局），LinearLayout （线性布局），AbsoluteLayout（绝对布局），RelativeLayout（相对布局），TableLayout（表格布局）。
>
> - FrameLayout：所有东西依次都放在左上角，会重叠，这个布局比较简单，也只能放一点比较简单的东西。
> - LinearLayout：线性布局，每一个LinearLayout里面又可分为垂直布局（android:orientation="vertical"）和水平布局（android:orientation="horizontal" ）。当垂直布局时，每一行就只有一个元素，多个元素依次垂直往下；水平布局时，只有一行，每一个元素依次向右排列。
> - AbsoluteLayout：绝对布局用X,Y坐标来指定元素的位置，这种布局方式也比较简单，但是在屏幕旋转时，往往会出问题，而且多个元素的时候，计算比较麻烦。
> - RelativeLayout：相对布局可以理解为某一个元素为参照物，来定位的布局方式。主要属性有：相对于某一个元素android:layout_below、      android:layout_toLeftOf相对于父元素的地方android:layout_alignParentLeft、android:layout_alignParentRigh；
> - TableLayout：表格布局，每一个TableLayout里面有表格行TableRow，TableRow里面可以具体定义每一个元素。每一个布局都有自己适合的方式，这五个布局元素可以相互嵌套应用，做出美观的界面。

### android中的动画有哪几类，它们的特点和区别是什么 [#3](https://github.com/Sogrey/Android_QA/issues/3)

> 两种，一种是Tween动画、还有一种是Frame动画。
>
> - Tween动画，这种实现方式可以使视图组件移动、放大、缩小以及产生透明度的变化;
> - Frame动画，传统的动画方法，通过顺序的播放排列好的图片来实现，类似电影。

### android 中有哪几种解析xml的类？官方推荐哪种？以及它们的原理和区别。[#4](https://github.com/Sogrey/Android_QA/issues/4)

> XML解析主要有三种方式，SAX、DOM、PULL。
>
> 常规在PC上开发我们使用Dom相对轻松些，但一些性能敏感的数据库或手机上还是主要采用SAX方式，SAX读取是单向的，优点:不占内存空间、解析属性方便，但缺点就是对于套嵌多个分支来说处理不是很方便。而DOM方式会把整个XML文件加载到内存中去，这里Android开发网提醒大家该方法在查找方面可以和XPath很好的结合如果数据量不是很大推荐使用，而PULL常常用在J2ME对于节点处理比较好，类似SAX方式，同样很节省内存，在J2ME中我们经常使用的KXML库来解析。

### ListView的优化方案 [#5](https://github.com/Sogrey/Android_QA/issues/5)

>  1、如果自定义适配器，那么在getView方法中要考虑方法传进来的参数contentView是否为null，如果为null就创建contentView并返回，如果不为null则直接使用。在这个方法中尽可能少创建view。
>
>   2、给contentView设置tag（setTag（）），传入一个viewHolder对象，用于缓存要显示的数据，可以达到图像数据异步加载的效果。
>
>   3、如果listview需要显示的item很多，就要考虑分页加载。比如一共要显示100条或者更多的时候，我们可以考虑先加载20条，等用户拉到列表底部的时候再去加载接下来的20条。

### 请介绍下Android的数据存储方式。[#6](https://github.com/Sogrey/Android_QA/issues/6)

> 使用SharedPreferences存储数据；文件存储数据；SQLite数据库存储数据；使用ContentProvider存储数据；网络存储数据；

### activity的启动模式有哪些？是什么含义？[#7](https://github.com/Sogrey/Android_QA/issues/7)

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

### 请描述一下Activity的生命周期 [#8](https://github.com/Sogrey/Android_QA/issues/8)

> - onCreate(Bundle savedInstanceState)：创建Activity时调用，设置在该方法中，还以Bundle的形式提供对以前存储的任何状态的访问。
> - onStart（）：activity变为在屏幕上对用户可见时调用
> - onResume（）：activity开始与用户交互时调用（无论是启动还是重新启动一个activity，该方法总是被调用）
> - onPause（）：activity被暂停或者收回cpu和其他资源时调用，该方法用于保存活动状态的，也是保护现场，压栈吧
> - onStop（）：activity被停止并转为不可见阶段及后续的生命周期事件时调用。
> - onRestart（）：重新启动activity时调用，该活动仍在栈中，而不是启动新的activity
> - onDestroy（）：activity被完全从系统内存中移除时调用  

### 两个Activity之间跳转时必然会执行的是哪几个方法 [#9](https://github.com/Sogrey/Android_QA/issues/9)

> - onCreate（）：在activity生命周期开始时调用
> - onRestoreInstanceState（）：用来恢复UI状态
> - onRestart（）：当activity重新启动时调用
> - onStart（）：当activity对用户即将可见时调用
> - onResume（）：当activity与用户交互时，绘制界面
> - onSaveInstanceState（）：当activity即将移除栈顶保留UI状态时被调用
> - onPause（）：暂停当前活动的activity，提交持久数据的改变，停止动画和其他占用CPu资源的东西，由于下一个activity在这个方法返回之前不会resume，所以这个方法的代码执行要快
> - onStop（）：activity不再可见时调用
> - onDestroy（）：在activity销毁栈时被调用的最后一个方法  

### 横竖屏幕切换时候activity的生命周期 [#10](https://github.com/Sogrey/Android_QA/issues/10)

> ①不设置activity的android:configChanges时，切屏会重新调用各个生命周期，切横屏时会执行一次，且竖屏时会执行两次
>
> ②设置activity的android:configChanges=”orientation"时，切屏还是会调用各个生命周期，切横屏，竖屏时只会执行一次
>
> ③设置activity的android:configChanges="orientation|keyboardHidden"时，切屏不会重新调用各个生命周期，只会执行onConfigurationChanged方法

### 如何将一个activity设置为窗口的样式 [#11](https://github.com/Sogrey/Android_QA/issues/11)

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

### 两个activity之间怎样传递数据 [#12](https://github.com/Sogrey/Android_QA/issues/12)

>   在Intent的对象中增加要传递的参数即可
>
>   在Intent对象的请求中加入键值对，对应名字`.putExtra`（“键值对的名字","键值对的值");在另一个activity中将Intent的请求中的数据取出来：
>
>   ``` java
>   Intent intent= getIntent（）；
>   String value = intent.getStringExtra("testIntent") ;
>   ```

### **IntentService有何优点?** [#16](https://github.com/Sogrey/Android_QA/issues/16)

> Acitivity的进程，当处理Intent的时候，会产生一个对应的Service； Android的进程处理器现在会尽可能的不kill掉你；非常容易使用

### 如果后台的Activity由于某原因被系统回收了，如何在被系统回收之前保存当前状态？[#17](https://github.com/Sogrey/Android_QA/issues/17)

> 重写onSaveInstanceState()方法，在此方法中保存需要保存的数据，该方法将会在activity被回收之前调用。通过重写onRestoreInstanceState()方法可以从中提取保存好的数据

### **android系统的优势和不足** [#18](https://github.com/Sogrey/Android_QA/issues/18)

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

## 数据库

### 如何将SQLite数据库(dictionary.db文件)与apk文件一起发布 [#19](<https://github.com/Sogrey/Android_QA/issues/19>)

> 可以将dictionary.db文件复制到Eclipse Android工程中的res raw目录中。所有在res raw目录中的文件不会被压缩，这样可以直接提取该目录中的文件。可以将dictionary.db文件复制到res raw目录中

### 如何将打开res raw目录中的数据库文件? [#20](<https://github.com/Sogrey/Android_QA/issues/20>)

> 在Android中不能直接打开res raw目录中的数据库文件，而需要在程序第一次启动时将该文件复制到手机内存或SD卡的某个目录中，然后再打开该数据库文件。
>
> 复制的基本方法是使用getResources().openRawResource方法获得res raw目录中资源的 InputStream对象，然后将该InputStream对象中的数据写入其他的目录中相应文件中。在Android SDK中可以使用SQLiteDatabase.openOrCreateDatabase方法来打开任意目录中的SQLite数据库文件。

## 异常

### 什么是ANR 如何避免它？[#13](https://github.com/Sogrey/Android_QA/issues/13)

> ANR：Application Not Responding。在Android中，活动管理器和窗口管理器这两个系统服务负责监视应用程序的响应，当用户操作的在5s内应用程序没能做出反应，BroadcastReceiver在10秒内没有执行完毕，就会出现应用程序无响应对话框，这既是ANR。
>
> 避免方法：Activity应该在它的关键生命周期方法（如onCreate()和onResume()）里尽可能少的去做创建操作。潜在的耗时操作，例如网络或数据库操作，或者高耗时的计算如改变位图尺寸，应该在子线程里（或者异步方式）来完成。主线程应该为子线程提供一个Handler，以便完成时能够提交给主线程。

### 什么情况会导致Force Close ？如何避免？能否捕获导致其的异常？[#14](https://github.com/Sogrey/Android_QA/issues/14)

> 程序出现异常，比如nullpointer。
>
> 避免：编写程序时逻辑连贯，思维缜密。能捕获异常，在logcat中能看到异常信息

### **Android本身的api并未声明会抛出异常，则其在运行时有无可能抛出runtime异常，你遇到过吗？诺有的话会导致什么问题？如何解决？** [#15](https://github.com/Sogrey/Android_QA/issues/15)

> 会，比如nullpointerException。我遇到过，比如textview.setText()时，textview没有初始化。会导致程序无法正常运行出现forceclose。打开控制台查看logcat信息找出异常信息并修改程序。

### error和exception有什么区别 [#42](https://github.com/Sogrey/Android_QA/issues/42)

> - error 表示恢复不是不可能但很困难的情况下的一种严重问题。比如说内存溢出。不可能指望程序能处理这样的情况
>
> - exception 表示一种设计或实现问题。也就是说，它表示如果程序运行正常，从不会发生的情况

### 给我一个你最常见到的runtime exception [#43](https://github.com/Sogrey/Android_QA/issues/43)

> 常见的运行时异常有如下这些ArithmeticException, ArrayStoreException, 
> BufferOverflowException, BufferUnderflowException, CannotRedoException, 
> CannotUndoException, ClassCastException, CMMException, ConcurrentModificationException,
> DOMException, EmptyStackException, IllegalArgumentException, IllegalMonitorStateException, 
> IllegalPathStateException, IllegalStateException, ImagingOpException, 
> IndexOutOfBoundsException, MissingResourceException, NegativeArraySizeException, 
> NoSuchElementException, NullPointerException, ProfileDataException, ProviderException, 
> RasterFormatException, SecurityException, SystemException, UndeclaredThrowableException, 
> UnmodifiableSetException, UnsupportedOperationException

### try {}里有一个return语句，那么紧跟在这个try后的finally {}里的code会不会被执行，什么时候被执行，在return前还是后 [#44](https://github.com/Sogrey/Android_QA/issues/44)

> 会执行，在return前执行

### 运行时异常与一般异常有何异同 [#45](https://github.com/Sogrey/Android_QA/issues/45)

> 异常表示程序运行过程中可能出现的非正常状态，运行时异常表示虚拟机的通常操作
> 中可能遇到的异常，是一种常见运行错误。java编译器要求方法必须声明抛出可能发生的
> 非运行时异常，但是并不要求必须声明抛出未被捕获的运行时异常。

### Java中的异常处理机制的简单原理和应用 [#46](https://github.com/Sogrey/Android_QA/issues/46)

> 当JAVA程序违反了JAVA的语义规则时，JAVA虚拟机就会将发生的错误表示为一个异常。
> 违反语义规则包括2种情况。一种是JAVA类库内置的语义检查。例如数组下标越界,会引发
> IndexOutOfBoundsException;访问null的对象时会引发NullPointerException。另一种情况
> 就是JAVA允许程序员扩展这种语义检查，程序员可以创建自己的异常，并自由选择在何时
> 用throw关键字引发异常。所有的异常都是java.lang.Thowable的子类。

### JAVA语言如何进行异常处理，关键字：throws,throw,try,catch,finally分别代表什么意义？在try块中可以抛出异常吗？ [#47](https://github.com/Sogrey/Android_QA/issues/47)

> Java通过面向对象的方法进行异常处理，把各种不同的异常进行分类，并提供了良好的接口。在Java中，每个异常都是一个对象，它是Throwable类或其它子类的实例。当一个方法出现异常后便抛出一个异常对象，该对象中包含有异常信息，调用这个对象的方法可以捕获到这个异常并进行处理。Java的异常处理是通过5个关键词来实现的：try、catch、throw、throws和finally。一般情况下是用try来执行一段程序，如果出现异常，系统会抛出（throws）一个异常，这时候你可以通过它的类型来捕捉（catch）它，或最后（finally）由缺省处理器来处理。
> 用try来指定一块预防所有"异常"的程序。紧跟在try程序后面，应包含一个catch子句来指定你想要捕捉的"异常"的类型。
> throw语句用来明确地抛出一个"异常"。
> throws用来标明一个成员函数可能抛出的各种"异常"。
> Finally为确保一段代码不管发生什么"异常"都被执行一段代码。
> 可以在一个成员函数调用的外面写一个try语句，在这个成员函数内部写另一个try语句保护其他代码。每当遇到一个try语句，"异常"的框架就放到堆栈上面，直到所有的try语句都完成。如果下一级的try语句没有对某种"异常"进行处理，堆栈就会展开，直到遇到有处理这种"异常"的try语句。

## Kotlin相关


#1.static关键字的用法
  用法：修饰变量，方法；静态块；静态内部类；
  没有用过静态导包：静态导入B类的静态成员变量和静态方法，A类使用B类的静态变量和静态函数，无需指明类名
<pre><code>
  java example:
  package com.highpay.zoom.a;

  import static com.highpay.zoom.b.BB;
  import static com.highpay.zoom.b.hello;

  class A{
    public static void main(String[] args){
      //直接使用B类的静态变量和函数，无需声明类名
      //缺点是带来代码可读性比较差
       System.out.println(hello(BB));
    }

  }

  package com.highpay.zoom.b;

  clsss B{
    public static final String BB = "123"
    public static void hello(){
      System.out.println("hello");
    }
  }
</code></pre>
#2.java foreach的原理
      target实现iterable接口，该接口定义了iterator迭代器的产生方法
      iterator接口的实现方法有
      hasNext()
      next()
      remove()
#3.transient关键字
<pre>
java对象在序列化时实现serializable接口，用来表示一个域不是该对象可串行化的一部分
简单点理解就是对象的字段用该关键字修饰后，在反序列化时获取不到。
<code>

</code>
</pre>
#4.volatile关键字
  <pre>
 volatile修饰的成员变量在每次被线程访问时，都强迫从主内存中重读该成员变量的值，而且当变量
发生变化时，强迫线程将最新的值写入主内存，这样保持两个不同的线程看到的总是同一个相同的值。

底层实现原理:
valatile关键字修饰的共享变量在写操作时，编译器生成的汇编代码中会带有lock前缀

多核CPU会做2件事情：
 1）将当前处理器缓存行的数据写回到系统内存
 2）这个写回内存的操作会引起其他CPU里缓存了该内存地址的数据无效（实现了缓存一致性协议）

每个处理器通过嗅探在总线上传播的数据来检查自己缓存的值是不是过期了，
当处理器发现自己缓存行对应的内存地址被修改，就会将当前处理器的缓存行设置成无效状态，
当处理器要对这个数据进行修改操作的时候，会强制重新从系统内存里把数据读到处理器缓存里。

今天有人又抛出volatile使用的内存屏障？
java内存屏障有哪几种？
 </pre>

#5.HashMap,HashTable,CurrentHashMap源代码理解
<pre>
   jdk6,7,8中CurrentHashMap的优化
   

</pre>
#6.object的sleep()和wait()区别

#7.ArrayList,HashSet,LinkedList，CopyOnWriteArrayList，CopyOnWriteArraySet

#8.java的隐式转换（小到大）和显示转换（大到小）、
<pre>
   自动转换按从低到高的顺序转换。不同类型数据间的优先关系如下：
    低--------------------------------------------->高
    byte,short,char-> int -> long -> float -> double
    为什么可以转呢？联系下分配内存的大小
    
    short i =1; i = i +1与short j = 1；j+=1;有什么问题？
 
</pre>
#9.try catch的原理，多个catch的执行顺序和原理？java的异常处理机制？
  <pre>
    调用catch子句中的精确的异常处理，如果没有就调用其父类的异常处理
  </pre>

#10.java的死锁实例，产生死锁的必要条件是什么？怎样避免死锁？如果发生死锁，怎么解决这个问题？

#11.java的接口和抽象类（1.8之前的）


#12.GC的原理，GC是否可以实时由程序员来调用执行？System.gc(),system.getRuntime.gc(),finalize()的作用。



#13.socket编程基础



#14.java的类加载器，类加载机制，双亲委派机制，为什么要使用这种机制，自定义类加载器，自定义类加载器与java自带的类加载器关系怎么处理？



#15.t1,t2,t3线程怎样保证三个线程顺序执行







---
title:  "java 中instanceof和isInstance 区别"

date:   2018-05-20

categories: text

---

* 都可以确定对象的类型，而且结果一样

* instanceof是java的一个操作符或语法关键字，instanceof有左右操作数，左操作数必须是一个对象的引用.`右操作数必须是一个类名`，这一点很重要，因为右操作数是`类名`，所以在`编译期间必须确定`，而isInstance可以在运行期间确定类名。

* 虽然这里instanceof表达式的左操作数是一个静态类型为Object的引用，但它指向的对象的实际类型是Foo，所以该instanceof表达式的值就为true。

{% highlight java %}

Object obj = new Foo();
boolean b = obj instanceof Foo; //obj引用对象的真实类型是否为Foo类型或Foo的子类，true
```

{% endhighlight %}

* isInstance是Class对象的实例方法

{% highlight java %}

//函数原型
boolean isInstance (Object object)

{% endhighlight %}

* 这里展示了isInstance和instanceof最大的不同：动态性。动态性体现在：类型是在运行时，调用对象的getClass方法确定的，而不是在编译时确定的。

{% highlight java %}

Object o1 = new A();
Object o2 = new B();

boolean b = o1.getClass().isInstance(o2);

{% endhighlight %}


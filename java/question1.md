__原文地址：__

http://stackoverflow.com/questions/40480/is-java-pass-by-reference

__问题原文：__

Java是传引用吗？

__问题补充：__

我一直以为Java是传引用的，然而我看到有些博客(例如 [这个博客](http://javadude.com/articles/passbyvalue.htm))它说Java不是传引用的，我不明白它们的区别。

有人能解释一下吗？

__回答1：__

Java一直是传值，难以理解的地方在于Java传对象时传值就像传引用一样。

它像这样：
```java
public void foo(Dog d) {
  d.name.equals("Max"); // true
  d = new Dog("Fifi");
  d.name.equals("Fifi"); // true
}

Dog aDog = new Dog("Max");
foo(aDog);
aDog.name.equals("Max"); // true
```

在这个例子中`aDog.name`一直是"Max","d"没有在函数中被像传对象引用一样的传值所覆盖。

同样还有:
```java
public void foo(Dog d) {
  d.name.equals("Max"); // true
  d.setname("Fifi");
}

Dog aDog = new Dog("Max");
foo(aDog);
aDog.name.equals("Fifi"); // true
```

**本人理解:**

在Java和JavaScript中从来都是传值，没有所谓的传引用，但是工作中经常遇到同事说传引用，因为传引用对他们来说很好理解，这是由于他们不太了解堆和栈，对于基本类型，由于存储大小固定，比如int四个字节，是直接存储在栈中的，但对于引用类型，我们并不知道它实际大小，所以把它存在堆中，给一个堆里的地址放在栈中，当传递时传的是这个地址，形参和实参指向同一个地址而已，如果用形参改变地址里的值，实参当然会改变，但当形参指向别处时，实参是不可能跟着变的，所以这是传值，而不是传引用。
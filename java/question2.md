__原文地址：__

http://stackoverflow.com/questions/8710619/java-operator

__问题原文：__

Java += 操作

__问题补充：__

直到现在我都以为，举个例子：

```
i += j;
```

是下面的简写：

```
i = i + j;
```

但是当我尝试这个的时候:

```
int i = 5;
long j = 8;
```

这时`i = i + j;`编译出错但`i += j;`编译时正常的。这是不是意味着`i += j;`实际上是其它的简写类似`i = (type of i) (i + j)`?我尝试过去Google但是没有任何收获。


__回答1：__

碰到这类问题，JLS总会给出答案。本问题[§15.26.2 Compound Assignment Operators](http://docs.oracle.com/javase/specs/jls/se5.0/html/expressions.html#15.26.2)。摘录:
> A compound assignment expression of the form E1 op= E2 is equivalent to E1 = (T)((E1) op (E2)), where T is the type of E1, except that E1 is evaluated only once.

引用自[§15.26.2](http://docs.oracle.com/javase/specs/jls/se5.0/html/expressions.html#15.26.2)


	[...]下面的代码是正确的：
	
	short x = 3;
	x += 4.6;
	
	x的结果是7，因为它等价于：
	
	short x = 3;
	x = (short)(x + 4.6);

换句话说，你的怀疑是正确的。

**本人理解:**

我记得我们以前的老师就是讲是简写，等价的。后来在一本书上面看到两者的这点差别，其实Java或者JS中很多看起来效果一样的操作，细究起来是有区别的，比如
    
    java:

    String s1 = new String('hello');
    String s2 = new String('hello').intern();
    String s3 = 'hello';

    js:
    
    function foo(){}
    var bar = function{}

话说这些都面试题的题目，也很基础，要知道原因，不求甚解或者不会碰到不是你的借口。
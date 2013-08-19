__原文地址：__

http://stackoverflow.com/questions/1066589/java-iterate-through-hashmap

__问题原文：__

遍历HashMap键值 

__问题补充：__

问题可能重复：

[如何遍历集合Map？](http://stackoverflow.com/questions/46898/how-do-i-iterate-over-each-entry-in-a-map)

__回答1:__

像下面这样遍历`entrySet`:

```java
public static void printMap(Map mp) {
    Iterator it = mp.entrySet().iterator();
    while (it.hasNext()) {
        Map.Entry pairs = (Map.Entry)it.next();
        System.out.println(pairs.getKey() + " = " + pairs.getValue());
        it.remove(); // avoids a ConcurrentModificationException
    }
}
```

有关[Map](http://docs.oracle.com/javase/1.4.2/docs/api/java/util/Map.html)更多内容

**本人理解：**

这个很基本的，无需解释，多读读文档。
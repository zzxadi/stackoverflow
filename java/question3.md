__原文地址：__

http://stackoverflow.com/questions/40471/differences-between-hashmap-and-hashtable

__问题原文：__

HashMap与Hashtable有何不同？

__问题补充：__

在Java中`HashMap`与`Hashtable`有什么不同？那个在*单线程*应用中更高效？

__回答1__:

在Java中它们有以下几点差别：
 
&nbsp;&nbsp;1.[Hashtable]()是同步的，而[HashMap]不是的。这个使HashMap在单线程应用中更好些，由于不同步的对象明显性能优于同步的对象。
&nbsp;&nbsp;2.`Hashtable`不容许键或值为空，`HashMap`容许一个键为空和任意数量的值为空。           
&nbsp;&nbsp;3.HashMap有一个子类是[LinkedHashMap](),所以当你想要遍历（默认为插入的顺序）时,你可以轻松的使用一个`LinkedHashMap`的HashMap,如果使用`Hashtable`会麻烦些。

由于你不关心同步，我推荐使用`HashMap`。如果考虑同步，你也可以试试[ConcurrentHashMap](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/ConcurrentHashMap.html)

**本人理解：**

Hashtable是JDK诞生就有的，所以你看命名都不规范(规范应为HashTable)，而HashMap是JDK1.2引入的，其作为就是替代Hashtable，我知道1,2两点，第3点也比较重要。
## StockoverflowRestful API

### 吾生也有涯，而知也无涯

| 版本号 | 修改人          | 修改日期   | 修改内容    |
| ------ | --------------- | ---------- | ----------- |
| v1.0   | shanYueFenCheng | 2019-08-19 | Restful文档 |

### 说明

翻译Stackoverflow的问题与答案，参考谷歌翻译，结合中文，保留原意的基础上有精简，代码风格贴近中文，仅用于分享和学习，有什么错误，请多多指教

### HashMap和Hashtable之间的区别？

Java中的HashMap和Hashtable有什么区别？哪个在非多线程程序更有效？

[原文]<https://stackoverflow.com/questions/40471/differences-between-hashmap-and-hashtable> )

#### 获得认同最多的回答

#### 一、区别

Java中的HashMap和Hashtable有下面几点不同：

一，同步性：Hashtable是加锁的，HashMap不是，HashMap无法保证同步性。这使得HashMap更适合非多线程的程序

二，性能差异：非加锁对象HashMap比加锁对象Hashtable执行效率更高。

```
注意:
	理解同步性与线程安全的核心要素
	1存在共享变量
	2在多线程环境
	3共享变量有修改操作
```

三，空值限制：Hashtable的key和value不允许使用null， HashMap允许一个空key和任意数量的null值。

#### 二、结论

非多线程场景下：使用HashMap，Hashtable已经过时但没有弃用，现在还保留是因为20世纪90年代的遗留代码API。需要同步的话，请使用ConcurrentHashMap或者外部同步HashMap（充分考虑多线程后果）。

[上一篇：**Java是“通过引用传递”还是“值传递”**](https://github.com/LucaceLC/StackoverflowJavaQuestion/blob/master/Java%E5%80%BC/%E3%80%90Java%E5%80%BC%E4%BC%A0%E9%80%92%E3%80%91%E3%80%901%E3%80%91%E3%80%90Java%E6%98%AF%E2%80%9C%E9%80%9A%E8%BF%87%E5%BC%95%E7%94%A8%E4%BC%A0%E9%80%92%E2%80%9D%E8%BF%98%E6%98%AF%E2%80%9C%E5%80%BC%E4%BC%A0%E9%80%92%E2%80%9D%E3%80%91.md)


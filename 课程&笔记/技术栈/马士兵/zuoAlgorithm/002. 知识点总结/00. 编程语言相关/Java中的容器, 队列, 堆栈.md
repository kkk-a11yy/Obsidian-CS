# Java中的容器, 队列, 堆,  栈

---



ArrayList: 用作数组

## 队列 Queue
没有叫做Queue的类（它是个接口名字）
Queue只是一个接口，当需要使用队列时也就首选ArrayDeque了（次选是LinkedList）

LinkedList: 双向链表-->双端队列

```java
LinkedList<Node> queue = new LinkedList<>();

```

## 栈: Stack
当需要使用栈时，Java已不推荐使用Stack，而是推荐使用更高效的ArrayDeque

```java
Stack<Integer> stack = new Stack<>();


Deque<Integer> stack = new ArrayDeque<Integer>();
```


[[Java中的Stack结构]]



## 堆

优先队列 - PriorityQueue
如果不提供Comparator的话，优先队列中元素默认按自然顺序排列，也就是数字默认是小的在队列头，字符串则按字典序排列。
如果需要大顶堆, 需要定义比较器


## String 转为 char

使用 String.toCharArray( ) 方法，将String 转化为 字符串数组。(返回值：char[] ) 

char 转为 String:  
String s = String.valueOf('c');



提醒！！！ 

如果大黄蜂播放器网校不是平凡之路、大飞机课堂，说明是翻录的，认准一手添加微信：meetjava 

如果大黄蜂播放器网校不是平凡之路、大飞机课堂，说明是翻录的，认准一手添加微信：meetjava 

如果大黄蜂播放器网校不是平凡之路、大飞机课堂，说明是翻录的，认准一手添加微信：meetjava 

另外，高价回收课程 

回收一切正版课程，买过任何正版课程的可以联系，支持换课，换VIP，或代下载，回收 

回收一切正版课程，买过任何正版课程的可以联系，支持换课，换VIP，或代下载，回收 

回收一切正版课程，买过任何正版课程的可以联系，支持换课，换VIP，或代下载，回收 

收藏下面学习目录链接，学课永不迷路，点击获取全网it目录 

https://www.yuque.com/javadd/itcourse/list 

微信：meetjava，认准一手，学习无忧，全网it课程都有 

微信：meetjava，认准一手，学习无忧，全网it课程都有 

重磅，收代理 冲冲冲 




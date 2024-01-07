
# Java中HashMap, TreeMap 等的元素遍历顺序

---

遍历HashMap里面的元素时, 得到的元素不是按照之前加入HashMap的顺序输出
```java
Map<String, String> hashMap = new HashMap<String, String>();

for (Entry<String, String> entry : hashMap.entrySet()) {
    MessageFormat.format("{0}={1}", entry.getKey(),entry.getValue()); 
}
```


**HashMap散列图、Hashtable散列表是按“有利于随机查找的散列(hash)的顺序”。并非按输入顺序。遍历时只能全部输出，而没有顺序**。甚至可以rehash()重新散列，来获得更利于随机存取的内部顺序。

总之，遍历HashMap或Hashtable时不要求顺序输出，即与顺序无关。

## 按加入时的顺序遍历
可以用**java.util.LinkedHashMap** 就是按加入时的顺序遍历了。

`Map<String, String> paramMap = new LinkedHashMap <String, String>();`

类似的还有 **java.util.LinkedHashSet**

## 按加入元素顺序遍历
如果想要得到的元素排序应该使用TreeMap  
`public TreeMap<String, Node> nextMap = new TreeMap<>();`





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
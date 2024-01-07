# Trie数 or 前缀树 or 字典树

#前缀树 
#Trie


---
- [[字母表实现前缀树]]
- [[哈希表实现前缀树]]


## 题目

## 经典前缀树


### 改写的前缀树

前缀树上每条路放的是字符串, 不是经典前缀树中的字符
- [[打印目录结构]]

```java
public static class Node {  
   // 上一个节点是通过哪条路，到我的  
 public String path;  
   // key : node下级的路 value：node在key这条路上对应的节点是什么  
 public TreeMap<String, Node> nextMap;  
     
   public Node(String p) {  
      this.path = p;  
      nextMap = new TreeMap<>();  
   }  
}


```



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
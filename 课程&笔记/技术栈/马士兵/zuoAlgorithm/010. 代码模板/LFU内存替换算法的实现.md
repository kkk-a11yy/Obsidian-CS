# LFU内存替换算法的实现


#LFU
#SuperHard 

难度不在于算法上的设计, 难度在于Coding

---

一个缓存结构需要实现如下功能  
```text
void set(int key, int value): 加入或修改key对应的value
int get(int key)            : 查询key对应的value值
```
但是缓存中最多放K条记录，如果新的第K+1条记录要加入，就需要根据策略删掉一条记录，然后才能把新记录加入。   
这个策略为:  
在缓存结构的K条记录中，哪一个key从进入缓存结构的时刻开始，被调用set或者get的次数最少，就删掉这个key的记录;  
如果调用次数最少的key有多个，上次调用发生最早的key被删除。  
这就是LFU缓存替换算法。实现这个结构，K作为参数给出。  

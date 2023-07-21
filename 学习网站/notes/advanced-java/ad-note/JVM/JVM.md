#JVM

压栈出栈： 活动栈帧    数据一致  

局部变量表：  32 slot    索引 this 

操作数栈： 顶-寄存器 栈深

方法调用： 静态：编译    符号-直接       ； 动态

方法绑定：早晚  

方法重写： 操作数栈顶 类型 访问权限 illegal 直接引用 父类 abstract

虚拟机栈：栈帧 SOF OOM 线程私有 

本地方法栈：C  栈帧 SOF OOM

堆 ：对象  共享  VM启动  GC: YOUNG1 EDft空 OLD2  8:1:1   连续   OOM

对象分配：堆 edge minorGc(suirv  0 1 ) 15 odl maxTurning     

Full/major GC : sys.gc   STW  MM

逃逸分析： 标量替换 -外界     hotspot  方法线程

TLAB：同步 枷锁

引用：强 ：new  null   软 ：不足 gc  弱：gc  虚

堆--方法区：类 常量  静变 编译代码

共享 永久 gc

运行时常量池： 

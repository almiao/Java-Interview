作者：vouv
链接：https://www.nowcoder.com/discuss/486577
来源：牛客网


        1. 自我介绍
        2. 简历项目
        3. Java
        - 3.1 Java中实现加锁的方式、sychronized、锁升级过程、底层AQS实现原理
        - 3.2 平时如何实现线程安全，ConcurrentHashMap
        - 3.3 线程状态、线程池有哪些参数、运行机制、四种拒绝策略
        4. 计网
        - 4.1 四次挥手过程、Close wait作用、第23次挥手能不能合并
        - 4.2 HTTP GET和POST区别
        5. 数据库
        - 5.1 数据库索引结构、聚簇索引和非聚簇索引区别、B+树结构、为什么不用B树或二叉树
        - 5.2 事务四大特性、事务隔离级别以及分别解决什么问题
        - 5.3 幻读、如何解决幻读
        6. 手撕算法
        - 6.1 面试题 10.03. 搜索旋转数组

    
***Java中实现加锁的方式、sychronized、锁升级过程、底层AQS实现原理***
    
参考：  

https://blog.csdn.net/u010842515/article/details/67634813  

https://blog.csdn.net/Javazhoumou/article/details/98866734
    
    
    Java多线程可以通过：1. synchronized关键字 2. Java.util.concurrent包中的lock接口和ReentrantLock实现类这两种方式实现加锁。
    
    sychronized实现原理：synchronized用的锁存在Java对象头里，Java对象头里的Mark Word默认存储对象的HashCode、分代年龄和锁标记位。
    在运行期间，Mark Word里存储的数据会随着锁标志位的变化而变化。32位JVM的Mark Word可能变化存储为以下5种数据：
    
    
#### Mysql RC 问题

![RUC-RC问题](https://ws3.sinaimg.cn/large/006tKfTcly1g1lwzkcjg7j312d0u0nam.jpg)


#### Mysql RR 问题

![RR问题](https://ws1.sinaimg.cn/large/006tKfTcly1g1lwz9jj30j311h0u0qhi.jpg)



#### RC 解决脏读过程

![RC解决脏读](https://ws3.sinaimg.cn/large/006tKfTcly1g1lwzy6f0sj31510u01kx.jpg)


#### RR解决 不可重复读 及 解决幻读过程

![RR解决不可重复读和幻读](https://ws3.sinaimg.cn/large/006tKfTcly1g1lx19t1mfj313l0u0ayz.jpg)

#### 思考

1,接上图

```
#事务ID=5 再次执行下述语句,结果是啥? 为啥?
start transaction;
select * from  soosoogoo_mvcc where user_id =1;
commit;
```

2,事如果还有事务ID=6,7,8,9,10… 呢,有多少版本,事务快照怎么删除和回收?开销大的原因

![RR下疑问](https://ws1.sinaimg.cn/large/006tKfTcly1g1lx1nzwl9j31100a4gpb.jpg)


3,RR下为什么 select xxx ==where id = 1== 和  update xxx ==where id = 1==  产生的结果不一致? (MVCC)
```
https://dev.mysql.com/doc/refman/5.6/en/innodb-consistent-read.html
```
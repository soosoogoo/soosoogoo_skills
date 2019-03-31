#### Mysql RC 问题

![图片.png](http://note.youdao.com/yws/res/13896/WEBRESOURCE21c829c33571bbf488bf38a28d547c31)


#### Mysql RR 问题

![rr问题.png](http://note.youdao.com/yws/res/13909/WEBRESOURCE7f844ebad3f408af88ec3ce4eec60775)



#### RC 解决脏读过程

![rc解决脏读.png](http://note.youdao.com/yws/res/13913/WEBRESOURCEea8ca6f2e4ce7fcbb0e3d8d9f203ab36)


#### RR解决 不可重复读 及 解决幻读过程

![rr解决不可重复读和幻读.png](http://note.youdao.com/yws/res/13920/WEBRESOURCE4a4b30fab5abaf78d780e41c0cf7f8b8)



#### 思考

1,接上图

```
#事务ID=5 再次执行下述语句,结果是啥? 为啥?
start transaction;
select * from  soosoogoo_mvcc where user_id =1;
commit;
```

2,事如果还有事务ID=6,7,8,9,10… 呢,有多少版本,事务快照怎么删除和回收?开销大的原因

![rr下疑问.png](http://note.youdao.com/yws/res/13933/WEBRESOURCE9a49eda3b6a855fb85948c4519b52397)


3,RR下为什么 select xxx ==where id = 1== 和  update xxx ==where id = 1==  产生的结果不一致? (MVCC)
```
https://dev.mysql.com/doc/refman/5.6/en/innodb-consistent-read.html
```
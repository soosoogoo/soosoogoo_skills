官方文档
> https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html

社区文章
> https://www.geek-share.com/detail/2752692802.html

#### InnoDB有三种行锁的算法：



锁类型 | 适用场景 | 解决问题
---|---|---
Record Lock 记录锁 |读提交(Read Committed)
Gap Lock 间隙锁 | 可重复读(Repeated Read)
Next-key Lock (记录锁 + 间隙锁) | 可重复读(Repeated Read) | ==解决幻读==


快照度
```
SELECT * FROM table_name WHERE ...;
```

当前读  , 显示加锁方法
```
#共享锁（S）
SELECT * FROM table_name WHERE ... LOCK IN SHARE MODE;
#排他锁（X）
SELECT * FROM table_name WHERE ... FOR UPDATE;
```
自动加锁
```
#X锁
UPDATE table_name SET xxxx WHERE …
INSERT INTO table_name ….  
DELETE FROM table_name  WHERE  …
```


查看当前锁
```
select * from information_schema.INNODB_TRX; #查看事务情况

select * from information_schema.INNODB_LOCKS; #查看锁情况

select * from information_schema.INNODB_LOCK_WAITS; #查看锁等待情况
```


#### 敲重点1: innoDB上层确定锁类型(S,X)后, inndb 通过==行锁算法==对指定行加锁
#### 敲重点2: InnoDB在RR级别下默认使用 next-key Lock


创建一个表,供后续食用
```
CREATE TABLE `soosoogoo_lock` (
  `id` int(11) DEFAULT NULL,
  `name` varchar(10) DEFAULT NULL,
  KEY `name` (`name`),
  KEY `index_name` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1


##插入数据
INSERT INTO `soosoogoo_lock` (`id`, `name`)
VALUES
	(2, '2'),(5, '3'),(10, '4'),(15, '5'),(20, '4'),(24, '4'),(27, '4'),(30, '4'),(35, '4');
	

set autocommit=0;

```



### Record Lock - 记录锁
> 单个行记录上的锁
```
select * from soosoogoo_lock where id = 5 for update;
```
![记录锁.png](http://note.youdao.com/yws/res/13169/WEBRESOURCE7ed6d041bc708108e8f92bb8dca8ca21)


### Gap Lock - 间隙锁
> 间隙锁，锁定一个范围，但不包括记录本身。GAP锁的目的，是为了防止同一事务的两次当前读，出现幻读的情况。

![间隙锁.png](http://note.youdao.com/yws/res/13166/WEBRESOURCEe4efffc31ff10d4f9badee6688c44f1a)

### Next-key Lock (间隙锁+记录锁)


![nextkeylock.png](http://note.youdao.com/yws/res/13177/WEBRESOURCEce9b4318be88f118741d8947d7bcc527)






疑问1:
```
begin;
select  * from  soosoogoo_lock  where id = 10 for update;


#然后 session2 执行
INSERT INTO `soosoogoo_lock` (`id`, `name`) VALUES (5, '2');  

# 返回 失败

#但是 
update soosoogoo_lock set name = 3 where id = 5; 
#确是成功  
```


疑问2:

```
select * from soosoogoo_lock where id >10 for update;

会锁全表


select * from soosoogoo_lock where id <10 for update;

会锁住 10
```


结构以及数据如下:
```
CREATE TABLE `soosoogoo_lock` (
  `id` int(11) DEFAULT NULL,
  `name` varchar(10) DEFAULT NULL,
  KEY `index_name` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1


INSERT INTO `soosoogoo_lock` (`id`, `name`)
VALUES
	(2, '2'),(3, '2'),	(5, '3'),	(10, '4'),	(15, '3'),	(20, '4'),(24, '4'),	(27, '4'),	(30, '4'),	(35, '4');

```

### 事务4要素 ACID





    | atomicity<br/>(原子性)  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | 一个事务必须被视为一个不可分割的最小工作单元，整个事务中的所有操作要么全部提交成功，<br/>要么全部失败回滚，对于一个事务来说，不可能只执行其中的一部分操作，这就是事务的原子性。 |
    | :----------------------------------------------------------- | :----------------------------------------------------------- |
    | **consistency<br/>(一致性)**                                 | 数据库总是从一个一致性的状态转换到另外一个一致性的状态。在前面的例子中，一致性确保了，<br/>即使在执行第三、四条语句之间时系统崩溃，支票账户中也不会损失200美元，因为事务最终没有提交，<br/>所以事务中所做的修改也不会保存到数据库中。<br/> |
    | **isolation<br/>(隔离性)**                                   | 通常来说，一个事务所做的修改在最终提交以前，对其他事务是不可见的。<br/>在前面的例子中，当执行完第三条语句、第四条语句还未开始时，<br/>此时有另外一个账户汇总程序开始运行，则其看到的支票账户的余额并没有被减去200美元。<br/>后面我们讨论隔离级别（Isolation level）的时候，会发现为什么我们要说“通常来说”是不可见的<br/> |
    | **durability<br/>(持久性)**                                  | 一旦事务提交，则其所做的修改就会永久保存到数据库中。此时即使系统崩溃，修改的数据也不会丢失。<br/>持久性是个有点模糊的概念，因为实际上持久性也分很多不同的级别。 |
    > 手册:https://dev.mysql.com/doc/refman/8.0/en/mysql-acid.html

    > 手册:https://dev.mysql.com/doc/refman/8.0/en/glossary.html#ACID

    <br/>

    ### 事务隔离级别(isolation level)
    | 名称                                          | 脏读 | 不可重复读 | 幻读 | 加锁读 |
    | :-------------------------------------------- | ---- | ---------- | ---- | ------ |
    | 读  - 未提交 Read Uncommit  (别名: 快照读)    | Y    | Y          | Y    | N      |
    | 读 - 已提交 Read Commit <br>(别名:不可重复读) | N    | Y          | Y    | N      |
    | 可重复读 Repeatable  Read                     | N    | N          | Y    | N      |
    | 串行化                                        | N    | N          | N    | Y?     |


    > 手册:https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html

    <br/>

    ### 事务日志

    | 事务日志 | 说明                                         |
    | -------- | -------------------------------------------- |
    | redo log | redo log buffer , redo log file 事务提交日志 |
    | undo log | 事务回滚日志                                 |


    ##### 对事务日志,以及binlog 感兴趣的同学可以参考 :

    > undo官方手册 : https://dev.mysql.com/doc/refman/8.0/en/innodb-redo-log.html

    > redo 官方手册 : https://dev.mysql.com/doc/refman/8.0/en/innodb-undo-logs.html

    > 博客:
    > https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html#auto_id_16


    <br/>

    ### 事务操作

    | 名称     | 操作                      |
    | -------- | ------------------------- |
    | 开启事务 | begin;/start transaction; |
    | 事务结束 |                           |
    | 提交事务 | commit;                   |
    | 回滚事务 | rollback                  |

    > 手册: <https://dev.mysql.com/doc/refman/8.0/en/innodb-autocommit-commit-rollback.html>

    <br/>

    ### 常用操作

    ```
    #设置隔离级别
    SET TRANSACTION ISOLATION LEVEL READ COMMITTED；
    SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITTED；


    #设置全局隔离级别
    SET GLOBAL TRANSACTION ISOLATION LEVEL READ COMMITTED；

    #查看隔离级别
    SELECT @@tx_isolation;
    ```




### Mysql 基本原理 

> 逐步更新中

![图片.png](http://note.youdao.com/yws/res/13328/WEBRESOURCE26b0dd83cf4f65f27c0eb741eb6dd3e6)



> 如果没有特殊需求 , 请务必使用InnoDB


##### 常见索引说明


| **Feature** (特征)                | **MyISAM**   | **Memory**       | **InnoDB**   | **Archive**  | **NDB**      |
| --------------------------------- | ------------ | ---------------- | ------------ | ------------ | :----------- |
| **B-tree indexes** (B树)          | Yes          | Yes              | Yes          | No           | No           |
| **备份/指定时间点恢复**(note 1)   | Yes          | Yes              | Yes          | Yes          | Yes          |
| **集群支持**                      | No           | No               | No           | No           | Yes          |
| **Clustered indexes**(聚簇索引)   | No           | No               | Yes          | No           | No           |
| **压缩数据**                      | Yes (note 2) | No               | Yes          | Yes          | No           |
| **数据缓存**                      | No           | N/A              | Yes          | No           | Yes          |
| **Encrypted data**(加密数据)      | Yes (note 3) | Yes (note 3)     | Yes (note 4) | Yes (note 3) | Yes (note 3) |
| **Foreign key support**(外键索引) | No           | No               | Yes          | No           | Yes (note 5) |
| **全文索引**                      | Yes          | No               | Yes (note 6) | No           | No           |
| **地理空间数据类型支持**          | Yes          | No               | Yes          | Yes          | Yes          |
| **地理空间索引支持**              | Yes          | No               | Yes (note 7) | No           | No           |
| **Hash indexes**(Hash索引)        | No           | Yes              | No (note 8)  | No           | Yes          |
| **Index caches**(Hash缓存)        | Yes          | N/A              | Yes          | No           | Yes          |
| **锁定粒度**                      | Table        | Table            | Row          | Row          | Row          |
| **MVCC**(多版本并发控制)          | No           | No               | Yes          | No           | No           |
| **复制支持** note 1               | Yes          | Limited (note 9) | Yes          | Yes          | Yes          |
| **Storage limits**(存储限制)      | 256TB        | RAM              | 64TB         | None         | 384EB        |
| **T-tree indexes**(T树索引)       | No           | No               | No           | No           | Yes          |
| **Transactions**(事务)            | No           | No               | Yes          | No           | Yes          |
| **更新数据字典**                  | Yes          | Yes              | Yes          | Yes          | Yes          |


note:
```
1.在服务器中实现，而不是在存储引擎中实现。

2.仅在使用压缩行格式时才支持压缩的MyISAM表。使用带MyISAM的压缩行格式的表是只读的。

3.通过加密功能在服务器中实现。

4.通过加密功能在服务器中实现; 在MySQL 5.7及更高版本中，支持数据静态表空间加密。

5. MySQL Cluster NDB 7.3及更高版本支持外键。

6. MySQL 5.6及更高版本中提供了InnoDB对FULLTEXT索引的支持。

7. MySQL 5.7及更高版本中提供了InnoDB对地理空间索引的支持。

8. InnoDB在内部利用哈希索引来实现其自适应哈希索引功能。

9.请参阅本节后面的讨论。
```



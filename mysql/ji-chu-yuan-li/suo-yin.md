##### Mysql最常用的两种引擎的索引结构


#### B+Tree 简单说明

```
http://note.youdao.com/noteshare?id=8045be159e4d7422709ef6a656382d82
```

#### B+Tree 和 BTree简单对比

```
http://note.youdao.com/noteshare?id=8045be159e4d7422709ef6a656382d82
```


#### 推荐资料

```
http://note.youdao.com/noteshare?id=58c6f82f1ff91efc60cda291243232c8
```


##### MyIASM索引结构  B+Tree

![20170920132633099.png](http://note.youdao.com/yws/res/12938/WEBRESOURCE295db2ab7cc84f5bd5f1c0826d2dcf75)


> MyIASM采用B+Tree作为索引结构,其中Col1为主键，
> 但是B+tree中叶子节点存储的是数据的>>>内存地址<<<，而不是具体的数据，数据与索引的分开。



如果以Col2为二级索引，他的组织形式：


![v2-8568bfd3f65cd449d13ec646b275edc3_hd.jpg](http://note.youdao.com/yws/res/12964/WEBRESOURCE541116b012293e3bd4e522c9c7312c07)



#### Innodb索引结构


##### 主键索引
![20170920132729406.png](http://note.youdao.com/yws/res/12969/WEBRESOURCEb8f73e12e71e65270a73eb93e1f1afd8)


##### 常规索引


![v2-4fe780f84512b569eea67da930ad1e4e_hd.jpg](http://note.youdao.com/yws/res/12974/WEBRESOURCEb7be969e980bb7248f9ab87074793b62)




#### 可以看出,当 innoDB使用主键索引的时候, 速度是和 MyIASM 一样的, 
#### ==但是 当使用的普通索引的时候,  普通索引的 B+Tree储存的是 主键 ID,==
#### ==会进行第二次搜索, 所以速度回比MyIASM 慢一丢丢==

添加索引

```
1.添加主键索引 
ALTER TABLE `table_name` ADD PRIMARY KEY (`column`) 

2.添加唯一索引
ALTER TABLE `table_name` ADD UNIQUE (`column`) 
3.添加全文索引
ALTER TABLE `table_name` ADD FULLTEXT (`column`) 

4.添加普通索引
ALTER TABLE `table_name` ADD INDEX index_name (`column` ) 
5.添加组合索引 
ALTER TABLE `table_name` ADD INDEX index_name (`column1`, `column2`, `column3`)
```








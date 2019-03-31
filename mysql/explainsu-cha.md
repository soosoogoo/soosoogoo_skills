**官方手册地址** [http://www.searchdoc.cn/rdbms/mysql/dev.mysql.com/doc/refman/5.7/en/explain-output.com.coder114.cn.html](http://www.searchdoc.cn/rdbms/mysql/dev.mysql.com/doc/refman/5.7/en/explain-output.com.coder114.cn.html)

列 \| json name \| 说明

---\|---\|--

id \| select\_id \| 查询标识符

select\_type \| None \| 查询类型

table \| table\_name \| 查询表的名称

partitions \| partitions \| 匹配的分区

type \| access\_type \| 链接类型

possible\_keys \| possible\_keys \| 可能使用的索引

key \| key \| 最终使用的索引

key\_len \| key\_length \| 所选键的长度

ref \| ref \| 列与索引进行比较

rows \| rows    \| 估计要检查的行

filtered \| filtered    \| 表条件过滤的行的百分比

Extra \| none \| 附加信息

\#\#\#\# TYPE含义

值 \| 说明

---\|---\|--

system \| 该表只有一行（=系统表）。这是const连接类型的特例

const \| 该表至多有一个匹配的行，在查询开始时读取。&lt;br&gt;由于只有一行，因此该行中列的值可以被优化器的其余部分视为常量。&lt;br&gt; const表格非常快，因为它们只读一次。

eq\_ref \| 从这个表读取一行，对于前面的表中的每一行的组合。&lt;br&gt;除了 system和 const类型，这是最好的连接类型。&lt;br&gt;当连接使用索引的所有部分并且索引是a PRIMARY KEY或UNIQUE NOT NULL索引时使用它。

ref \| 所有具有匹配索引值的行都从这个表中读取，&lt;br&gt;用于以前表中的每个行的组合。ref如果连接只使用键的最左边的前缀，&lt;br&gt;或者如果键不是a PRIMARY KEY或 UNIQUE索引&lt;br&gt;（换句话说，如果连接不能基于键值选择单个行），则使用该键。&lt;br&gt;如果使用的键只匹配几行，这是一个很好的连接类型。

fulltext \| 连接使用FULLTEXT 索引执行。

ref\_or\_null \| 这种连接类型就像 ref，但是另外MySQL对包含NULL值的行进行额外的搜索。&lt;br&gt;这种连接类型优化最常用于解析子查询。

index\_merge \| 此连接类型表示使用索引合并优化\[详情\]\([http://www.searchdoc.cn/rdbms/mysql/dev.mysql.com/doc/refman/5.7/en/index-merge-optimization.com.coder114.cn.html\](http://www.searchdoc.cn/rdbms/mysql/dev.mysql.com/doc/refman/5.7/en/index-merge-optimization.com.coder114.cn.html\)\)

index\_subquery \| 在 某 些 IN 查 询 中 使 用 此 种 类 型 ,&lt;br&gt; 与 unique\_subquery 类似,但是查询的是非唯一 性索引:&lt;br&gt; value IN \(SELECT key\_column FROM single\_table WHERE some\_expr\)

range \| 扫描给定范围 例如:&lt;br&gt; =， &lt;&gt;， &gt;， &gt;=， &lt;， &lt;=， IS NULL， &lt;=&gt;， BETWEEN，或 IN\(\)

index \| 使用默认主键索引,如果where 有指定其他索引&lt;br&gt; 则表示没有生效

ALL \| 扫全表  最差


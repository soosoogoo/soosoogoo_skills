文档
https://petl.readthedocs.io/en/stable/transform.html#transforming-rows



> 能方便的转换 字段 以及 清洗 

```python
import pymysql
import petl as etl

#
# 'host' => 'xxx',
# 'username' => 'xxx',
# 'password' => 'xxx',
# 'db' => 'xxx',
# 'port' => xxx,
# 'charset' => 'utf8',

conn = pymysql.connect(
    host='xxx',
    port=xxx,
    user='xxx',
    passwd='xxx',
    db='xxx',
    charset='utf8',
)

cur = conn.cursor()
cur.execute('SELECT * FROM `trust_done`   LIMIT 0,50;')
#  获取所有数据
dbs = cur.fetchall()
# for db_info in dbs:
#     print(db_info)


table1 = dbs
table2 = etl.tail(table1,4)
print(table2)

for col in table2:
    print(col)
    
input()
```



### 结果如下:



![image-20190413233615639](https://ws2.sinaimg.cn/large/006tNc79ly1g21fj8pul7j32eq0gmtit.jpg)







```python
import pymysql
import petl as etl
from collections import OrderedDict

#
# 'host' => 'bitz-8070cc54.cn-hongkong-b.ads.aliyuncs.com',
# 'username' => 'LTAIgbCuHK05Njkz',
# 'password' => 'YP5ZNdYQQbiBH2XTp8aLxXpthbuY1N',
# 'db' => 'bitz',
# 'port' => 10004,
# 'charset' => 'utf8',

conn = pymysql.connect(
    host='bitz-8070cc54.cn-hongkong-b.ads.aliyuncs.com',
    port=10004,
    user='LTAIgbCuHK05Njkz',
    passwd='YP5ZNdYQQbiBH2XTp8aLxXpthbuY1N',
    db='bitz',
    charset='utf8',
)

# cur = conn.cursor()
# cur.execute('SELECT * FROM `trust_done`   LIMIT 0,50;')
# #  获取所有数据
# dbs = cur.fetchall()
# for db_info in dbs:
#     print(db_info)


table2 = etl.fromdb(conn,'SELECT * FROM `trust_done`   LIMIT 0,50;')
print(table2)

# for col in table2:
#     print(col)


mappings = OrderedDict()
mappings['tuid'] = 'uid'

table3 = etl.fieldmap(table2, mappings)

print(table3)
input()
```





### 结果如下





![image-20190415105335130](https://ws2.sinaimg.cn/large/006tNc79ly1g234qaytxrj319u0gmado.jpg)
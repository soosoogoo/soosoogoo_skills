## 问题1

> 
>
> Warning: /opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop/bin/../../accumulo does not exist! Accumulo imports will fail.
> Please set $ACCUMULO_HOME to the root of your Accumulo installation.



```
vim /opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop/bin/configure-sqoop
```



#### 解决方式

```shell
148 #if [ ! -d "${ACCUMULO_HOME}" ]; then
149 #  echo "Warning: $ACCUMULO_HOME does not exist! Accumulo imports will fail."
150 #  echo 'Please set $ACCUMULO_HOME to the root of your Accumulo installation.'
151 #fi
```



## 问题2

### 

>  ERROR manager.CatalogQueryManager: Failed to list tables
> com.mysql.cj.jdbc.exceptions.CommunicationsException: Communications link failure



#### 解决方式

检查  数据库连接,  此处是连接配置有误




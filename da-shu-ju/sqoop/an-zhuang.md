官方手册:<https://sqoop.apache.org/docs/1.4.6/SqoopUserGuide.html>

### 安装Sqoop

##### 安装 java jdk (见java)

##### 找到sqoop 目录

```shell
locate /bin/sqoop  
```



##### 复制connector到 sqoop

```shell
 cp  mysql-connector.jar /opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop


```

##### 将 sqoop 添加到path

```shell
vim /etc/profile

PATH="/usr/java/jdk1.8.0_141-cloudera/bin:/opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop/bin:$PATH"

source /etc/profile
```



##### 使用sqoop链接数据库

```shell
sqoop list-databases  --connect jdbc:mysql://rm-j6ct3738rs916u5k3.mysql.rds.aliyuncs.com:3306/bitz --username dev_user --password IC90MxENmPl6cKFi 
```









### 抽象命令

##### 创建一个文件

```shell
vim /usr/sqoop/test-db.s

#写入

# 导入还是导出
#import

# 链接方式
--connect
jdbc:mysql://rm-j6ct3738rs916u5k3.mysql.rds.aliyuncs.com:3306/bitz

# 用户名
--username
dev_user

# 密码
--password
IC90MxENmPl6cKFi
```



##### 然后执行如下命令 可以达到跟上述一样的效果:

```shell
sqoop  list-databases --options-file /usr/sqoop/conn.s 
```



> 此方式可以把公用配置,数据库参数 都抽象出来



   

 

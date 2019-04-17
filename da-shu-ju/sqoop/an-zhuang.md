官方手册:<https://sqoop.apache.org/docs/1.4.6/SqoopUserGuide.html>

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
sqoop import --connect jdbc:mysql://m-j6ct3738rs916u5k3.mysql.rds.aliyuncs.com:3306/bitz --username dev_user --password IC90MxENmPl6cKFi 
```





 

   

 

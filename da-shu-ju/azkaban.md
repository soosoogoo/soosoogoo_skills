官方文档 https://azkaban.github.io/



#### git 下载

```shell
git clone https://github.com/azkaban/azkaban.git
```



#### 只支持 java1.8

```
https://download.oracle.com/otn-pub/java/jdk/8u201-b09/42970487e3af4f5aa5bca3f542482c60/jdk-8u201-linux-x64.rpm?AuthParam=1555310423_61da8f95df0fd337a3472fb0f61c559f
```



#### 安装java 命令

Java 官方文档 : https://docs.oracle.com/en/java/javase/12/install/installation-jdk-linux-platforms.html#GUID-4907E1A6-7B4B-4E98-9DA5-BF2A4D01AA57

```shell
$ rpm -ivh jdk-12.interim.update.patch_linux-x64_bin.rpm
```



#### 修改PATH

```shell
vim /etc/profile

#添加
PATH="/usr/local/bitz/bin:/usr/local/bin:/opt/remi/php72/root/usr/bin:/usr/java/jdk1.8.0_201-amd64/bin:$PATH"

```



#### 安装

```
cd azkaban; ./gradlew build installDist
```





默认IP为 http://localhost:8081/

```shell
#查看默认密码
vim /data/azkaban/azkaban/azkaban-web-server/src/test/resources/azkaban-users.xml
```








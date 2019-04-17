#### 下载 jdk (只支持 java1.8)


```
https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
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




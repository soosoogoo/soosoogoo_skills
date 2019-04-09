### 参考文档

canal: https://github.com/alibaba/canal

canal wiki: https://github.com/alibaba/canal/wiki/QuickStart

canal client: https://github.com/CanalClient/canal-go





### 安装步骤



```shell
https://github.com/alibaba/canal/releases
选择 releases-deployer


mkdir /data/canal
cd /data/canal

#下载
wget https://github.com/alibaba/canal/releases/download/canal-1.1.2/canal.deployer-1.1.2.tar.gz

#解压
tar zxvf canal.deployer-1.1.2.tar.gz  -C /data/canal

```



### 常用命令

```shell
#启动
cd /data/canal && sh bin/startup.sh

#关闭
cd /data/canal && sh bin/stop.sh

#查看canal日志
tail -100 /data/canal/logs/canal/canal.log

#查看实例日志
tail -100 /data/canal/logs/example/example.log

#修改配置文件
vim /data/canal/conf/example/instance.properties

```


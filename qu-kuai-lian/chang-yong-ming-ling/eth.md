```
GETH操作大全
http://cw.hubwiz.com/card/c/geth-rpc-api/1/4/2/
```
利用防火墙 开控制黑白名单


### 启动eth  默认端口 30303

```shell
#此处要注意带上 eth,web3,admin,personal,net,否则 不能使用 geth rpc 的对应库函数
nohup  geth --rpc --datadir /data/.ethereum --rpcaddr 192.168.3.31 --rpcapi eth,web3,admin,personal,net &


nohup  geth --rpc --datadir /data/.ethereum --rpcaddr 0.0.0.0 --rpcapi eth,web3,admin,personal,net &

```

### 杀eth
```shell

 lsof -i:30303 | awk '{print $2}' | xargs  kill -9  &&  lsof -i:8545 | awk '{print $2}' | xargs  kill -9 
```


### 进入控制台

```shell

geth attach

#测试数据
geth --dev  
```

### 创建账号

```shell

personal.newAccount(\''.$password.'\')
```

### 获取账号列表

```shell

curl 192.168.3.31:8545 -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"personal_listAccounts","params":[],"id":1}'

```
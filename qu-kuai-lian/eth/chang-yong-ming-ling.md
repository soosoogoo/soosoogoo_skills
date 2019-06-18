info```
GETH操作大全
http://cw.hubwiz.com/card/c/geth-rpc-api/1/4/2/
```

### 启动eth

```
#此处要注意带上 eth,web3,admin,personal,net,否则 不能使用 geth rpc 的对应库函数
nohup  geth --rpc --datadir /data/.ethereum --rpcaddr 192.168.3.31 --rpcapi eth,web3,admin,personal,net &


```

### 进入控制台

```
geth attach

#测试数据
geth --dev  
```

### 创建账号

```
personal.newAccount(\''.$password.'\')
```

### 获取账号列表

```
curl 192.168.3.31:8545 -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"personal_listAccounts","params":[],"id":1}'

```
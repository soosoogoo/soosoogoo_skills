[区块浏览器](https://etherscan.io/ )   

[中文ETH爱好者入门](https://ethfans.org/wikis/wallet-mirror)

[ETH RPC文档](https://github.com/ethereum/wiki/wiki/JSON-RPC) 

[ETH RPC 中文文档](http://cw.hubwiz.com/card/c/ethereum-json-rpc-api/1/3/2/) 

[ETH gitbook 文档](https://ethereum.gitbooks.io/frontier-guide/content/ethereum.html)   

[GETH RPC 文档](http://cw.hubwiz.com/card/c/geth-rpc-api/1/4/6/)




```
GETH操作大全
http://cw.hubwiz.com/card/c/geth-rpc-api/1/4/2/
```

启动eth

```
#此处要注意带上 eth,web3,admin,personal,net,否则 不能使用 geth rpc 的对应库函数
nohup  geth --rpc --datadir /data/.ethereum --rpcaddr 192.168.3.31 --rpcapi eth,web3,admin,personal,net &


```

进入控制台

```
geth attach

#测试数据
geth --dev  
```

创建账号
```
personal.newAccount(\''.$password.'\')
```

获取账号列表

```
curl 192.168.3.31:8545 -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"personal_listAccounts","params":[],"id":1}'

```
**1.下载安装文件**

https://ethfans.org/wikis/Ethereum-Geth-Mirror 



**2.RPC文档**

https://github.com/ethereum/wiki/wiki/JSON-RPC 



**3.下载后进入目录,开始同步区块, 大约1到2天,默认端口为30303**

```
nohup ./geth  & 
```

\#同步过程当中,如果获取节点很慢 可以添加国内节点



**4.同步完步过后,以rpc方式启动 geth 启动参数如下**

| 参数名称      | 参数描述                                                     |
| ------------- | ------------------------------------------------------------ |
| datadir       | 设置当前区块链网络数据存放的位置                             |
| nodiscover    | 私有链地址，不会被网上看到                                   |
| console       | 启动命令行模式，可以在Geth中执行命令                         |
| identity      | 区块链的标示，用于标示目前网络的名字                         |
| rpc           | 开启rpc通道                                                  |
| rpcapi        | 要开放哪些rpc api                                            |
| rpccorsdomain | 允许能连接到你的节点执行rpc api的url，使用逗号分隔。*表示任何url都可以连接 |
| rpcaddr       | HTTP-RPC服务器接口地址，默认为localhost                      |
| rpcport       | HTTP-RPC服务器端口地址，默认为8545                           |
| networkid     | 网络标识，私有链取一个大于4的随意的值                        |



nohup  ./geth --rpc --rpcaddr 192.168.3.31 --rpcapi eth,web3,admin,personal,net &  



**5,参照测试RPC是否成功**

​     <https://ethereum.gitbooks.io/frontier-guide/content/rpc.html>  (官方文档)

​     <http://cw.hubwiz.com/card/c/ethereum-json-rpc-api/1/3/3/>  (中文文档)



```
curl 192.168.3.31:8545 -H "Content-Type: application/json" -X POST --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}' 
```




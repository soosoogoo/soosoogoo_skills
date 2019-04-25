omnicore是来bitcoin改的

参考资料
http://www.omnilayer.org/download.html
https://bitcoin.org/zh_CN/download



btc编译好的包:
https://bitcoin.org/bin/bitcoin-core-0.17.1/bitcoin-0.17.1-x86_64-linux-gnu.tar.gz



```
./bitcoind -daemon
```




usdt编译好的包:
https://bintray.com/artifact/download/omni/OmniBinaries/omnicore-0.4.0-x86_64-linux-gnu.tar.gz



默认配置文件

```shell
vim  /home//ops/.bitcoin/bitcoin.conf
```



```shell
server=1  
txindex=1 
rpcuser=soosoogoo
rpcpassword=weixin123
rpcallowip=127.0.0.1 
rpcport=8332
paytxfee=0.00001
minrelaytxfee=0.00001
datacarriersize=80
logtimestamps=1
omnidebug=tally  
omnidebug=packets
omnidebug=pending
```



启动

```
./omnicored -daemon
```



查看区块 (如果)

```shell
./omnicore-cli getinfo 
```

```shell
root@dev-lh-usdtwallet:/data/usdt/omnicore-0.4.0/bin# ./omnicore-cli getinfo 
{
  "version": 130200,
  "protocolversion": 70015,
  "walletversion": 130000,
  "balance": 0.00000000,
  "blocks": 219425,
  "timeoffset": 0,
  "connections": 8,
  "proxy": "",
  "difficulty": 2968775.332075074,
  "testnet": false,
  "keypoololdest": 1556118507,
  "keypoolsize": 100,
  "paytxfee": 0.00001000,
  "relayfee": 0.00001000,
  "errors": ""
}
```



如果 blocks 一直在变多 ,则说明在同步
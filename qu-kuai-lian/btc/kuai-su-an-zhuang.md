omnicore是来bitcoin改的

参考资料
http://www.omnilayer.org/download.html
https://bitcoin.org/zh_CN/download



btc编译好的包:
https://bitcoin.org/bin/bitcoin-core-0.17.1/bitcoin-0.17.1-x86_64-linux-gnu.tar.gz

./bitcoind -daemon






usdt编译好的包:
https://bintray.com/artifact/download/omni/OmniBinaries/omnicore-0.4.0-x86_64-linux-gnu.tar.gz




server=1  
txindex=1 
rpcuser=你的rpc用户名
rpcpassword=你的rpc密码
rpcallowip=127.0.0.1 
rpcport=8332
paytxfee=0.00001
minrelaytxfee=0.00001
datacarriersize=80
logtimestamps=1
omnidebug=tally  
omnidebug=packets
omnidebug=pending

作者：一叶行知
链接：https://www.jianshu.com/p/bd573e2df746
来源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
官方地址

<https://github.com/OmniLayer/omnicore>





安装libdb4

> <https://dl.fedoraproject.org/pub/epel/6/x86_64/Packages/l/>





### 官方推荐使用ubantu



### 安装omni

```shell
# BITCOIN_ROOT=$(pwd)
mkdir /data/usdt
git clone https://github.com/OmniLayer/omnicore.git

# Pick some path to install BDB to, here we create a directory within the bitcoin directory
#BDB_PREFIX="${BITCOIN_ROOT}/db4"
#mkdir -p $BDB_PREFIX
mkdir -p /data/usdt/db4

cd /data/usdt/db4
# Fetch the source and verify that it is not tampered with
wget 'http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz'
echo '12edc0df75bf9abd7f82f821795bcee50f42cb2e5f76a6a281b85732798364ef db-4.8.30.NC.tar.gz' | sha256sum -c
# -> db-4.8.30.NC.tar.gz: OK
tar -xzvf db-4.8.30.NC.tar.gz

# Build the library and install to our prefix
cd db-4.8.30.NC/build_unix/
# Note: Do a static build so that it can be embedded into the executable, instead of having to find a .so at runtime
../dist/configure --enable-cxx --disable-shared --with-pic --prefix=/data/usdt/db4
make install

# Configure Bitcoin Core to use our own-built instance of BDB
#cd $BITCOIN_ROOT
cd /data/usdt/omnicore/
./autogen.sh
./configure LDFLAGS="-L${/data/usdt/db4}/lib/" CPPFLAGS="-I${/data/usdt/db4}/include/" 
# (other args...)
```







```shell
mkdir /data/autoconf && cd /data/autoconf

wget ftp://ftp.gnu.org/gnu/autoconf/autoconf-2.68.tar.gz

tar zxvf autoconf-2.68.tar.gz
cd autoconf-2.68
./configure --prefix=/usr/
make && make install
```


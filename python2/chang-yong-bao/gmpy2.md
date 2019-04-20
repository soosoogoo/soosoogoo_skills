### Linux

> 安装要求:
> gmpy2仅使用最新版本的GMP，MPFR和MPC进行了测试。具体来说，对于整数和合理支持，gmpy2需要GMP 5.0.x或更高版本。要支持多精度浮点运算，需要MPFR 3.1.x或更高版本。复杂算术需要MPC 1.0.1或更高版本。
> https://gmpy2.readthedocs.io/en/latest/intro.html#requirements

```shell
#各自的官方下载地址
#mpfr https://www.mpfr.org/mpfr-current/#download
#m4 http://ftp.gnu.org/gnu/m4/
#gmp https://gmplib.org/download/gmp/
#mpc ftp://ftp.gnu.org/gnu/mpc


mkdir ~/install && cd ~/install

#编译gmp:
wget https://gmplib.org/download/gmp/gmp-6.1.2.tar.lz
yum install lzip -y
lzip -d gmp-6.1.2.tar.lz
tar xvf gmp-6.1.2.tar && cd gmp-6.1.2
./configure
make && make install

#编译mpfr:
cd ~/install
wget ftp://ftp.gnu.org/gnu/mpfr/mpfr-3.1.6.zip
unzip mpfr-3.1.6.zip && cd mpfr-3.1.6
./configure
make && make install

#编译mpc:
cd ~/install
wget http://ftp.gnu.org/gnu/mpc/mpc-1.1.0.tar.gz
tar zxvf mpc-1.1.0.tar.gz && cd mpc-1.1.0
./configure
make && make install

#加载lib位置:
sed -i '$a\/usr/local/lib' /etc/ld.so.conf

ldconfig

#安装gmpy2:
cd ~/install
wget https://files.pythonhosted.org/packages/90/f4/9a2e384b325b69bc5827b9a6510a8fb4a51698c915c06a3f25a86458892a/gmpy2-2.0.8.zip
unzip gmpy2-2.0.8.zip
cd gmpy2-2.0.8
python3.7 setup.py build
python3.7 setup.py install

验证:
python3.7 -c "import gmpy2"
```



### MacOS

#### 问题1:

> xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun



### 解决方式

```shell
xcode-select –install
```



参考文章:<https://www.jianshu.com/p/50b6771eb853>



#### 问题2



> src/gmpy.h:252:12: fatal error: 'mpfr.h' file not found



### 解决方式

```shell
brew install libmpc mpfr gmp
```





参考文章:

<https://github.com/OpenMined/PySyft/issues/125>

<https://github.com/iamtrask/PySonar/blob/master/README.md#base-libraries>




http://docs.peewee-orm.com/en/latest/peewee/quickstart.html#quickstart
 多版本共存的时候 : python -m pip 
 
 
 
https://pypi.org/project/setuptools/#files
 
 
 

yum install gcc libffi-devel python-devel openssl-devel


python2.7 -m pip  install  gevent









# yum install centos-release-SCL
# yum install scl-utils-build
# yum --disablerepo="*" --enablerepo="centos-sclo-rh" list
# yum install python27 -y

https://www.jianshu.com/p/36f5d3524240

yum install centos-release-scl -y
yum install devtoolset-7 -y
scl enable devtoolset-7 bash
gcc --version


注释：
在centos的devtoolset库中 最新的为 devtoolset-7，所以我们以后可以自己改数字安装最新的版本
scl enable devtoolset-7 bash 如果使用的是zsh则使用
scl enable devtoolset-7 zsh
如果不知道什么是zsh那么默认的就好了



https://www.jianshu.com/p/36f5d3524240
https://www.jianshu.com/p/b8792a7b5350
https://blog.51cto.com/wenguonideshou/2083301

https://www.python.org/ftp/python/3.7.3/
















http://ftp.gnu.org/gnu/m4/
https://gmplib.org/download/gmp/
https://www.mpfr.org/mpfr-current/



v=1.4.18
cd $HOME/src
wget http://ftp.gnu.org/gnu/m4/m4-${v}.tar.gz
tar xf m4-${v}.tar.gz && cd m4-${v}
./configure -prefix=/usr/local
make && make check && make install

v=4.0.1
cd $HOME/src
wget http://www.mpfr.org/mpfr-current/mpfr-${v}.tar.bz2
tar -jxvf mpfr-${v}.tar.bz2 && cd mpfr-${v}
./configure --prefix=$HOME/static --enable-static --disable-shared --with-pic --with-gmp=$HOME/static
make && make check && make install




v=4.0.1
cd $HOME/src
wget http://www.mpfr.org/mpfr-current/mpfr-${v}.tar.bz2
tar -jxvf mpfr-${v}.tar.bz2 && cd mpfr-${v}
./configure --prefix=$HOME/static --enable-static --disable-shared --with-pic --with-gmp=$HOME/static
make && make check && make install
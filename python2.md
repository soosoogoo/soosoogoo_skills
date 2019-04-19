 多版本共存的时候 : python -m pip 
 
 
 
 https://pypi.org/project/setuptools/#files
 
 
 
 centos
 sudo yum install python-devel
sudo yum install libevent-devel
easy_install gevent

yum install gmp-devel
yum install mpfr-devel
yum install libmpc-devel

yum install mpfr-devel
yum install gmpy

yum install gcc libffi-devel python-devel openssl-devel




wget http://people.centos.org/tru/devtools-2/devtools-2.repo
mv devtools-2.repo /etc/yum.repos.d
yum install devtoolset-2-gcc devtoolset-2-binutils devtoolset-2-gcc-c++


2、三个安装包(gcc/g++/c++)会被安装到，/opt/rh/devtoolset-2/root/目录中。然后我们创建一个软连接就可以使用了。


ln -s /opt/rh/devtoolset-2/root/usr/bin/gcc /usr/bin/gcc
ln -s /opt/rh/devtoolset-2/root/usr/bin/c++ /usr/bin/c++
ln -s /opt/rh/devtoolset-2/root/usr/bin/g++ /usr/bin/g++
gcc --version

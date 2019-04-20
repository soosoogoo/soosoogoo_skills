 ### 多版本共存的时候 : 

```shell
python -m pip 
```



### Python3.6

```shell
yum install epel-release -y

yum install https://centos6.iuscommunity.org/ius-release.rpm -y
yum install https://centos7.iuscommunity.org/ius-release.rpm -y

yum install  -y  python36u python36u-pip python36u-devel python36u-tools python36u-libs python36u-setuptools
```



### Python2.7

```shell
yum install centos-release-SCL
yum install scl-utils-build
yum --disablerepo="*" --enablerepo="centos-sclo-rh" list
yum install python27 -y
```



https://www.jianshu.com/p/36f5d3524240



### 升级GCC

```shell
yum install centos-release-scl -y
yum install devtoolset-7 -y
scl enable devtoolset-7 bash
gcc --version

#注释：
#在centos的devtoolset库中 最新的为 devtoolset-7，所以我们以后可以自己改数字安装最新的版本
#scl enable devtoolset-7 bash 如果使用的是zsh则使用
#scl enable devtoolset-7 zsh
#如果不知道什么是zsh那么默认的就好了
```



https://www.jianshu.com/p/36f5d3524240
https://www.jianshu.com/p/b8792a7b5350
https://blog.51cto.com/wenguonideshou/2083301

https://www.python.org/ftp/python/3.7.3/

https://pypi.org/project/setuptools/#files


http://ftp.gnu.org/gnu/m4/
https://gmplib.org/download/gmp/
https://www.mpfr.org/mpfr-current/



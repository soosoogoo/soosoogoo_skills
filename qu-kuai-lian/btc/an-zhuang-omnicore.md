官方地址

<https://github.com/OmniLayer/omnicore>





安装libdb4

> 如果是centos7  则把地址更换为 <https://dl.fedoraproject.org/pub/epel/7/>  即可







```
mkdir /home/libdb4
cd libdb4/
wget http://dl.fedoraproject.org/pub/epel/7/x86_64/Packages/l/libdb4-4.8.30-13.el7.x86_64.rpm
wget http://dl.fedoraproject.org/pub/epel/7/x86_64/Packages/l/libdb4-devel-4.8.30-13.el7.x86_64.rpm
wget http://dl.fedoraproject.org/pub/epel/7/x86_64/Packages/l/libdb4-cxx-4.8.30-13.el7.x86_64.rpm
wget http://dl.fedoraproject.org/pub/epel/7/x86_64/Packages/l/libdb4-cxx-devel-4.8.30-13.el7.x86_64.rpm

rpm -ivh libdb4-4.8.30-13.el7.x86_64.rpm
rpm -ivh libdb4-devel-4.8.30-13.el7.x86_64.rpm
rpm -ivh libdb4-cxx-4.8.30-13.el7.x86_64.rpm
rpm -ivh libdb4-cxx-devel-4.8.30-13.el7.x86_64.rpm

```


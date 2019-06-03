```
GRANT SELECT, INSERT, UPDATE,DELETE ON `smoney-main`.* TO 'xianhui'@'%' IDENTIFIED BY  '123123zsz';

GRANT SELECT, INSERT, UPDATE,DELETE ON `smoney-admin`.* TO 'xianhui'@'%';

GRANT SELECT, INSERT, UPDATE,DELETE ON `smoney-user`.* TO 'xianhui'@'%';

GRANT SELECT, INSERT, UPDATE,DELETE ON `smoney-wallet`.* TO 'xianhui'@'%';

```

修改密码

```
use mysql;
UPDATE user SET password=PASSWORD("123123123zsz") WHERE user='root'; 
FLUSH PRIVILEGES; 
```
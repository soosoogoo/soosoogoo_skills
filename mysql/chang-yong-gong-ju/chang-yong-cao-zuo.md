```
GRANT SELECT, INSERT, UPDATE,DELETE ON smoney-main.* TO 'username'@'%' IDENTIFIED BY  'passsword';

GRANT SELECT, INSERT, UPDATE,DELETE ON smoney-admin.* TO 'username'@'%';

GRANT SELECT, INSERT, UPDATE,DELETE ON smoney-user.* TO 'username'@'%';

GRANT SELECT, INSERT, UPDATE,DELETE ON smoney-wallet.* TO 'username'@'%';

```
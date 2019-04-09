###### slave_master_info

```javascript
SHOW command denied to user 'xxx'@'xxx' for table 'slave_master_info'
```



> 一般公有云 rds 会禁用  slave_master_info 权限



```javascript
#修改配置文件

vim  /data/cancal/conf/example/instance.properties 

# table regex  指定库命和标明即可, 详情见参数表
canal.instance.filter.regex=databaseName\\..*    
# table black regex
canal.instance.filter.black.regex=
```




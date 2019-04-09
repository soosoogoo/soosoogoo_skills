



参数说明



| 参数名字                           | 参数说明                                                     | 默认值         |
| ---------------------------------- | ------------------------------------------------------------ | -------------- |
| canal.instance.mysql.slaveId       | mysql集群配置中的serverId概念，需要保证和当前mysql集群中id唯一  (v1.1.x版本之后canal会自动生成，不需要手工指定) | 无             |
| canal.instance.master.address      | mysql主库链接地址                                            | 127.0.0.1:3306 |
| canal.instance.master.journal.name | mysql主库链接时起始的binlog文件                              | 无             |
| canal.instance.master.position     | mysql主库链接时起始的binlog偏移量                            | 无             |
| canal.instance.master.timestamp    | mysql主库链接时起始的binlog的时间戳                          | 无             |
| canal.instance.gtidon              | 是否启用mysql gtid的订阅模式                                 | false          |
| canal.instance.master.gtid         | mysql主库链接时对应的gtid位点                                | 无             |
| canal.instance.dbUsername          | mysql数据库帐号                                              | canal          |
| canal.instance.dbPassword          | mysql数据库密码                                              | canal          |
| canal.instance.defaultDatabaseName | mysql链接时默认schema                                        |                |
| canal.instance.connectionCharset   | mysql 数据解析编码                                           | UTF-8          |
| canal.instance.filter.regex        | mysql 数据解析关注的表，Perl正则表达式.多个正则之间以逗号(,)分隔，转义符需要双斜杠(\\) 常见例子：1.  所有表：.*   or  .*\\..* 2.  canal schema下所有表： canal\\..* 3.  canal下的以canal打头的表：canal\\.canal.* 4.  canal schema下的一张表：canal\\.test15.  多个规则组合使用：canal\\..*,mysql.test1,mysql.test2 (逗号分隔) | .*\\..*        |
| canal.instance.filter.black.regex  | mysql 数据解析表的黑名单，表达式规则见白名单的规则           | 无             |
| canal.instance.rds.instanceId      | aliyun rds对应的实例id信息(如果不需要在本地binlog超过18小时被清理后自动下载oss上的binlog，可以忽略该值) | 无             |
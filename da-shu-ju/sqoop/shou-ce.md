官方文档:https://sqoop.apache.org/docs/
参考资料
1.https://blog.csdn.net/dabokele/article/details/51868594

2.<https://www.jianshu.com/p/695c3bae42b3>

### 公共参数

<div id='publicParams'></div>

```shell
sqoop help
usage: sqoop COMMAND [ARGS]

Available commands:
  codegen            Generate code to interact with database records
  create-hive-table  Import a table definition into Hive
  eval               Evaluate a SQL statement and display the results
  export             Export an HDFS directory to a database table
  help               List available commands
  import             Import a table from a database to HDFS
  import-all-tables  Import tables from a database to HDFS
  import-mainframe   Import mainframe datasets to HDFS
  list-databases     List available databases on a server
  list-tables        List available tables in a database
  version            Display version information

See 'sqoop help COMMAND' for information on a specific command.
```





###  import-export-comm

<div id="import-comm"></div>



| 选项                                 | 说明                                   |
| ------------------------------------ | :------------------------------------- |
| --connect < jdbc-uri >               | 指定JDBC连接字符串                     |
| --connection-manager < class-name >  | 指定要使用的连接管理器类               |
| --driver < class-name >              | 指定要使用的JDBC驱动类                 |
| --hadoop-mapred-home < dir >         | 指定$HADOOP_MAPRED_HOME路径            |
| --help                               | 打印用法帮助信息                       |
| --password-file                      | 设置用于存放认证的密码信息文件的路径   |
| -P                                   | 从控制台读取输入的密码                 |
| --password < password >              | 设置认证密码                           |
| --username < username >              | 设置认证用户名                         |
| --verbose                            | 打印详细的运行信息                     |
| --connection-param-file < filename > | 可选，指定存储数据库连接参数的属性文件 |



### import-comm



| 参数                                                         | 说明                                                         |
| ------------------------------------------------------------ | :----------------------------------------------------------- |
| --connect                                                    | 连接RDBMS的jdbc连接字符串。<br /> 示例：--connect     jdbc:mysql:// MYSQL_SERVER: PORT / DBNAME <br />其中：mysql默认端口号为3306； 示例：--connect jdbc:oracle:thin:USERNAME/PASSWORD@ORACLE_SERVER:PORT: SID<br /> 其中：Oracle默认端口号为1521；<br /> thin：是驱动方式，“瘦”的意思，直接使用原生的Oracle JDBC驱动；<br /> SID：是一个数据库的唯一标识符，是建立一个数据库时系统自动赋予的一个初始ID。 |
| --username                                                   | 连接RDBMS所使用的用户名。                                    |
| --password                                                   | 连接RDBMS所使用的密码。                                      |
| --table                                                      | 将要导入到hive的表。                                         |
| --split-by                                                   | 分割导入任务所使用的字段。需要明确指定，推荐使用主键。       |
| --hive-import                                                | 插入数据到hive当中，使用hive默认的分隔符。                   |
| -m, --num-mappers< n>                                        | 使用n个map任务并行导入数据。<br />是指生成的map任务的总数量， 不是同时处于RUNNING状态的数量。 |
| --hive-database                                              | hive当中的数据库。                                           |
| -- hive-table                                                | hive当中的表名                                               |
| --hive-partition-key                                         | hive分区的列名 。                                            |
| --hive-partition-value                                       | hive分区的值。                                               |
| --columns <col ………….>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | 从表中导出指定的一组列的数据，用逗号分隔， oracle中列名需要大写。 |
| --warehouse-dir                                              | （必选）可以指定为-warehouse-dir/user/hive/warehouse/ <br />即导入数据的存放路径，如果该路径不存在，会首先创建。<br /> 在该路径下会生成和TABLE（--table）同名的文件夹，<br />该文件夹下存放数据文件。 <br />如果路径存在，需要保证该文件夹下不存在与TABLE(--table)同名文件。<br /> 如果不手动指定，默认是启动sqoop任务的用户的home目录。 |
| --direct                                                     | 使用快速模式导入                                             |
| --compress                                                   | 启用压缩，生成的文件为经过压缩的文件。 默认使用GZIP算法。<br /> 通过--compression-codec设置压缩算法。 通常当空间不够时可以使用压缩，<br />不过需要注意，如果压缩率过大可能导致CPU占用过高。 <br />如果可以，推荐使用snappy。 <br />另外，如果配置了mapreduce的“map输出压缩”， <br />那么即使不适用—compress开关， 导入的数据文件也会使用对应的codec进行压缩。 |
| --compression-codec                                          | 使用Hadoop Codec。（默认gzip）前提是设置了—cpmpress。        |
| 其他                                                         | 可使用 sqoop import 命令查看帮助。                           |



### import-control (导入控制参数)

<div id="import-control"></div>

| 选项                              | 说明                                                         |
| --------------------------------- | :----------------------------------------------------------- |
| --append                          | 将数据追加到HDFS上一个已存在的数据集上                       |
| --as-avrodatafile                 | 将数据导入到Avro数据文件                                     |
| --as-sequencefile                 | 将数据导入到SequenceFile                                     |
| --as-textfile                     | 将数据导入到普通文本文件（默认）                             |
| --boundary-query < statement >    | 边界查询，用于创建分片（InputSplit）                         |
| --columns < col,col,col…>         | 从表中导出指定的一组列的数据                                 |
| --delete-target-dir               | 如果指定目录存在，则先删除掉                                 |
| --direct                          | 使用直接导入模式（优化导入速度）                             |
| --direct-split-size < n >         | 分割输入stream的字节大小（在直接导入模式下）                 |
| --fetch-size < n >                | 从数据库中批量读取记录数                                     |
| --inline-lob-limit < n >          | 设置内联的LOB对象的大小                                      |
| -m,--num-mappers < n >            | 使用n个map任务并行导入数据                                   |
| -e,--query < statement >          | 导入的查询语句                                               |
| --split-by < column-name >        | 指定按照哪个列去分割数据                                     |
| --table < table-name >            | 导入的源表表名                                               |
| --target-dir < dir >              | 导入HDFS的目标路径                                           |
| --warehouse-dir < dir >           | HDFS存放表的根路径                                           |
| --where < where clause>           | 指定导出时所使用的查询条件                                   |
| -z,--compress                     | 启用压缩                                                     |
| --compression-codec < c >         | 指定Hadoop的codec方式（默认gzip）                            |
| --null-string < null-string >     | 如果指定列为字符串类型，使用指定字符串替换值为null的该类列的值 |
| --null-non-string < null-string > | 如果指定列为非字符串类型，使用指定字符串替换值为null的该类列的值 |






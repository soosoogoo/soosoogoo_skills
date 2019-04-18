官方文档:https://sqoop.apache.org/docs/
参考资料https://blog.csdn.net/dabokele/article/details/51868594



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





###  import-comm

<div id="import-comm"></div>

```shell
Argument	Description
--connect <jdbc-uri>	Specify JDBC connect string
--connection-manager <class-name>	Specify connection manager class to use
--driver <class-name>	Manually specify JDBC driver class to use
--hadoop-mapred-home <dir>	Override $HADOOP_MAPRED_HOME
--help	Print usage instructions
--password-file	Set path for a file containing the authentication password
-P	Read password from console
--password <password>	Set authentication password
--username <username>	Set authentication username
--verbose	Print more information while working
--connection-param-file <filename>	Optional properties file that provides connection parameters
--relaxed-isolation	Set connection transaction isolation to read uncommitted for the mappers.

```



### import-control

<div id="import-control"></div>

```
Argument	Description
--append	Append data to an existing dataset in HDFS
--as-avrodatafile	Imports data to Avro Data Files
--as-sequencefile	Imports data to SequenceFiles
--as-textfile	Imports data as plain text (default)
--as-parquetfile	Imports data to Parquet Files
--boundary-query <statement>	Boundary query to use for creating splits
--columns <col,col,col…>	Columns to import from table
--delete-target-dir	Delete the import target directory if it exists
--direct	Use direct connector if exists for the database
--fetch-size <n>	Number of entries to read from database at once.
--inline-lob-limit <n>	Set the maximum size for an inline LOB
-m,--num-mappers <n>	Use n map tasks to import in parallel
-e,--query <statement>	Import the results of statement.
--split-by <column-name>	Column of the table used to split work units. Cannot be used with --autoreset-to-one-mapper option.
--split-limit <n>	Upper Limit for each split size. This only applies to Integer and Date columns. For date or timestamp fields it is calculated in seconds.
--autoreset-to-one-mapper	Import should use one mapper if a table has no primary key and no split-by column is provided. Cannot be used with --split-by <col> option.
--table <table-name>	Table to read
--target-dir <dir>	HDFS destination dir
--temporary-rootdir <dir>	HDFS directory for temporary files created during import (overrides default "_sqoop")
--warehouse-dir <dir>	HDFS parent for table destination
--where <where clause>	WHERE clause to use during import
-z,--compress	Enable compression
--compression-codec <c>	Use Hadoop codec (default gzip)
--null-string <null-string>	The string to be written for a null value for string columns
--null-non-string <null-string>	The string to be written for a null value for non-string columns
```




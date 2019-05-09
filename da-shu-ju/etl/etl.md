#流水增量
0 */1 * * * sh /home/ops/import_incremental/ck_assets_flow_record-increase-load.sh
#盘口增量
0 */1 * * * sh /home/ops/import_incremental/pan_kou_increase.sh
#订单增量
0 */1 * * * sh /home/ops/import_incremental/order_done.sh
#0点5分 把表重新同步一遍  覆盖操作 冲提记录
5 0 * * * sh /home/ops/import2hive/import_exchange.sh >> /home/ops/import2hive/log/cron.log
##0点5分 把表重新同步一遍  覆盖操作  user 资产
5 0 * * * sh /home/ops/import2hive/import_user.sh >> /home/ops/import2hive/log/cron.log

##ETL 用户信息合并到一张表 app层
0 5 * * * sh /home/ops/hql/user_info.sh
##
##app层报表 app层

##盈亏
#盈亏算法
30 5 * * * sh /home/ops/al/profit_loss_day.sh
#盈亏快照 
30 5 * * * sh /home/ops/al/profit_loss_snapshot.sh
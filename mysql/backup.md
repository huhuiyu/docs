# mysql备份

- [返回](README.md)
  ***
- mysql主从备份  
  - 开启主库 binarylog  
  执行`vi /etc/my.cnf`打开 mysql 配置文件，在 mysqld 小节下面添加配置

  ```info
  log_bin=mysql-bin  
  server-id=1  
  binlog_do_db=要主从的数据库名称  
  binlog-ignore-db=不需要主从的数据库名称  
  ```

  执行`systemctl restart mysqld`重启 mysql  
  执行`show master status\G`查看主库日志状态记住 File 和 Position，从库需要这个
  - 开启从库 binarylog  
  执行`vi /etc/my.cnf`打开 mysql 配置文件，在 mysqld 小节下面添加配置  

  ```inf
  log_bin=mysql-bin  
  server-id=2  
  replicate_do_db=要主从的数据库名称  
  replicate-ignore-db=不需要主从的数据库名称  
  relay_log=relay_bin  
  log-slave-updates=ON
  ```

  执行`systemctl restart mysqld`重启 mysql  
  执行`CHANGE MASTER TO MASTER_HOST='主库ip', MASTER_USER='主库用户', MASTER_PASSWORD='主库密码', MASTER_LOG_FILE='上面主库查询的file', MASTER_LOG_POS=上面主库查询的position;`语句初始化从库同步状态  
  执行`show slave status\G`查看从库日志状态
  ***
- [返回](README.md)
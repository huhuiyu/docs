# centos安装mysql

- [返回](README.md)
  ***
- centos安装mysql  
  执行`wget https://repo.mysql.com//mysql57-community-release-el7-11.noarch.rpm`下载安装文件  
  执行`yum localinstall mysql57-community-release-el7-11.noarch.rpm`添加到本地安装源  
  执行`yum install mysql-community-server`安装mysql  
  执行`systemctl enable mysqld`配置mysql服务开机启动  
  执行`systemctl start mysqld`启动mysql  
  执行`grep 'temporary password' /var/log/mysqld.log`查看mysql的默认root密码  
  执行`mysql -uroot -p`启动命令行，密码就是上一步查看的  
  执行`ALTER USER 'root'@'localhost' IDENTIFIED BY '密码';`修改root默认密码，否则不能执行其它管理命令  
  执行`CREATE USER '用户名'@'%' IDENTIFIED BY '密码';`添加用户  
  执行`GRANT ALL ON *.* TO '用户名'@'%' with grant option;`用户授权  
  执行`FLUSH PRIVILEGES;`用户权限立即生效  
  现在可以用新用户登录了
  ***
- [返回](README.md)
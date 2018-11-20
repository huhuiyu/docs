# centos-知识点

- [返回目录](README.md)
- 基础部分
  - [用户管理](#用户管理)
  - [配置网络](#配置网络)
  - [安装 tmux](#安装-tmux)
  - [防火墙](#防火墙)
  - [ssh 登陆](#ssh-登陆)
  - [简单的 vi 指令](#简单的-vi-指令)
- 开发部分
  - [安装 jdk](#安装-jdk)
  - [安装 git](#安装-git)
  - [安装 mysql](#安装-mysql)
  - [安装 nginx](#安装-nginx)
  - [mysql 主从备份](#mysql-主从备份)

## 用户管理

- 执行`ls –l /home`查看用户列表
- 执行`userdel -rf username`删除 username 指定的用户
- 执行`adduser username`创建 username 指定的用户
- 执行`passwd username`修改用户 username 的密码
- 执行`su - username`可以切换到指定用户
- 执行`su -`可以切换到 root
- 执行`visudo`编辑 sudo 权限
- [返回目录](#centos-知识点)

## 配置网络

- 执行`nmcli connection show`查看网络列表
- 执行`systemctl restart network`重启网络服务
- 执行`nmtui`启动图形界面网络管理
- [返回目录](#centos-知识点)

## 安装-tmux

- 执行`yum install tmux`安装
- 执行`tmux`开启一个 tmux session
- 执行`tumx a`恢复到上次启动的 tmux session
- 执行`tmux ls`查看 tmux 全部 session
- 执行`tmux kill-session -t session名`关闭 session 名对应的 session
- 按键`Ctrl+b "`横向分割窗口
- 按键`Ctrl+b %`竖向分割窗口
- 按键`Ctrl+b 方向键`移动到指定方向的窗口
- 按键`Ctrl+d`关闭当前窗口
- [返回目录](#centos-知识点)

## 防火墙

- 执行`systemctl status firewalld.service`查看防火墙状态
- 执行`systemctl enable firewalld.service`开启防火墙
- 执行`systemctl restart firewalld.service`重启防火墙
- 执行`firewall-cmd --list-all`查看防火墙信息
- 执行`firewall-cmd --permanent --zone=public --add-port=3306/tcp`添加 3306 端口配置
- 执行`firewall-cmd --permanent --zone=public --remove-port=3306/tcp`移除 3306 端口配置
- [返回目录](#centos-知识点)

## ssh-登陆

- 使用 putty 的 ssh 工具生成公钥和私钥
- 执行`mkdir ~/.ssh`创建 ssh 目录
- 执行`chmod 700 ~/.ssh`设置权限
- 执行`vi ~/.ssh/authorized_keys`创建公钥认证文件，将公钥复制到文件中
- 执行`chmod 600 ~/.ssh/authorized_keys`设置权限
- 配置 putty 使用私钥登陆
- 执行`vi /etc/ssh/sshd_config`，配置 PasswordAuthentication no 可以关闭密码登陆,执行`systemctl restart sshd.service`重启 ssh 服务生效
- [返回目录](#centos-知识点)

## 简单的-vi-指令

- 输入`i`切换到输入模式,`esc`退出
- 输入`:wq`保存并退出,`:q!`退出不保存修改
- 输入`\查找内容`查找内容
- [返回目录](#centos-知识点)

## 安装-jdk

- 执行`yum search java|grep jdk`查找可用的 jdk 版本
- 执行`yum install java-1.8.0-openjdk-devel.x86_64`安装 openjdk1.8
- 执行`javac -version`测试 jdk 是否安装成功
- [返回目录](#centos-知识点)

## 安装-git

- 执行`yum install git`安装 git
- 执行`git --version`测试 git 是否安装成功
- 强制替换本地版本为远程  
  `git fetch --all`  
  `git reset --hard origin/master`  
  `git pull`
- 执行`git add .`添加全部更改文件
- 执行`git commit -a -m "提交信息"`提交更新
- 执行`git pull`拉取更新
- 执行`git push origin master`推送更新到远端主分支
- 执行`git config --global credential.helper store`可以本地存储 git 账号密码
- 在 git bash 中执行`ssh-keygen -t rsa -C huhuiyu.vip@gmail.com`可以创建 ssh 密钥
- 执行`git remote origin set-url [url]`修改远程仓库地址
- [返回目录](#centos-知识点)

## 安装-mysql

- 通过网址`https://dev.mysql.com/downloads/repo/yum/`找到 mysql 的 yum 安装源
- 执行`wget https://repo.mysql.com//mysql57-community-release-el7-11.noarch.rpm`下载安装文件
- 执行`yum localinstall mysql57-community-release-el7-11.noarch.rpm`添加到本地安装源
- 执行`yum repolist enabled | grep "mysql.*-community.*"`查看本地安装源是否添加成功
- 执行`yum install mysql-community-server`安装 mysql
- 执行`systemctl enable mysqld`配置 mysql 服务开机启动
- 执行`systemctl start mysqld`启动 mysql
- 执行`grep 'temporary password' /var/log/mysqld.log`查看 mysql 的默认 root 密码
- 执行`mysql -uroot -p`启动命令行，密码就是上一步查看的
- 执行`ALTER USER 'root'@'localhost' IDENTIFIED BY 'MySQL-123';`修改 root 默认密码，否则不能执行其它管理命令
- 执行`CREATE USER 'huhuiyu'@'%' IDENTIFIED BY 'MySQL-123';`添加用户
- 执行`GRANT ALL ON *.* TO 'huhuiyu'@'%' with grant option;`用户授权
- 执行`FLUSH PRIVILEGES;`用户权限立即生效
- [返回目录](#centos-知识点)

## 安装-nginx

- 执行`vi /etc/yum.repos.d/nginx.repo`编辑 nginx 下载源，内容如下  
  [nginx]  
  name=nginx repo  
  baseurl=http://nginx.org/packages/centos/7/$basearch/  
  gpgcheck=0  
  enabled=1
- 执行`yum install nginx`安装 nginx
- 执行`systemctl enable nginx`配置 nginx 服务开机启动
- 执行`systemctl start nginx`启动 nginx
- 执行`systemctl disable nginx`关闭 nginx 服务开机启动
- 执行`systemctl stop nginx`停止 nginx
- 配置文件默认位置  
  /etc/nginx/nginx.conf  
  /etc/nginx/conf.d/\*.conf
- 通过浏览器打开`http://服务器地址`测试 nginx 是否搭建成功
- [返回目录](#centos-知识点)

## mysql-主从备份

- 开启主库 binarylog  
  执行`vi /etc/my.cnf`打开 mysql 配置文件，在 mysqld 小节下面添加配置  
  log_bin=mysql-bin  
  server-id=1  
  binlog_do_db=要主从的数据库名称  
  binlog-ignore-db=不需要主从的数据库名称  
  执行`systemctl restart mysqld`重启 mysql  
  执行`show master status\G`查看主库日志状态记住 File 和 Position，从库需要这个
- 开启从库 binarylog  
  执行`vi /etc/my.cnf`打开 mysql 配置文件，在 mysqld 小节下面添加配置  
  log_bin=mysql-bin  
  server-id=2  
  replicate_do_db=要主从的数据库名称  
  replicate-ignore-db=不需要主从的数据库名称  
  relay_log=relay_bin  
  log-slave-updates=ON
  执行`systemctl restart mysqld`重启 mysql  
  执行  
  `CHANGE MASTER TO MASTER_HOST='主库ip', MASTER_USER='主库用户', MASTER_PASSWORD='主库密码', MASTER_LOG_FILE='上面主库查询的file', MASTER_LOG_POS=上面主库查询的position;`  
  语句初始化从库同步状态  
  执行`show slave status\G`查看从库日志状态
- [返回目录](#centos-知识点)

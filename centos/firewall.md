# 防火墙

- [返回](index.md)
  ***
- 执行`systemctl status firewalld.service`查看防火墙状态
- 执行`systemctl enable firewalld.service`开启防火墙
- 执行`systemctl restart firewalld.service`重启防火墙
- 执行`firewall-cmd --list-all`查看防火墙信息
- 执行`firewall-cmd --permanent --zone=public --add-port=3306/tcp`添加 3306 端口配置
- 执行`firewall-cmd --permanent --zone=public --remove-port=3306/tcp`移除 3306 端口配置
  ***
- [返回](index.md)
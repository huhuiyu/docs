# 防火墙

- [返回](README.md)
  ***
- 执行`systemctl status firewalld.service`查看防火墙状态
- 执行`systemctl enable firewalld.service`开启防火墙
- 执行`systemctl restart firewalld.service`重启防火墙
- 执行`firewall-cmd --list-all`查看防火墙信息
- 执行`firewall-cmd --permanent --zone=public --add-port=80/tcp`添加80端口配置
- 执行`firewall-cmd --permanent --zone=public --remove-port=80/tcp`移除80端口配置
  ***
- [返回](README.md)
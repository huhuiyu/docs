# nginx安装

- [返回](README.md)
  ***

- 执行`vi /etc/yum.repos.d/nginx.repo`编辑 nginx 下载源，内容如下  

  ```inf
  [nginx-stable]
  name=nginx stable repo
  baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
  gpgcheck=1
  enabled=1
  gpgkey=https://nginx.org/keys/nginx_signing.key
  ```

- 执行`yum install nginx`安装 nginx，过程中所有问题都输入`y`确定
- 执行`nginx -v`查看安装是否成功(会显示版本号)
- 执行`systemctl enable nginx`配置 nginx 服务开机启动
- 执行`systemctl start nginx`启动 nginx
- 执行`systemctl disable nginx`关闭 nginx 服务开机启动
- 执行`systemctl stop nginx`停止 nginx
- 配置文件默认位置  

  ```linux
  /etc/nginx/nginx.conf  
  /etc/nginx/conf.d/\*.conf
  ```

- 通过浏览器打开`http://服务器地址`测试 nginx 是否搭建成功)
  ***
- [返回](README.md)
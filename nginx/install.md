# nginx安装和基础配置

- [返回](README.md)
  ***
- [nginx官方网站](http://nginx.org/)  
  ![nginx001](images/nginx001.png)  
  ![nginx002](images/nginx002.png)  
  ![nginx003](images/nginx003.png)  
  ![nginx004](images/nginx004.png)  
  ![nginx005](images/nginx005.png)  
  ![nginx006](images/nginx006.png)  
  ![nginx007](images/nginx007.png)  
  ![nginx008](images/nginx008.png)  
  ![nginx009](images/nginx009.png)  
  ![nginx010](images/nginx010.png)  
  ![nginx011](images/nginx011.png)  
  ![nginx012](images/nginx012.png)  
  ![nginx013](images/nginx013.png)  
  ![nginx014](images/nginx014.png)  
  ![nginx015](images/nginx015.png)  
- `nginx.conf`的内容

```nginx
events {
#连接数配置
    worker_connections 1024;
}
#http服务配置
http {
#包含类型配置文件
    include mime.types;
#服务器配置
    server {
#下面的配置表示当访问http://本机ip地址的时候会展示html目录下面的index.html
#如果监听端口号不是80，需要通过http://本机ip地址:端口号访问
#监听端口号，80是http默认端口
        listen 80;
#服务器名称，0.0.0.0表示本机所有ip地址，也可以是域名
        server_name 0.0.0.0;
#默认编码
        charset utf-8;
#虚拟目录配置,/表示服务器根
        location / {
#root表示虚拟目录对应的文件目录
            root html/;
#index是默认文档
            index index.html;
        }
    }
}
```

- `start.bat`的内容`D:\Develop\nginx-1.14.2\nginx -c nginx.conf`
- `stop.bat`的内容`D:\Develop\nginx-1.14.2\nginx -s stop -c nginx.conf`
  ***
- [返回](README.md)
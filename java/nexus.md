# 自建私有仓库

- [返回](README.md)
  ***
- [nexusoss 官方网站](https://www.sonatype.com/nexus-repository-oss)
- [unix 下载地址](https://download.sonatype.com/nexus/3/latest-unix.tar.gz)
- 执行`wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz`下载
- 执行`tar -zxvf latest-unix.tar.gz`解压
- 进入解压后的`bin`目录执行`./nexus run &`启动
- 默认访问端口为`8081`，默认用户`admin`,默认密码`admin123`
- 创建`hosted`类型的`maven`资源库即可
  ***
- [返回](README.md)
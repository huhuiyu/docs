# putty基础

- [返回](putty.md)
  ***
- **连接服务器**  
  ![centos015](images/centos015.png)  
  ![centos016](images/centos016.png)  
  ![centos017](images/centos017.png)  

- **ssh连接服务器**  
  ![centos018](images/centos018.png)  
  ![centos019](images/centos019.png)  
  ![centos020](images/centos020.png)  
  ![centos021](images/centos021.png)  
  ![centos022](images/centos022.png)  
  ![centos023](images/centos023.png)  
  ![centos024](images/centos024.png)  
  ![centos025](images/centos025.png)  
  ![centos026](images/centos026.png)  
  ![centos027](images/centos027.png)  
  上面的四个指令  

  ```linux
    mkdir ~/.ssh
    chmod 700 ~/.ssh
    vi ~/.ssh/authorized_keys
    chmod 600 ~/.ssh/authorized_keys
  ```

  ![centos028](images/centos028.png)  
  ![centos029](images/centos029.png)  
  ![centos030](images/centos030.png)  
  ![centos031](images/centos031.png)  
  ![centos032](images/centos032.png)  
  ![centos033](images/centos033.png)  
  ![centos034](images/centos034.png)  

  **拒绝使用密码登录-一旦开启，丢失ssh密钥将无法登录！！！**  
  执行`vi /etc/ssh/sshd_config`配置ssh  
  ![centos035](images/centos035.png)  
  执行`systemctl restart sshd.service`重启ssh服务生效  
  ***
- [返回](putty.md)
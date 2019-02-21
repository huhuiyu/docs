# github

- [返回](README.md)
  ***
- 一些简单的指令  
  `git clone 资源库地址`-克隆资源库  
  `git status`-查看资源库状态  
  `git add 文件或者.`-添加文件或者全部文件到暂存区  
  `git commit -m "提交代码的说明信息"`-提交  
  `git pull`-拉取远程文件  
  `git push`-推送到远程  
  `git remote origin set-url [url]`-修改远程仓库地址
- 强制替换本地版本为远程

  ```git
  git fetch --all
  git reset --hard origin/master
  git pull
  ```

  ***
- [返回](README.md)
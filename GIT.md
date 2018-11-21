# git-知识点

- [返回目录](README.md)
- [开启-SSH](#开启-SSH)

## 开启-SSH

- 检查是否存在`ssh`：打开`git bash`，输入`cd ~`，再输入`cd .ssh`，如果提示目录不存在就不存在 ssh，存在就继续输入`ls`，会显示目录中的文件，查看是否存在`id_rsa`文件（如果公钥没有移动，会有 id_rsa.pub 文件）
- 如果上面检测失败，执行`cd ~`，再输入`ssh-keygen -t rsa -C "你的邮箱"`启动 sshkey 创建，然后所有的提示都直接回车（选择默认值），完成后执行上一步检测
- 打开`ssh`文件所在目录：打开`git bash`，输入`cd ~`，再输入`cd .ssh`，在输入`start .`即可
- [code.aliyun.com](https://code.aliyun.com) 的 ssh 配置

  - 登录后点击左侧`设置`菜单
  - 点击左侧`SSH 公钥`菜单
  - 点击右上`增加SSH密钥`按钮
  - 用文本编辑器打开上个步骤中生成的`id_rsa.pub`文件，将内容复制到公钥的文本框中
  - 标题可以输入你的邮箱，然后点击`增加密钥`按钮完成公钥添加

- [github.com](https://github.com/) 的 ssh 配置

  - 登录后点击用户头像下拉菜单中的`settings`菜单
  - 点击左侧`SSH and GPG keys`菜单
  - 点击右上`New SSH key`按钮
  - 用文本编辑器打开上个步骤中生成的`id_rsa.pub`文件，将内容复制到 key 的文本框中
  - title 可以输入你的邮箱，然后点击`Add SSH key`按钮完成公钥添加

- [gitee.com](https://gitee.com/) 的 ssh 配置

  - 登录后点击用户头像下拉菜单中的`设置`菜单
  - 点击左侧`SSH公钥`菜单
  - 用文本编辑器打开上个步骤中生成的`id_rsa.pub`文件，将内容复制到公钥的文本框中
  - 标题可以输入你的邮箱，然后点击`增加密钥`按钮完成公钥添加

- [返回目录](#git-知识点)

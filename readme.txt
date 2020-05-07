1.官网下载git 默认安装即可

2.在开始菜单找到 Git Bash 打开,执行设置指令:
  a.$ git config --global user.name "名字"
  b.$ git config --global user.email "email地址"

3.在需要使用git管理的文件根目录右键打开 Git Bash,
  a.通过 $ git init 命令把这个目录变成Git可以管理的仓库

4.在仓库内添加文件
  a.$ git add 文件名称.后缀 (多文件添加用空格隔开)
  b.$ git commit -m "描述内容"
1.官网下载git 默认安装即可

2.在开始菜单找到 Git Bash 打开,执行设置指令:

  a.$ git config --global user.name "名字"

  b.$ git config --global user.email "email地址"

3.在需要使用git管理的文件根目录右键打开 Git Bash,

  a.通过 $ git init 命令把这个目录变成Git可以管理的仓库,创建Git版本库时，Git自动为我们创建了唯一一个master分支

4.在仓库内添加文件

  a.$ git add 文件名称.后缀 (多文件添加用空格隔开):实际上就是把文件修改添加到暂存区

  b.$ git commit -m "描述内容" :实际上就是把暂存区的所有内容提交到当前分支

5.文件修改

  a.通过 $ git status 查看仓库状态(哪些文件是否有修改)

  b.通过 $ git diff 文件名称.后缀 查看具体修改的内容

  c.确认后再次提交到仓库(步骤4)

  d.再次查看仓库状态

6.版本回退

  a.通过 $ git log 查看提交历史

  b.HEAD:表示当前版本;HEAD^^:表示上一版本;HEAD^^:表示上上一版本,依次类推;100个^简写:HEAD～100

  c.使用 $ git reset --hard HEAD^ 回退到上一版本

  d.注:再次使用 $ git log 查看记录发现最新版本记录没有了(确保当前窗口没有关闭,仍然可以查看到之前的commitID)
    解决办法:通过 $ git reset --hard 对应版本的commitID 指定回到该版本
    窗口关闭情况: 通过 $ git reflog 查看每次提交的commitID

7.文件删除

  a.$ git rm 文件名称.后缀

  b.$ git commit -m "删除文件描述"


8,本地删除通过版本库恢复(实际是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”)

  a.$ git checkout --文件名称.后缀

-------------------------------------------------- 远程仓库 ---------------------------------------------

1.创建SSH Key(只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了)

  a.$ ssh-keygen -t rsa -C "email地址",一路回车

  b.在用户主目录里找到 .ssh 目录,里面有 id_rsa 和 id_rsa.pub 两个文件,这两个就是SSH Key的秘钥对，id_rsa是私钥,id_rsa.pub是公钥

  c.登陆GitHub，打开“Account settings”，“SSH Keys”页面,点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容

2.添加远程库

  a.在GitHub创建一个 repository,Repository name填写与本地仓库名字一致,其他默认即可

  b.把本地仓库关联GitHub仓库,在本地库运行命令: $ git remote add origin git@github.com:自己的GitHub账户名/仓库名.git
    注:git@github.com:自己的GitHub账户名/仓库名.git:可以直接复制远程库SSH地址
  
  c.把本地库的内容推送到远程库 命令: $ git push -u origin master,输入yes即可
    注:	我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令

  d.本地提交后 通过 $ git push origin master 将本地分支的最新修改推送至远程库

3.从远程库克隆(先有远程库情况)

  a.创建空文件夹用作本地仓库

  b.通过 $ git clone add origin git@github.com:自己的GitHub账户名/仓库名.git 将远程库克隆到本地













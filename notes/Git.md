# 基本操作
git pull

git status

git add .

git commit -m "注释信息"

git push origin master




## 改作者身份信息
git config --global user.email "youremail@google.com"

git config --global user.name "your name"

修改提交时作者名字

不过之前提交的不能改，配置之后就会显示作者名字了


# 解决冲突
简单冲突直接拉取会自动合并，再add+commit+push

如果冲突比较复杂，无法自动合并，会提示你手动解决冲突，步骤如下：

先把本地的代码add并且commit之后，再拉取，再手动解决冲突，再将无冲突的版本重新add+commit，有需要的话，最后再push

或者Pycharm菜单 - VCS - Git - Resolve Conflicts

或者git mergetool


## 拉取
拉取

git pull

然后会合并到本地，如果复杂的冲突会显示在py文件中，手动选择怎么合并，合并后再重新提交



# 冲突显示格式：

<<<<<<< HEAD

本地老代码

=======

git远端分支上拉取的新代码

\>>>>>>> de9ad0139e331843184180e12e4fa4a5cae321d4

把<<<<<<<和>>>>>>>之间的代码手动合并/筛选之后，就可以重新add和commit

### 注：
如果是本地没有这个文件，而远程有这个文件，那么可能冲突体现不出来，可能要重新建立，然后把冲突解决后，修改gitignore把不必要的文件忽略掉

# 冲突合并编辑方法
如果拉取过程让你取名字/写合并理由，再提交，注意这是Linux的操作：

按 i 或者 insert键，开始写入模式，正常写理由

写好后，按Esc键退出写入模式，还没保存

输入“:w”保存，进入查看模式

输入 “:q”退出整个Linux模式

详情见链接：我的Linux（SecureCRT）操作笔记


# 查看状态
git status

看当前分支状态

有暂存了的和没有暂存的

Changes to be committed:下面就是已经暂存的

  modified: xxx.py

Changes not staged for commit:下面是没有暂存的更新

modified: xxx.py




# 暂存
暂存命令：

git add main.py

git add .


## 暂存撤销
commit 之前撤销暂存命令（commit之后就没用了）：

git reset main.py

git reset .

git reset


# 提交注释
提交并注释：

git commit -m "update main.py"


## 撤销提交注释
commit之后，push之前，撤回commit，回到add之前的命令：

git reset HEAD~

（这时撤销的这个commit会复制到ORIG_HEAD上去，后面如果要用的可以用）



# 推送：

git push origin master





# 下载代码：

git clone https://github.com/iphysresearch/TOP250movie_douban.git

# 问题解决：

问题：

warning: LF will be replaced by CRLF in post.php.

解决方法：

git config --global core.autocrlf false



# 添加SSH秘钥

在bash中输入：

cat ~/.ssh/id_rsa.pub

然后返回的字符串，全部复制，粘贴到网站的设置里添加SSH key的地方：

http://gitlab.go-goal.cn/profile/keys

然后鼠标点击“Add key”

就可以了


# 合并代码工具
配置meld为mergetool

git config --global merge.tool meld

git config --global mergetool.meld.path "C:\Program Files (x86)\Meld\Meld.exe"

或者Pycharm 菜单栏-VCS-Git-Resolve Conflicts

但都不好用，还是在代码里直接手动改最安全可靠






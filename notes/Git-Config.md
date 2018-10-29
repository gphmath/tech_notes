首先生成一个你要添加的git账户的rsa码，填那个git的邮箱
```
ssh-keygen -t rsa -C "XXXXX@163.com"
```

在返回问题中：

```
Enter file in which to save the key (****/id_rsa):
```
这后面自己填一个新的秘钥的名字，复制这串地址，加个后缀就行，比如****/id_rsa_new_acount

后面都回车选择默认值，就会出现如图

多个.pub的id_rsa_new_acount.pub是公钥

用文本编辑器打开这个公钥id_rsa_new_acount.pub，全部复制这串公钥字符串，添加到git网站的SSH秘钥里面

开启ssh-agent：
```bazaar
eval `ssh-agent -s`
```


添加刚刚创建的ssh
```bazaar
ssh-add ~/.ssh/id_rsa_gphmath
```


编辑配置文件~/.ssh/config
```
#Default gitlab.go-goal.cn

Host gitlab.go-goal.cn

  HostName gitlab.go-goal.cn

  User git

  IdentityFile ~/.ssh/id_rsa

Host github-gphmath

  HostName github.com

  User git

  IdentityFile ~/.ssh/id_rsa_gphmath
```
编辑完这里有两个host配置，第二个是新添加的Host那里相当于别名，自己取一个好理解的，后面要用。

HostName就是git网站的地址。

IdentityFile就是你前面添加的秘钥文件

管理仓库地址

查看当前项目的git配置：
```markdown
git config -l
```


查看当前项目的仓库url：
```bazaar
git remote -v
```


删除当前仓库remote的origin分支的url设置：
```
git remote rm origin
```
添加remote的origin分支url：
```
git remote add origin URL地址
```
更改(设置)remote的origin分支url：
```
git remote set-url origin URL地址
```


如果从HTTPS模式调整为使用SSH的话，是需要修改origin分支的URL的。

HTTPS模式的URL是：
```
https://github.com/gphmath/tech_notes.git
```
对应的SSH模式的URL就是
```
git@github-gphmath:gphmath/tech_notes.git
```
其中前缀就是"git@"加上前面config文件的HOST别名"github-gphmath"

冒号后面是git的用户名

后面仓库名字是一样的

所以要改成SSH的话，就直接设置新的URL：
```
git remote set-url orgin git@github-gphmath:gphmath/tech_notes.git
```
当然也可以用上面的方法，先删除旧的，再添加新的

本地新建git仓库：

在新文件夹下面
```
git init
```
然后用上面的方法设置好要传的远端仓库URL（不管是用HTTPs还是SSH）
```
git remote add origin ****
```
就可以了，正常创建文件，写代码，正常add，commit，push


网上的命令参数列得太全。。还是自己记一下常用的比较好以后到这里搜索比较方便

原来，tar只是打包，并不压缩，不过一般情况下为什么要压缩呢，除非太大放不下，打包解包很方便嘛



tar -cvf xpdf_linux.tar xpdfl

c表示压打包，compress

v表示显示view压缩的全过程，压缩了哪些文件

f表示指定压缩后的文件名，必须放在最后

f后面隔一个空格紧跟压缩后的名称

再隔一个空格，要压缩的文件夹



tar -xvf xpdf_linux.tar

解包，其他一样，就是

x表示解包

然后不需要指定解包后的文件夹名，自动是解开为同名文件夹



.tar.gz 和 .tgz

解压：tar -zxvf FileName.tar.gz

压缩：tar -zcvf FileName.tar.gz DirName

就是参数都比上面不压缩的时候多一个字母：z



压缩包zip

解压：unzip FileName.zip

压缩：zip FileName.zip DirName

unzip -d folder a.zip

把a解压到folder文件夹下





ll很好用！！！等价于 ls -l

ls -al

不一定要切到那个文件夹下才能查看

可以用

ll folder

ls -l folder

-a：连系统文件也显示，名称前有个点的那种，一般不需要关注

-l：显示文件详情，路径，时间等，一行显示一个文件，看起来比较清楚



rm hhh.tar

rm -f hhh.tar

删除某个文件，不能删除文件夹

-f 就是直接强行删除，不作任何提示的意思，

rm -rf testfolder（文件夹名称）

-r 就是向下递归，不管有多少级目录，一并删除，删除文件夹的话一定要写，否则无法删除文件夹，哪怕是空文件夹









locate guoph/xpdf

查找guoph这个文件下面（包括它的子文件里），所有以xpdf开头的文件和文件名

好处是可以显示出完整的文件路径，方便代码里用



vim testfile

vi testfile

这里vi和vim是一样的。后面的文件名，如果不存在就是新建文件，如果存在，就是编辑文件

一开始要按一下字母i，进入insert插入，也就是编辑模式

编辑好后，按ESC或者CTRL+C，退出编辑模式，还没保存。

输入:w，注意是冒号加w，保存文件，这时候是查看文件模式

再输入:q，退出该文件



mkdir guoph/newfolder

在guoph文件夹下创建新文件夹newfloder

mkdir -p guoph/China/Shanghai

-p表示递归创建，如果没有China文件夹，就会自动新建China文件夹，再在下面创建Shanghai



移动和重命名

重命名就是相当于在同一个文件夹里移动为新名字的文件

mv，就是move

mv oldlocation newlocation

比如重命名：

mv pcre2-10.23 pcre

如果不是重命名，是移动，那肯定要分别写上新旧路径

比如，移动加重命名：

mv pcre2-10.23.zip test/pcre.zip

移动但不重命名，就可以省略（假设wuyuan和JiangXi在同一文件夹下）：

mv wuyuan.tar JiangXi

mv pcre2-10.23.zip test

mv a/* b

把a下的全部文件，移到b



复制文件

cp [options] source dest



./configure :配置和检查安装环境，可以指定安装参数，安装地址，都在这里配置

make 编译，不需要权限

make all 正式安装，需要权限




获取当前路径

pwd





软件路径：

/usr/bin



cd :切换目录，就是change directory缩写





上传 在目标目录下输入：

rz

然后选择文件就可以

就会上传到该目录

试试rz -y，是不是默认打开本地上传目录

sz

下载到本地

设置下载上传地址：

在session option里面

X/Y/Zmode里面设置本地的上传和下载目录



进入Python虚拟环境

source ../run_python3_env/bin/activate

source 就是开启某个环境，主要就是要找到activate文件在那里，

比如你已经进入上面这个bin文件夹

source activate

就行了



至于创建新的虚拟环境，用virtualenv命令，网上查查就好了。

一般服务器上的电脑都有虚拟环境了，直接用就行



查看当前运行的所有python程序

ps -ef | grep python

看鸟哥私房菜P516：进程的查看

grep表示正则表达式，最后一列里会打出触发此进程的命令语句，比如python3 main.py，就可以被正则表达式匹配到

常用的：

ps -l:查自己bash程序

ps aux：查所有进程

-ef表示所有进程

-f只打印当前bash的？

ps aux |grep cluster

就可以看自己的聚类程序了



杀死进程，比如进程ID是3827

kill -9 3827





nohup python3 main.py &

nohup表示不要输出到命令行（会输出到当前目录下的nohup.out文件，如果没有就会创建），最后一个&表示运行到后台，结合起来用。

然后就可以输入其他命令，也可以退出，程序不会停止。





VI模式下：命令：

Vi Cheat Sheet

ctrl+f，向下（前）翻一页

ctrl+b，向上（后）翻一页

ctrl+u，上翻半页

ctrl+d，下翻半页

:e 刷新当前文档（e就是edit）

CTRL+e：向下滚动一行

CTRL+y：向上滚动一行

CTRL+G：显示当前文件名、路径、行数、当前阅读进度百分比





注意Python cannot import module 的问题

Python can't find my module

python不知道你运行的文件在哪个项目里的，只会找系统路径和同一文件夹下的module，所以要么添加路径，要么把py文件移到适当的地方：

运行的py文件和要导入的module的第一层在同一文件夹下，

比如from a.b import c，要求a和py文件在同一文件夹下














创建一个learngit版本库
$ mkdir learngit
$ cd learngit
$ pwd   //pwd命令用于显示当前目录
---------------------------------------
通过git init命令把这个目录变成Git可以管理的仓库
$ git init
---------------------------------------
用命令git add告诉Git，把文件添加到仓库
$ git add readme.txt
用命令git commit告诉Git，把文件提交到仓库
$ git commit -m "wrote a readme file"


---------------------------------------
git status命令可以让我们时刻掌握仓库当前的状态
$ git status
---------------------------------------
git diff查看difference，显示的格式正是Unix通用的diff格式
$ git diff readme.txt 

git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别
$ git diff HEAD -- readme.txt 
---------------------------------------
git log命令显示从最近到最远的提交日志
$ git log
$ git log --pretty=oneline //
---------------------------------------
git reset命令：
$ git reset --hard HEAD^
上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100

$ git reset --hard 3628164 //$ git reset --hard (commit id)指定回到未来的某个版本
---------------------------------------
git reflog用来记录你的每一次命令
$ git reflog
---------------------------------------
git checkout -- file可以丢弃工作区的修改：
$ git checkout -- readme.txt
--很重要
命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。
---------------------------------------
命令git reset HEAD file可以把暂存区的修改撤销掉（unstage），重新放回工作区：
$ git reset HEAD readme.txt
git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本。
---------------------------------------
命令git rm用于删除一个文件。
$ git rm test.txt
如果一个文件已经被提交到版本库，那么你永远不用担心误删，
但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容
---------------------------------------

---------------------------------------
***            远程仓库            ****
---------------------------------------
创建SSH Key:
$ ssh-keygen -t rsa -C "youremail@example.com"
换成你自己的邮件地址(一路回车，使用默认值即可)

用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥

登陆GitHub
点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
---------------------------------------
命令git remote add origin git@server-name:path/repo-name.git；本地仓库关联
origin:远程库的名字就是origin
server-name:path/repo-name.git:GitHubGitHub账户名/远程库

$ git remote add origin git@github.com:michaelliao/learngit.git

---------------------------------------
本地库的所有内容推送到远程库上：
git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

***当你第一次使用Git的clone或者push命令连接GitHub时，会得到一个警告：
***The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
***RSA key fingerprint is xx.xx.xx.xx.xx.
***Are you sure you want to continue connecting (yes/no)?
***这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，
需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入yes回车即可。
---------------------------------------



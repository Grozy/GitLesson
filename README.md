#Git教程
##Git常用命令
###git init -- 初始化仓库
要使用Git进行版本管理，首先初始化仓库。
```
mkdir git-tutorial
cd git-tutorial
git init
```
如果初始化成功，执行了`git init`命令的目录下就会生成.git目录。这个.git目录里存储着管理当前目录内容所需的仓库数据。
Git中，称这个目录为“附属于该仓库的工作树”
###git status --查看仓库状态
`git status`命令用于显示Git仓库的状态。工作树和仓库在被操作的过程中，状态会不断的发生变化。在Git操作过程中时常用`git status`命令查看当前命令了。
```
$ git status
# On branch master
#
# Initial commit
#
noting to commit (create/copy files and use "git add" to track)
```
如上，第一行`#`提示所在的分支，例子中是master分支。`Untracked files`中显示了未提交的文件信息。只要曾经对Git的工作树或仓库进行操作，`git status`命令的显示结果就会发生变化。
###git add -- 向暂存区中添加文件
如果只是用Git仓库的工作树创建了文件或文件内容发生了修改，那么该文件并不会被记入Git仓库的版本管理对象中。因此我们用`git status`命令显示发生变化的文件，它们就会显示在Untracked files里。要想让文件成为Git仓库的管理对象，就需要用`git add`命令将其加入暂存区(Stage或者Index)中。暂存区是提交之前的一个临时去。
```
$git add README.md 
$git status
# On branch Master
#
# Initial commit
# 
# Changes to committed:
#
#	new file:  README.md
#
```
将README.md文件加入暂存区后，`git status`命令的显示结果发生了变化，README.md文件显示在Changes to commited中了。

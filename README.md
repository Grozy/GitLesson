#Git教程
新增一条分支feature-B中的数据
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
###git commit -- 保存仓库的历史记录
`git commit`命令可以将当前暂存区中的文件实际保存到仓库的历史记录中。通过这些记录，我们就可以在工作树中恢复文件。
```
$git commit -m "First commit"
```
`-m`参数后的"First commit"称作提交信息，是对这个提交的概述。
如果想要详细提交信息，直接执行`git commit`命令。执行后编辑器就会启动。
 第一行：用一行文字简述提交的更改内容
 第二行：空行
 第三行：技术更改的原因和详细内容
在以#标识的注释Changes to be commited栏中，可以查看本次提交中包含的文件。将提交信息按格式记述完毕后，保存并关闭编辑器。以#标识注释的行不必删除。
执行完`git commit`命令后再查看当前状态。
```
$ git status
# On branch master
nothing to commit, working directory clean
```
当前工作树处于刚刚完成提交更新的状态，所以结果显示没有更改。
如果想要终止提交，将填写信息留空并直接关闭编辑器，随后提交会被终止。
###git log -- 查看提交日志
`git log`命令可以查看以往仓库中提交的日志。包括可以查看什么人在什么时候进行了提交或合并，以及操作前后有怎样的差别。
```
$ git log
 
commit 提交的哈希值
Author 提交的人，包括邮箱
	提交的信息
```
只显示指定的目录、文件的日志，只要在`git log`命令后加上目录名，便会只显示该目录下的日志。如果加的是文件名，就会只显示与文件相关的日志。
####显示文件的改动
如果想查看提交索带来的改动，可以加上-p参数，文件的前后差别就会显示在提交信息之后。
```
$git log -p
```
执行命令之后，就可以查看提交的详细内容。
`git log --graph`通过加上graph参数，就可以看到图形化的log信息。
###git diff -- 查看文件修改前后的差别
git diff 命令可以查看工作树、暂存区、最新提交之间的差别。
```
$ git diff
```
没有add心文件之前，`git diff`只会显示工作树与最新的提交状态之间的差别。"+"表示新增行，"-"表示删除行
```python
def func(params):
	print(params)

class a(Object):
	func init():
		print("init")
```
```Objective-C
@interface Person :NSObject

@property (nonotmiac,copy) NSString *name;

@end
```

# Git  常用命令
###一、创建版本库
1、命令`mkdir learngit`  创建目录<br>
2、命令`git init`  初始化仓库<br>
3、添加文件到git仓库，分两步：<br>
＊ 命令`git add <file>`  添加多个文件，文件之间用空格，或用.表示所有文件<br>
＊ 命令`git commit -m “introduce”` 把暂存区的内容提交到分支 introduce表示提交的说明<br>
4、命令`git status`  查看当前状态<br>
5、命令`git diff file` 查看文件修改的内容<br>

###二、时光穿梭机<br>
1、版本回退<br>
* 命令`git log (--pretty=oneline)`  查看提交日志(简洁信息)<br>
HEAD表示当前版本<br>
* `git reset --hard commit_id` 回退到commit_id对应的版本<br>
* `git reflog`  查看命令历史记录<br>
2、暂存区和工作区
* 工作区－－在电脑里能看到的目录<br>
* 版本库－－隐藏的目录.git<br>
* 暂存区<br>
3、撤销修改
* 命令`git checkout -- file` 丢弃工作区的修改，回到最近一次git commit或git add的状态<br>
* 命令`git reset HEAD file`  撤销暂存区的修改，回到工作区<br>
4、删除文件<br>
*  `rm file`  文件管理器中删除文件<br>
* `git rm file`  从版本库中删除文件<br>

##三、远程仓库
1、命令`git remote add origin <branchName>`   把本地库的内容推送到远程库上<br>
2、命令`git push -u origin master`<br> 把分支master推送到远程，第一次推送加上－u参数，表示把本地master分支和远程master分支关联起来<br>
3、命令`git clone` 仓库git地址   克隆一个本地仓库<br>
git支持多种协议，包括https，通过ssh支持的原生git协议速度更快<br>

##四、分支管理
1、命令`git branch`  查看分支<br>
2、命令`git branch <name>`  创建分支<br>
3、命令`git checkout <name>`  切换分支<br>
4、命令`git checkout -b <name>` 创建并切换分支<br>
5、命令`git branch -d <name>`  删除分支  强制删除用大写的D<br>
6、命令`git log --graph` 查看分支合并图<br>
7、命令`git merge --no-ff -m "" <branchName>` 用普通模式合并，合并后的历史有分支<br>
8、命令`git stash` 把当前工作现场隐藏起来，当文件未写完无法提交时，可创建新分支<br>
* `git stash list` 查看工作现场<br>
#####恢复工作现场<br>
* 命令`git stash apply` 恢复，但stash内容并不删除<br>
* 命令`git stash pop` 恢复的同时把stash内容也删了<br>

##五、标签管理
1、命令`git tagtagName` 创建标签<br>
2、命令`git show tagName`  查看标签信息<br>
3、命令`git tag -a tagName -m ""`  指定标签信息<br>

##冲突管理
1、命令`git push origin branch-name`推送自己的修改；
如果推送失败,需要先用git pull试图合并,如果合并有冲突,则解决冲突,并在本地提交;没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！
如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream branch-name origin/branch-name`。

最后附上详细命令解释链接：(http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)




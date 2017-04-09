#Git相关
[TOC]

##基本流程
###查看历史
* 图示显示提交历史<br>`git log --graph --pretty=oneline --abbrev-commit`
###解决冲突
##文件状态
>
status|meaning
-------|-------
已暂存(staged)|对这个被暂存，并把暂存放到下次要提交的清单
已修改(modified)|已被修改，但还没被提交，没有做暂存
已提交(commited)|已安全的保存在本地数据库

##分支管理
###1\.创建分支<br>
* 创建本地分支<br>`git branch local_branch`
* 分支切换<br>`git checkout local_branch`
* **可简写为**`git checkout -b local_branch`
###2\.本地分支与远程分支
* 抓取远程分支到本地<br>`git checkout -b local_branch origin/remote_branch`
* 关联本地与远程分支<br>`git branch --set-upstream local_branch origin/remote_branch`
* 查看本地分支对应的远程分支<br>`git branch -vv`
* 远程分支已创建并与本地分支建立联系，在分支上推送<br>`git push`
* 远程分支已创建并未关联本地分支，在分支上推送<br>`git push -u origin/remote_branch`<br>仅关联的话可：<br>`git branch -u origin/remote_branch`
* 远程分支没有创建分支，在分支上推送(同名话':'之后可省略)<br>`git push origin local_branch:remote_branch`
###3\.查看分支状态
* 查看本地分支 &emsp; `git branch`
* 查看远程库信息 `git ls-remote`<br>或`git remote (-v 查看权限)/show remote_branch`
* 查看所有分支 &emsp;`git branch -a`
###4\.重命名分支
* 若newbranch名字分支已存在，则需要-M强制重命名(不建议)<br>`git branch -m|-M oldbranch newbranch`
###5\.删除分支
* 删除本地分支<br>`git branch -d (-force) local_branch`
* 删除远程分支<br>`git push origin --delete remote_branch`<br>或`git push origin :remote_branch`

##小技巧
###1\.修改错误的提交信息
* 编辑最近的一次提交（未推送）<br>`git commit --amend -m "new_commit_message"`
* 若已退送，则需要强制推送提交以覆盖（慎用）<br>`git push <remote> <branch> --force`
###2\.提交前撤销git add
* 往暂存区(staging area)中加入错误文件<br>移除一个文件<br>`git reset <file_name>`<br>移除所有未提交的文件<br>`git reset`
###3\.撤销合并
&emsp;&emsp;`git checkout -b <SHA>`
###4\.移除未被追踪的本地文件<br>
* 显示会被移除的文件 `git clean -f -n`
* 移除文件 `git clean -f`

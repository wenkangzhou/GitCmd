#基本功能

设置自己的用户名和邮箱 
- git config –global user.name "Your Name" 
- git config –global user.email "Your Email"

#本地缓存

修改到提交之间有一个缓存区 

* git add . 当前所有修改提交到缓存区，也可以单独指定
* git diff --cached 查看缓存区和本地仓库里的差异
* git diff HEAD 查看已缓存和当前的区别
* git diff 查看当前未缓存的和本地仓库里的区别
* git diff --stat 显示摘要

撤销缓存区里的一个更改，例如 git reset HEAD -- a.js

- git rm file 将file从文件缓存区、本地目录中移除
- git rm file --cached 只从缓存区移除，保存本地目录中的

#提交

- git commit 提交的是暂存区里面的内容，也就是 Changes to be committed 中的文件
- git commit -a 除了将暂存区里的文件提交外，还提交 Changes bu not updated 中的文件。
- git commit -m "commit info" 给提交内容添加注释
- git commit -am "commit info" 整合了git add和git commit -m
- git commit --amend 修改上一次提交的信息

#分支

- git branch 列出可用的分支
- git branch a 创建a分支
- git checkout -b a 检查a分支是否存在，不存在就创建，并且切换过去
- git push origin :a 删除远程分支
- git branch -d a 删除分支a
- git merge 其它分支合并到当前分支
- git checkout -b gh-pages origin/gh-pages 检出并且设置当前分支为远程分支gh-pages

#Log

- git log --oneline 紧凑查看
- git log --graph 图形显示
- git log a ^master 查看只在a分支里的修改
- git log --grep 正则取一个log
- git shortlog master 生成一个简报

#status

- git status 查看当前状态，包括add,commit,modify,merge等信息

#Tag

- git tag -a v1.0 打上v1.0

#远程

- git remote 列出远端的别名
- git remote add remotename remotepath 以remotename命名remotepath
- git remote rm remotename 删除别名为remotename的远程仓库
- git fetch 只下载
- git pull 下载并更新
- git push remotename branch 推送本地分支branch到远程仓库remotename的branch分支

#冲突

手动修改冲突，然后git add filename; git commit

#Diff

- git diff master..test 显示2个分支之间的差异 

#忽略

根目录先创建一个.gitignore 的文件 # 以'#' 开始的行，被视为注释. # 忽略掉所有文件名是 foo.txt 的文件. foo.txt # 忽略所有生成的 html 文件, *.html # foo.html是手工维护的，所以例外. !foo.html # 忽略所有.o 和 .a文件. *.[oa]

#合并特定的文件

- git cherry-pick #commitid

#回退到特定版本

- git reset --hard HEAD~3 会将最新的3次提交全部重置

#查看今天的更改

- git log --since=1.days

#未commit的文件回退到同线上一致的状态

-  git checkout 文件路径

#注
本文档内容根据[liluo](http://liluo.me/2015/03/11/git-learn.html)整理、添加。

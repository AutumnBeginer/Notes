# week1 git操作

## day1 git安装与首次commit

1.查看版本：git --version

2.建立目录+初始化仓库：

mkdir learning-log
cd learning-log
git init

注：git文件夹默认是隐藏的

3.可以在创建的文件夹下自命名.md文件来记录：

1. git init：把普通文件夹变成 Git 仓库
2. git add：把文件放进暂存区，告诉 Git 这个文件要存档
3. git commit：把暂存区的内容正式打包，生成一条提交记录

4.三板斧：add->commit->log

git add W1-Git笔记.md
git commit -m "W1 Git笔记 | 首次提交"
git log

新增修改后重复上一过程



git知识：git仓库分为工作区，暂存区和提交历史三部分

![](C:\Users\Autum\Desktop\Notes\Note_pictures\msedge_LkLCg0nTBo.png)

工作区类似于我们当前的项目文件，当项目文件有多个时，我们可以通过git add命令，将需要提交的文件放入暂存区里，当暂存区的文件全部整理好时，再通过commit命令统一提交，作为一次修改的整体版本。
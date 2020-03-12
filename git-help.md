## 基本步骤和命令
>参考-[廖雪峰git教程文档](https://www.liaoxuefeng.com/wiki/896043488029600/)
1. 启动本地git命令行
>开始菜单 >git>Git bash
2. 进入本地仓库
>D:\git\joanluck\learngit
******
## git基本操作命令
**查看git状态**
```
git status
```
 **创建仓库** 
+ 首先，选择一个合适的地方，创建一个空目录
+ 通过git init命令把这个目录变成Git可以管理的仓库 
```
git init
```

 **把文件添加到仓库**
+ 将文本文件放到仓库目录下
+ 用命令git add告诉Git，把文件添加到仓库：
+ 用命令git commit告诉Git，把文件提交到仓库：
```
git add readme.txt
git add file2.txt file3.txt
git commit -m "wrote a readme file"
#git commit -m <message> -m后面输入的是本次提交的说明
```

**添加远程库**
1. 登陆GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库：
2. 我们根据GitHub的提示，在本地的learngit仓库下运行命令：
 ```
git remote add origin git@github.com:michaelliao/learngit.git
#远程库的名字就是origin，这是Git默认的叫法
```
3. 把本地库的所有内容推送到远程库上
```
git push -u origin master
#第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
以后就可以简化命令
git push origin master
```
4. 小结
+ 要关联一个远程库，使用命令
```
git remote add origin git@server-name:path/repo-name.git
```
+ 关联后，使用命令第一次推送master分支的所有内容；
```
git push -u origin master
```

+ 此后，每次本地提交后，只要有必要，就可以使用命令推送最新修改；
```
git push origin master
```
**从远程库克隆**

```
git clone git@github.com:michaelliao/gitskills.git
```
**标签管理**

 + 首先，切换到需要打标签的分支上：

```
$ git branch
* dev
  master
$ git checkout master
Switched to branch 'master'
```

 + 然后，敲命令git tag <name>就可以打一个新标签：

```
git tag v1.0
```

+ 可以用命令git tag查看所有标签：

```
$ git tag
v1.0
```
**分支管理**
>Git鼓励大量使用分支：

+ 查看分支：git branch
+ 创建分支：git branch <name>
+ 切换分支：git checkout <name>或者git switch <name>
+ 创建+切换分支：git checkout -b <name>或者git switch -c <name>
+ 合并某分支到当前分支：git merge <name>
+ 删除分支：git branch -d <name>
+ 查看分支合并图：git log --graph

**历史版本**
>HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭。
+ 使用命令git reset --hard commit_id。
+ 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
+ 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
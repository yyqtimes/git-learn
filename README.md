# 1.仓库管理 常用命令

## 1.1 版本回退

在Git中，用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。

```shell
git reset --hard Head^   # -- 回退到上一个版本

# 指定commit-id回退到指定的版本
git reset --hard [commit-id]  
```

## 1.2 查看操作历史

```
git reflog
```

## 1.3 撤销修改

场景1：直接丢弃工作区的修改时，用命令`git checkout -- file`。

```shell
git checkout -- file
```

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD <file>`，就回到了场景1

## 1.4 远程仓库

### …or create a new repository on the command line

```
echo "# fastcore" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/fastjoy/fastcore.git
git push -u origin main
```

### …or push an existing repository from the command line



```
git remote add origin https://github.com/fastjoy/fastcore.git
git branch -M main
git push -u origin main
```

…delete remote

```
git remote remove origin
```

# 2. 分支管理

## 2.1 创建和切换分支

首先，我们创建`dev`分支，然后切换到`dev`分支：

```
$ git checkout -b dev
```

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

```
$ git branch dev
$ git checkout dev
```

## 2.2 分支合并

`dev`分支的工作成果合并到`master`分支上

```
$ git merge dev
```

`git merge`命令用于合并指定分支到当前分支。

## 2.3 删除分支

```shell
$ git branch -d dev

# 同步删除远程分支
$ git push origin --delete dev   
```

## 2.4 总结

Git鼓励大量使用分支：

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`或者`git switch <name>`

创建+切换分支：`git checkout -b <name>`或者`git switch -c <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

## 2.5 分支管理策略


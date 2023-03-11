# 1.git 常用命令

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


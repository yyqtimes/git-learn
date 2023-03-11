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




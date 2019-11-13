# git branch

> `git branch`命令用于列出，创建或删除分支。

### 查看分支

```
  git branch //本地分支
  git branch -r //远程分支
  git branch -a //所有分支
```

### 创建本地分支

```
  git checkout -b [branch-name]
```

本地分支推到服务端

```
  git push -u origin [branch-name]

  // 不加-u 需要额外绑定两个分支的关系
  git push origin [branch-name-remote]
  git branch --set-upstream [branch-name-local] origin/[branch-name-remote]
```

### 切换分支

```
  // 本地分支
  git checkout [local branch]

  // 远程分支, 并在本地创建同样的分支名
  git checkout -b 本地分支名 origin/远程分支名
  // eg
  git checkout -b dev origin/dev

  git push <远程主机名> <本地分支名>:<远程分支名>
  // eg
  git push -u origin dev:origin/dev

  or git push -u origin dev:origin/master

  or git push origin dev:origin/dev
  
  or git push origin dev:origin/master

```
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

### 删除分支

  现在在 `dev` 分支 想删除 `dev` 

  1.  先切换到别的分支: git checkout master

  2. 删除本地分支： git branch -d dev

  3. 如果删除不了可以强制删除，git branch -D dev

  4. 有必要的情况下，删除远程分支：git push origin --delete dev

  5. 在从公用的仓库fetch代码：git fetch origin dev:dev

  6. 然后切换分支即可：git checkout dev

  *注：上述操作是删除个人本地和个人远程分支，如果只删除个人本地，请忽略第4步
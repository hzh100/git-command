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


  ```
    在删除分支的时候,我们会使用git branch --delete dev来执行.有时还会通过缩写git branch -d dev来代替,使用中我们发现还有git branch -D dev的写法,他们有什么区别呢?

    -d 是--delete的缩写,在使用--delete删除分支时,该分支必须完全和它的上游分支merge完成(了解上游分支,可以点击查看链接),如果没有上游分支,必须要和HEAD完全merge
    -D 是--delete --force的缩写,这样写可以在不检查merge状态的情况下删除分支

    --force 简写-f,作用是将当前branch重置到初始点(startpoint),如果不使用--force的话,git分支无法修改一个已经存在的分支.
  ```



  ### 分支合并
    将某个分支merge到当前分支

    ```
      git merge [other-branch] 
    ```
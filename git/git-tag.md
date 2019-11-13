# git tag
> `git tag`命令用于创建，列出，删除或验证使用GPG签名的标签对象。同大多数 VCS 一样，Git 也可以对某一时间点上的版本打上标签。人们在发布某个软件版本(比如 v1.0 等等)的时候，经常这么做。本节我们一起来学习如何列出所有可用的标签，如何新建标签，以及各种不同类型标签之间的差别。//原文出自【易百教程】，商业转载请联系作者获得授权，非商业请保留原文链接：https://www.yiibai.com/git/git_tag.html

### 查看所有tag

```
  git  tag
```

### 本地打tag

```
  //最简单方式,commitID 不填默认为当前commit
  git tag [tag-name] [commit-id]

  eg
    git tag v1.0.0

  //比较合理的用法
  git tag -fa [tag-name] -m "your comment"
  // -f 表示覆盖已有的同名标签
  // -a 表示是annotated tag， 可以加注释

  eg
    git tag -a v1.0.0 -m "tag信息"

```
### tag 同步到服务端

```
  git push --tags // 只push tag， push 所有tags

  git push v1.0.0  // push 需要的tag

  git push --all // push 所有，包括代码和tag
```

### 删除本地tag

```
  git tag -d [tag-name]
```

### 删除tag

```
  git push origin :refs/tags/<tagname> //按名称删除所有分支中的tag
```


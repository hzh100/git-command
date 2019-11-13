# git diff

> `git diff`命令用于显示提交和工作树等之间的更改。此命令比较的是工作目录中当前文件和暂存区域快照之间的差异,也就是修改之后还没有暂存起来的变化内容。//原文出自【易百教程】，商业转载请联系作者获得授权，非商业请保留原文链接：https://www.yiibai.com/git/git_diff.html

查看本地修改

```
  git diff [filename] //查看未进入待提交队列的修改, 不填filename则是所有文件
  git diff --cached  //查看已进入待提交队列的修改
```


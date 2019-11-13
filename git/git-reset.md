# git reset

> 回退、回滚

###  <u>回退之前一定记得 做个 `分支的备份` <u>

***

回滚到某个commit_id

```
  git reset --hard commit_id
  // eg
  git reset --hard 139dcfaa558e3276b30b6b2e5cbbb9c00bbdca96 
```


强制提交到master分支（具体哪个分支请酌情修改）
```
  git push -f -u origin master
```


回退到上一个版本是：

```
  git reset --hard HEAD~1 或 git reset --hard HEAD^

  git push -f origin master
```
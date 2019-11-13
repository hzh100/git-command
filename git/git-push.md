# git push

> `git push`命令用于将本地分支的更新，推送到远程主机

一般格式

```
  git push <远程主机名> <本地分支名>:<远程分支名>
```

1. git push origin master
<br>
如果远程分支被省略，如上则表示将本地分支推送到与之存在追踪关系的远程分支（通常两者同名），如果该远程分支不存在，则会被新建

2. git push origin ：refs/for/master
<br>
如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支，等同于 git push origin –delete master

3. git push origin
   <br>
如果当前分支与远程分支存在追踪关系，则本地分支和远程分支都可以省略，将当前分支推送到origin主机的对应分支

4. git push
   <br>
如果当前分支只有一个远程分支，那么主机名都可以省略，形如 git push，可以使用git branch -r ，查看远程的分支名


**关于 refs/for**：
refs/for 的意义在于我们提交代码到服务器之后是需要经过code review 之后才能进行merge的，而refs/heads 不需要
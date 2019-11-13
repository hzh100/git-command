# git log

> `git log`命令用于显示提交日志信息

`git log` 可以让我们查看提交commit history, `git log`默认会输出commit hash, author, date, commit message.

### git log 提供的参数

### 1 --oneline

`--oneline`这个命令简化git log的默认的输出，仅仅输出commit hash 前7个字符串和commit message.

```
  16eada1 feat(docs): git reset
  275e572 feat(docs): git-fetch-pull.md
  8c211d4 update: git branch merge
  0da6b4d update: git-branch.md
```

### 2 --stat
`--stat`:是在git log 的基础上输出文件增删改的统计数据。


### 3 -p
`-p`:控制输出每个commit具体修改的内容，输出的形式以diff的形式给出。


### 4 --pretty
我们可以用–pretty来自定义输出的信息
<br>
`git log --pretty="%cn committed %h on %cd""`


### 5 --author
`--author`用来过滤commit,限定输出给定的用户

```
  git log --author="hzh100"
```

### 6 -n

`-n`: 限定log输出。直接在log命令之后，加 -n参数即可，n表示你要输出的数量.
```
  git log -2
```

### 7 限定指定日期范围的log

`--after` 和 `--before`

```
  git log --after '2019-11-13'
```
# git add
> *`git add` 命令将文件内容添加到索引(将修改添加到暂存区)。也就是将要提交的文件的信息添加到索引库中。*

### git add -A和 git add .   git add -u在功能上看似很相近，但还是存在一点差别

```
  git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
      [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
      [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing]
      [--chmod=(+|-)x] [--] [<pathspec>…​]//原文出自【易百教程】，商业转载请联系作者获得授权，非商业请保留原文链接：https://www.yiibai.com/git/git_add.html

  基本用法
    git add <path> <path>

```

* `git add . ` 提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件

* `git add -u ` 提交被修改(modified)和被删除(deleted)文件，不包括新文件(new) （git add --update的缩写）

* `git add -A`  提交所有变化 （git add --all的缩写）
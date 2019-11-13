# git reset

> 回退、回滚

## 回退之前一定记得 做个 `分支的备份`

---

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
---

## git add 撤销操作

git add . （空格+ 点） 表示当前目录所有文件，不小心就会提交其他文件

git add 如果添加了错误的文件的话

撤销操作

```
  git status 先看一下add 中的文件
  git reset HEAD 如果后面什么都不跟的话 就是上一次add 里面的全部撤销了
  git reset HEAD XXX/XXX/XXX.java 就是对某个文件进行撤销了
```
---

## git commit之后，想撤销commit

git add . //添加所有文件

git commit -m "本功能全部完成"

撤销操作

```
  git reset --soft HEAD^
```

这样就成功的撤销了你的commit

* 注意，仅仅是撤回 `commit `操作，代码仍然保留 `add` 操作（暂存区）。需再执行撤销 `git add` 操作
  更简单的做法
  ```
    git reset head^
    或
    git reset HEAD^
  ```
  此操作直接撤回`commit`和`add` 操作的所有文件

#### 说一下个人理解：

HEAD^的意思是上一个版本，也可以写成HEAD~1

如果你进行了2次commit，想都撤回，可以使用HEAD~2

---

## git reset 参数

### --mixed 
意思是：不删除工作空间改动代码，撤销commit，并且撤销git add . 操作
* 这个为默认参数,git reset --mixed HEAD^ 和 git reset HEAD^ 效果是一样的。
 

### --soft  
不删除工作空间改动代码，撤销commit，不撤销git add . 
 
### --hard
删除工作空间改动代码，撤销commit，撤销git add . 

注意完成这个操作后，就恢复到了上一次的commit状态。
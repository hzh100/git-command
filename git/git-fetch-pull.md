## git fetch和git pull的区别

### git fetch命令用于从另一个存储库下载对象和引用。

### git pull命令用于从另一个存储库或本地分支获取并集成(整合)。git pull命令的作用是：取回远程主机某个分支的更新，再与本地的指定分支合并，它的完整格式稍稍有点复杂。


#### git fetch
  
  1. git fetch相当于是从远程获取最新到本地，不会自动merge，如下指令：

  2. git fetch orgin master //将远程仓库的master分支下载到本地当前branch中

  3. git log -p master ..origin/master //比较本地的master分支和origin/master分支的差别

  4. git merge origin/master //进行合并

  也可以用以下指令：

  1. git fetch origin master:tmp //从远程仓库master分支获取最新，在本地建立tmp分支

  2. git diff tmp //将当前分支和tmp进行对比

  3. git merge tmp //合并tmp分支到当前分支

#### git pull
  
  1. git pull 相当于是从远程获取最新版本并merge到本地

  2. git pull origin master //将远程仓库的master分支下载到本地当前branch中并进行merge

  在实际使用中，git fetch更安全一些，效果相同时git pull将更为快捷。
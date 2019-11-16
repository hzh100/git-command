# git-command

> git 命令行 常用操作学习、记录

verify git commit message 
```
  yarn install or npm install
```


### Git是目前世界上最先进的分布式版本控制系统（没有之一）。[搭建Git服务器](https://bolerolily.github.io/2018/08/02/%E6%90%AD%E5%BB%BAGit%E6%9C%8D%E5%8A%A1%E5%99%A8/)


## Git commit message convention

> This is adapted from [Angular's commit convention](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-angular)

Messages must be matched by the following regex:

```
/^(revert: )?(feat|fix|polish|docs|style|refactor|perf|test|workflow|ci|chore|types)(\(.+\))?: .{1,50}/
```

#### Examples

Appears under "Features" header, `compiler` subheader:

```
feat(compiler): add 'comments' option
```

Appears under "Bug Fixes" header, `v-model` subheader, with a link to issue #28:

```
fix(v-model): handle events on blur

close #28
```

Appears under "Performance Improvements" header, and under "Breaking Changes" with the breaking change explanation:

```
perf(core): improve vdom diffing by removing 'foo' option

BREAKING CHANGE: The 'foo' option has been removed.
```

The following commit and commit `667ecc1` do not appear in the changelog if they are under the same release. If not, the revert commit appears under the "Reverts" header.

```
revert: feat(compiler): add 'comments' option

This reverts commit 667ecc1654a317a13331b17617d973392f415f02.
```

## [详情](https://github.com/hzh100/git-commit-commitizen)


# Git Hooks(钩子)
> [source](https://git-scm.com/book/zh/v2/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-Git-%E9%92%A9%E5%AD%90) 

钩子都被存储在 `Git` 目录下的 `hooks` 子目录中。 也即绝大部分项目中的 `.git/hooks` 。 当你用 `git init` 初始化一个新版本库时，`Git` 默认会在这个目录中放置一些示例脚本。这些脚本除了本身可以被调用外，它们还透露了被触发时所传入的参数。 所有的示例都是 shell 脚本，其中一些还混杂了 `Perl` 代码，不过，任何正确命名的可执行脚本都可以正常使用 —— 你可以用 `Ruby` 或 `Python`，或其它语言编写它们。 这些示例的名字都是以 `.sample` 结尾，如果你想启用它们，得先移除这个后缀。

### Git 钩子 分为 客户端钩子，服务端钩子
学习客户端常用钩子

**`pre-commit`** 钩子在键入提交信息前运行。 它用于检查即将提交的快照，例如，检查是否有所遗漏，确保测试运行，以及核查代码。 如果该钩子以非零值退出，Git 将放弃此次提交，不过你可以用 git commit --no-verify 来绕过这个环节。 你可以利用该钩子，来检查代码风格是否一致（运行类似 lint 的程序）、尾随空白字符是否存在（自带的钩子就是这么做的），或新方法的文档是否适当。

**`prepare-commit-msg`** 钩子在启动提交信息编辑器之前，默认信息被创建之后运行。 它允许你编辑提交者所看到的默认信息。 该钩子接收一些选项：存有当前提交信息的文件的路径、提交类型和修补提交的提交的 SHA-1 校验。 它对一般的提交来说并没有什么用；然而对那些会自动产生默认信息的提交，如提交信息模板、合并提交、压缩提交和修订提交等非常实用。 你可以结合提交模板来使用它，动态地插入信息。

**`commit-msg`** 钩子接收一个参数，此参数即上文提到的，存有当前提交信息的临时文件的路径。 如果该钩子脚本以非零值退出，Git 将放弃提交，因此，可以用来在提交通过前验证项目状态或提交信息。 在本章的最后一节，我们将展示如何使用该钩子来核对提交信息是否遵循指定的模板。

**`post-commit`** 钩子在整个提交过程完成后运行。 它不接收任何参数，但你可以很容易地通过运行 git log -1 HEAD 来获得最后一次的提交信息。 该钩子一般用于通知之类的事情。

---

### 安装 `yorkie` 或者 `husky` 注册 git hooks

### Example
*安装yorkie*`

  1. 在项目 ` .git/hooks `目录下：

    ```js
      applypatch-msg            post-applypatch           post-rewrite              pre-auto-gc               pre-rebase                prepare-commit-msg.sample
      applypatch-msg.sample     post-checkout             post-update               pre-commit                pre-rebase.sample         push-to-checkout
      commit-msg                post-commit               post-update.sample        pre-commit.sample         pre-receive               sendemail-validate
      commit-msg.sample         post-merge                pre-applypatch            pre-push                  pre-receive.sample        update
      fsmonitor-watchman.sample post-receive              pre-applypatch.sample     pre-push.sample           prepare-commit-msg        update.sample

    ```

  2. 在 package.json 文件中配置git hooks:

    ```bash
      "gitHooks": {
        "pre-commit": "str=hello; echo $str, message --- pre-commit",
        "commit-msg": "node scripts/verify-commit-msg.js"
      }

    ```

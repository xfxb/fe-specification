# gitflow-工作流windows安装配置及初始化项目

- 复制安装[命令][1]到本地

- 执行该命令安装：`./gitflow.sh install stable`

- 进入项目根目录: `cd project-name`

- 初始化项目分支约定： `git flow init` (全部回车，按照默认设定即可)


输出实例：

```bash
$ git flow init
Branch name for "next release" development: [develop]

How to name your supporting branch prefixes?
Feature branches? [feature/]
Bugfix branches? [bugfix/]
Release branches? [release/]
Hotfix branches? [hotfix/]
Support branches? [support/]
Version tag prefix? []
Hooks and filters directory? [E:/git-test/.git/hooks]

```

## git flow 子命令（git flow help查看）

```doc
   init      Initialize a new git repo with support for the branching model.
   feature   Manage your feature branches.
   bugfix    Manage your bugfix branches.
   release   Manage your release branches.
   hotfix    Manage your hotfix branches.
   support   Manage your support branches.
   version   Shows version information.
   config    Manage your git-flow configuration.
   log       Show log deviating from base branch.

   Try 'git flow <subcommand> help' for details. 查看子命令的用法

```



## 参考

[git-flow 备忘清单][2]

[git-flow 的工作流程][4]

[gitflow 官方库地址][3]


[1]:https://raw.githubusercontent.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh "windows 安装 git flow命令"
[2]:http://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html "git-flow 备忘清单"
[3]:https://github.com/petervanderdoes/gitflow-avh "gitflow 官方库地址"
[4]:https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow "git-flow 的工作流程"
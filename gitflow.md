# gitflow-工作流

## windows安装配置

- 复制安装[命令][1]到本地

- 执行该命令安装：`./gitflow.sh install stable`

## 初始化项目

- 进入项目根目录: `cd project-name`

- 初始化项目分支约定： `git flow init` (全部回车，按照默认设定即可)

输出示例：

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

gitflow的一个命令相当于是git的几个命令的集合，通过一系列动作完成一项任务。

```doc
   init      Initialize a new git repo with support for the branching model.  初始化一个新git仓库，使其支持gitflw分支模型
   feature   Manage your feature branches. 
   bugfix    Manage your bugfix branches.
   release   Manage your release branches.
   hotfix    Manage your hotfix branches.
   support   Manage your support branches.
   version   Shows version information.
   config    Manage your git-flow configuration.
   log       Show log deviating from base branch.

   Try 'git flow <subcommand> help' for details. 查看子命令的用法

   $ git flow feature help # 查看所有的子命令。每个分支命令(eg: feature, hotfix)的动作命令(eg: start, finish) 几乎是一样的。
   例如：
   usage: git flow feature [list]
   or: git flow feature start  // 创建feature分支
   or: git flow feature finish // 完成feature分支
   or: git flow feature publish //将本地feature分支发布到远程仓库
   or: git flow feature track // 设置跟踪
   or: git flow feature diff
   or: git flow feature rebase
   or: git flow feature checkout
   or: git flow feature pull
   or: git flow feature delete // 删除feature分支

    Manage your feature branches.

    For more specific help type the command followed by --help


```

## 开发人员发起 pull request

`feature` 分支测试通过后请求合并到 `develop` 分支
`hotfix` 分支测试通过后请求合并到 `master` 分支

``

## 参考

[git-flow 备忘清单][2]

[git-flow 的工作流程][4]

[gitflow 官方库地址][3]


[1]:https://raw.githubusercontent.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh "windows 安装 git flow命令"
[2]:http://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html "git-flow 备忘清单"
[3]:https://github.com/petervanderdoes/gitflow-avh "gitflow 官方库地址"
[4]:https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow "git-flow 的工作流程"
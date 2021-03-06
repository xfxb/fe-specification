# gitflow-工作流

## windows安装配置

- 复制安装[命令][1]到本地

- 执行该命令安装：`./gitflow.sh install stable`

## OSX安装配置

- 执行`brew install git-flow-avh`

## 开发功能(feature)

[master]

- 创建feature分支：`git flow feature start -F feature-branch-name`
- 合并feature分支到 develop 分支：`git flow feature finish`
- 创建release分支：`git flow release start Vx.x.x`
- release分支提测后, 发布release分支：`git flow release finish -F -T Vx.x.x -p -m 'tag message'`

[developer]

- 基于`feature-branch-name`创建自己的功能分支：`git fetch && git checkout  feature/feature-branch-name && git flow feature start -F  yourself-branch-name  feature/feature-branch-name`
- [你可能会用到其他人的功能或者模块等]。这种情形处理方式: 待其他人合并请求更新`origin/feature/feature-branch-name`之后, 然后更新自己本地开发分支：`git fetch && git rebase  feature/feature-branch-name`
- 合并请求到 feature 总分支

## 修复release分支bug(bugfix)

[developer]

- 基于 release 分支创建 bugfix 分支：`git fetch && git checkout  release/Vx.x.x && git flow bugfix start yourself-branch-name release/Vx.x.x`
- 推送bugfix分支到远程： `git flow bugfix publish`
- 合并请求到 release/Vx.x.x 分支

## 修复线上bug(hotfix)
  
[developer]:

1. 创建自己的bug分支：`git flow hotfix start -F your-branch-name`
2. bug修复之后，把本地分支提交远程仓库：`git flow hotfix publish`
3. 发提测邮件
4. 测试通过后，在远程库发起合并请求：pr `hotfix/your-branch-name` to `master`

[master]:

1. 收到合并请求后，审核代码
2. 打标签发布：
- `git fetch && git checkout hotfix/branch-name`
- `git flow hotfix finish -F -T v1.1.15 -p -m 'tag message'`
    Summary of actions:(这一句命令做了什么事)
    - Latest objects have been fetched from 'origin'
    - Hotfix branch 'hotfix/cys_phone_check_20180605' has been merged into 'master'
    - The hotfix was tagged 'v1.1.15'
    - Hotfix tag 'v1.1.15' has been back-merged into 'develop'
    - Hotfix branch 'hotfix/cys_phone_check_20180605' has been locally deleted; it has been remotely deleted from 'origin'
    - 'develop', 'master' and tags have been pushed to 'origin'
    - You are now on branch 'develop'

打标签时，可能不知道下一个版本号是什么，可以通过查看现有标签列表，来决定下一个版本号。

查看标签列表：`git tag --column --sort=-v:refname`

## 标签命名规则

版本和Tag的命名规范
基本的版本命名规则(针对Java ,  POM里面有对应的版本字段)

- 使用x.x.x进行定义
- 第一个x代表大版本只有在项目有重大变更时更新
- 第二个x代表常规版本有新需求会更新
- 第三个x代表紧急BUG修正
- 如进销存重构一期发布版命名为:   1.0.0  
- 因为我们变异使用的是jar包依赖, 所以，这个版本号的管理很重要

Tag 命名规则

- ”V”+版本号+版本类型+序号+ “_” +日期
- 版本类型:  A(alpha), 内部测试版;  R(Release), 发布版, 用来tag那些离上线很近的版本;  P(Patch)补丁版。 针对正常的小需求，一般不需要打Alpha版本, 而是直接打Release版本, 因为这样可以少测试一次(因为每次打tag 都会触发自动构建, 所以打的每一个tag都需要测试)。
- 如 V1.0.0A01_20180901  说明: V1.0.0 内测版第一次发布(序号从01开始,表示是一个基线版本)， 并且于2018年9月1号构建
- P01的P(Pathc)额外注明这是个补丁, 和x.x.x第三个x表示相同的意思. 

以后构建代码是统一使用标签构建，不使用分支，所以每次有代码改动，需要打标签后，再给测试构建。

**现在由于我们没有严格区分不同的阶段，所以统一以A后缀使用**

eg: `V1.0.1A01_20190101`; `V1.0.1`: 可以理解为产品/需求版本，`A01`: 可以理解我构建次数(第二次打标签构建就是A02，一次递增)`20190101`：当前打标签时间

给当前HEAD打标签命令: `git tag -a V1.0.1A01_20190101 -m 'fix: some bugs'`

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

    $ git flow hotfix finish --help # 查看动作命令用法
    usage: git flow hotfix finish [-h] [-F] [-s] [-u] [-m | -f ] [-p] [-k] [-n] [-b] [-S] <version>

    Finish hotfix branch <version>

    -h, --help            Show this help
    --showcommands        Show git commands while executing them
    -F, --[no]fetch       Fetch from origin before performing finish
    -s, --[no]sign        Sign the release tag cryptographically
    -u, --[no]signingkey  Use the given GPG-key for the digital signature (implies -s)
    -m, --[no]message     Use the given tag message
    -f, --[no]messagefile ...
                          Use the contents of the given file as tag message
    -p, --[no]push        Push to origin after performing finish
    -k, --[no]keep        Keep branch after performing finish
    --[no]keepremote      Keep the remote branch
    --[no]keeplocal       Keep the local branch
    -D, --[no]force_delete
                          Force delete hotfix branch after finish
    -n, --[no]notag       Don't tag this hotfix
    -b, --[no]nobackmerge
                          Don't back-merge master, or tag if applicable, in develop
    -S, --[no]squash      Squash hotfix during merge
    -T, --tagname         Use given tag name


```

## 常见问题

### 1. `error: There was a problem with the editor 'vi'.Not committing merge; use 'git commit' to complete the merge.`

   运行`git config --global core.editor $(which vim)`可以解决

## 参考

[git-flow 备忘清单][2]

[git-flow 的工作流程][4]

[gitflow 官方库地址][3]

[gitlab 内部培训文档][5]

[gitflow 参数说明文档][6]


[1]:https://raw.githubusercontent.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh "windows 安装 git flow命令"
[2]:http://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html "git-flow 备忘清单"
[3]:https://github.com/petervanderdoes/gitflow-avh "gitflow 官方库地址"
[4]:https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow "git-flow 的工作流程"
[5]:https://zhangmengpl.gitbooks.io/gitlab-guide/content/index.html "gitlab 内部培训文档"
[6]:https://github.com/petervanderdoes/gitflow-avh/wiki "gitflow 参数说明文档"

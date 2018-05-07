# 多账号免密登录不同git仓库

## 配置步骤

1. 使用`ssh-keygen`命令生成key pair(公钥和私钥)

    ```bash
    ssh-keygen -t rsa -C YourEmail
    # "-t rsa"表示使用密钥的加密类型；
    # -C 设置注释,一般写你对应git的注册邮箱，也可以写其他邮箱

    # 输入命令后会出现以下对话
    # Enter file in which to save the key (/Users/faner/.ssh/id_rsa): #设置私钥文件名字。 eg: github（若不指定目录，就在当前目录生成）
    # Enter passphrase (empty for no passphrase):                     # 输入密钥文件授权密码，不用设置 直接回车
    # Enter same passphrase again:                                    # 确认密钥文件授权密码，不用设置 直接回车
    # Your identification has been saved in /Users/faner/.ssh/id_rsa.
    # Your public key has been saved in /Users/faner/.ssh/id_rsa.pub.

    # 重复以上步骤生成多对 ssh key。
    ```

2. 复制公钥到git服务器上的ssh keys设置的地方
3. 进入用户 `home` 目录下的 `.ssh`：`cd ~/.ssh`
4. 配置 `config`。请参考下面我的配置格式。


## 我的配置

- 目录结构

```tree
./ssh
├── config
├── github
├── github.pub
├── id_rsa
├── id_rsa.pub
└── known_hosts
```

- config文件内容

```ini
# 配置gitlab.blissmall.net
Host gitlab.blissmall.net
    HostName gitlab.blissmall.net
    IdentityFile C:\Users\win7\.ssh\id_rsa
    PreferredAuthentications publickey
    User yangyongpeng

# 配置github.com
Host github.com
    HostName github.com
    IdentityFile C:\Users\win7\.ssh\github
    PreferredAuthentications publickey
    User bugknightyyp
```

## 注意事项

git 使用的是
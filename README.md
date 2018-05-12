# fe-specification

幸福西饼前端基本规范

## vscode 编辑器

vscode有四个等级的配置，优先级依次是：

文件设置 > 工作区设置 > 用户设置 > 编辑器默认设置

项目的基本设置我们放在用户设置，具体设置项如下：

```json

```

使用 `.editorconfig` 统一团队代码风格问题,解决缩进及行长问题。[参考][1]

```ini
# EditorConfig is awesome: http://EditorConfig.org

# top-most EditorConfig file
root = true

# Unix-style newlines with a newline ending every file
[*]
end_of_line = lf
insert_final_newline = true

# Matches multiple files with brace expansion notation
# Set default charset
[*.{js,py}]
charset = utf-8

# 4 space indentation
[*.py]
indent_style = space
indent_size = 4

# Tab indentation (no size specified)
[Makefile]
indent_style = tab

# Indentation override for all JS under lib directory
[lib/**.js]
indent_style = space
indent_size = 2

# Matches the exact files either package.json or .travis.yml
[{package.json,.travis.yml}]
indent_style = space
indent_size = 2
```

## 语法

es / typescript

## 代码

- ESlint
- 不要出现魔法字符串

## 命名

- 样式

1. less/sass variable

- js

## 文档

## 其他

[1]:http://editorconfig.org/
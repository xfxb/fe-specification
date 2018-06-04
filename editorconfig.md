# editorconfig

editorconfig是一个跨编辑器统一编码格式的开源项目。解决团队内使用不同编辑器情形下，统一编码格式。

将配置文件 `.editorconfig` 放在项目根目录下，配置内容如下，然后在不同编辑器里安装对应的 `editorconfig` 的插件即可，插件会把配置项转成不同编辑器的对应项。

`.editorconfig` 配置：

```ini
# http://editorconfig.org
root = true

[*]
indent_style = space # 缩进风格
indent_size = 2 # 缩进大小
# end_of_line = lf
charset = utf-8 # 编码
trim_trailing_whitespace = true # 截取
insert_final_newline = true # 表示行末是否保留空格
max_line_length = 120 # 最大行长

[*.md]
trim_trailing_whitespace = false

[Makefile]
indent_style = tab

```

## vscode 的配置

vscode有四个等级的配置，优先级依次是：

文件设置 > 工作区设置 > 用户设置 > 编辑器默认设置

我们是放在工作区（存放目录 project-name/.vscode/settings.json）来统一代码格式化

这只是基本项,每个项目可以针对项目需求添加所需配置。

这个是vscode 对应的配置项

```json
{
  "editor.detectIndentation": false, //关闭自动探测缩进方式
  "editor.tabSize": 2, // 一个制表符等于2个空格
  "editor.wordWrap": "wordWrapColumn",//换行方式为 超过 配置的列（wordWrapColumn） 就换行发的发生 第三方的
  "editor.wordWrapColumn": 120,
  "files.insertFinalNewline": true, // 自动在文件末尾插入新行
  "files.eol": "\r\n",
}
```

## 参考

[editorconfig官网][1]

[editorconfig所有配置属性][2]

[vscode 设置文档](https://code.visualstudio.com/docs/getstarted/settings)

[1]:http://editorconfig.org/ "editorconfig官网"
[2]:https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties "editorconfig所有配置属性"

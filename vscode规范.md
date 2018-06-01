# vscode 编辑器规范

vscode有四个等级的配置，优先级依次是：

文件设置 > 工作区设置 > 用户设置 > 编辑器默认设置

我们是放在工作区（存放目录 project-name/.vscode/settings.json）来统一代码格式化。

这只是基本项,每个项目可以针对项目需求添加所需配置。

```json
{
  "editor.detectIndentation": false, //关闭自动探测缩进方式
  "editor.tabSize": 2, // 一个制表符等于2个空格
  "editor.wordWrap": "wordWrapColumn",//换行方式为 超过 配置的列（wordWrapColumn） 就换行发的发生 第三方的
  "editor.wordWrapColumn": 120,
  "files.insertFinalNewline": true, // 自动在文件末尾插入新行
  "files.eol": "\n", // 默认行尾字符。使用 \n 表示 LF，\r\n 表示 CRLF。
}
```

项目里会自带关于vscode 的配置，如果你是基于其他编辑器，请自行设置对等的配置。

## 参考

[vscode 设置文档](https://code.visualstudio.com/docs/getstarted/settings)

[1]:http://editorconfig.org/

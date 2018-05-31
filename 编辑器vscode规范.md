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
  "editor.wordWrapColumn": 80,
  "files.insertFinalNewline": true, // 自动在文件末尾插入新行
}
```

## 参考

[vscode 设置文档](https://code.visualstudio.com/docs/getstarted/settings)

[1]:http://editorconfig.org/

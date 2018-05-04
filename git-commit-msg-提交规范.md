# Git commit日志基本规范

规范提交日志，统一团队习惯，方便代码审查，版本控制，自动生成发布日志等,

> 日志基本格式：

---

```document
<type>[optional scope]: <description>
(这是里空行)
[optional body]
(这是里空行)
[optional footer]
```

---

`<>` 表示必填，`[]` 表示选填。

**type**: 表示`commmit`的类型。必须是以下任意种：\

- build: 影响构建系统或者外部依赖（比如受影响的范围是webpack, gulp, npm等）

- ci: 持续冀衡， 改变CI

- docs: 只修改了文档。如 `README` 以及文档等说明性文件

- feat: 新增功能

- fix: 修复bug

- refactor: 

- perf: 性能、体验等优化

- style: 比如只涉及空格、缩进、换行等只是格式化文件，不修改代码

- test: 测试相关的，修改添加测试用例，集成测试等

当使用命令 `git commit` 时，会弹出commit message 编辑器，可以按照上述格式进行编辑。

## 参考

[Conventional Commits 1.0.0-beta.1][1]

[谷歌angular commit msg 规范][2]


[1]:https://conventionalcommits.org/ "Conventional Commits 1.0.0-beta.1"
[2]:https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit "谷歌angular commit msg 规范"
[3]:hhttp://www.feflowjs.org/zh-cn/docs/permalinks.html "feflow Git提交规范"
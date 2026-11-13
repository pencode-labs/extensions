# pencode extensions

The official extension registry for [pencode](https://github.com/pencode-labs/pencode).

This repository maintains the list of available pencode extensions in [`extensions.json`](./extensions.json).

## JSON API

The registry is published automatically from `main` to GitHub Pages:

- Homepage: https://pencode-labs.github.io/extensions/
- Extension list: https://pencode-labs.github.io/extensions/extensions.json

Fetch the list with a public, unauthenticated HTTP GET request:

```sh
curl --fail https://pencode-labs.github.io/extensions/extensions.json
```

```js
const response = await fetch("https://pencode-labs.github.io/extensions/extensions.json");
if (!response.ok) throw new Error(`Registry request failed: ${response.status}`);
const { extensions } = await response.json();
```

The response contains an `extensions` array. Each entry has `name`, `repository`,
and `description` fields. The endpoint serves the same `extensions.json` maintained
in this repository.

## Available extensions

| Extension | Description |
| --- | --- |
| [php](https://github.com/pencode-labs/php) | 为 PHP 和 Blade 模板提供代码补全、错误诊断、定义跳转、引用查找、重命名与格式化。集成 Xdebug 调试，支持运行当前 PHP 文件或监听外部请求，查看断点、调用栈和变量。 |
| [codex](https://github.com/pencode-labs/codex) | 在编辑器中与 Codex 对话，阅读代码、修改文件并执行命令。支持流式回复、文件变更对比、历史会话恢复，以及模型、推理强度和操作权限设置。 |
| [go](https://github.com/pencode-labs/go) | 通过 gopls 提供 Go 代码补全、错误诊断、定义跳转、引用查找、重命名与格式化。集成 Delve 调试，支持断点、单步执行、调用栈和变量查看，并自动安装缺失工具。 |
| [ui-demo](https://github.com/pencode-labs/ui-demo) | 面向扩展开发者的交互示例，演示菜单、对话框、浮窗、面板与通知的使用。包含表单输入、扩展设置和界面生命周期事件，便于了解和验证 Pencode 扩展 UI 能力。 |
| [material-icons](https://github.com/pencode-labs/material-icons) | 为文件和文件夹提供 Material Design 风格图标，根据文件名、扩展名和目录名匹配语言、工具及项目图标，让项目结构更直观、常用文件更易辨认。 |
| [markdown-preview](https://github.com/pencode-labs/markdown-preview) | 实时预览 Markdown 文档，可独立打开或与源码分栏显示，编辑后自动更新。支持表格、代码块、图片与链接，方便编写和检查项目文档。 |
| [docker](https://github.com/pencode-labs/docker) | 从标题栏管理 Docker 容器，启动、停止、重启容器并查看自动刷新的日志。 |
| [office-viewer](https://github.com/pencode-labs/office-viewer) | 本地只读预览 Word、Excel 和 PowerPoint 文件，支持工作表切换、连续滚动、文本选择复制、搜索与幻灯片浏览。 |

## Adding an extension

Open a PR that adds an entry to `extensions.json`, following the existing format.

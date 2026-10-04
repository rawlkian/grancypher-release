# Chrome 扩展插件（实验）

在设置中启用 Chrome 扩展支持，并添加包含 `manifest.json` 的解包插件文件夹。插件管理中可以调整网站访问范围、可选权限及工具区图标。重新加载后会使用源文件夹的新内容。

## 为什么需要逐项适配

Grancypher 基于 WebView2 构建。扩展依赖的标签页、权限、后台通信、书签和音频，需要与 Grancypher 的窗口及数据连接，并在弹出窗口、后台 worker 和 offscreen 文档中保持一致的接口行为。适配采用通用 Chrome 接口，让使用同类接口的插件复用已有能力；WebView2 未提供的能力需要另行实现，扩展支持仍为实验功能。

## 读取书签

声明并获准 `bookmarks` 权限的扩展可以通过 `chrome.bookmarks.getTree`、`getSubTree`、`getChildren`、`get`、`search` 读取当前账户书签，包括未固定在侧栏的项目、文件夹层级和同级顺序。可选权限需要在插件管理中授予。Shortkeys 的书签选择器也可以使用这些数据。

目前提供只读接口；书签修改、历史创建时间和变更事件尚未适配。接口遵循 [Chrome bookmarks API](https://developer.chrome.com/docs/extensions/reference/api/bookmarks)。

## 音量和静音

使用 Volume Master 等音量扩展时，先点击工具区的插件入口，为当前网页授予捕获授权，再在插件界面调整音量。支持通过标准 `tabCapture` 接口取得真实网页音频，以及通过 `tabs.update` 控制网页静音。同网址的两个网页分别识别，可独立授权及静音；停止音轨或停用插件后释放捕获，重载和跨站导航撤销旧授权。

音频捕获支持 callback、Promise、状态查询和状态事件。目前提供音频捕获，不支持视频、`consumerTabId` 和附加音频约束；本地 WebRTC 传输存在编码与延迟差异。音频字段的 `tabs.onUpdated` 事件尚未桥接。接口参见 [Chrome tabCapture API](https://developer.chrome.com/docs/extensions/reference/api/tabCapture)。

内置用户脚本声明 `@grant GM.audio` 或 `@grant GM_audio` 后，可以调用静音、状态读取及状态变化监听接口，静音包含 HTML 媒体和 Web Audio 输出。两份 GBF 静音脚本示例可从 [v0.4.4 附件](https://github.com/rawlkian/grancypher-release/releases/tag/v0.4.4) 下载，按需要选择一份使用。

## 菜单与置顶窗口

侧栏右键菜单和“更多”菜单会临时显示在太郎等置顶窗口上方。关闭菜单后恢复原层级，窗口的永久置顶设置继续由用户控制。

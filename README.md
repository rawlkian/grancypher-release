<p align="center">
  <img src="assets/banner.svg" alt="Grancypher — 碧蓝幻想桌面浏览器" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Windows-x64-4aa3df?style=flat-square&amp;logo=windows&amp;logoColor=white" alt="Windows x64">
  <img src="https://img.shields.io/badge/.NET-10-8067c8?style=flat-square&amp;logo=dotnet&amp;logoColor=white" alt=".NET 10">
  <img src="https://img.shields.io/badge/Engine-WebView2-48b6ac?style=flat-square" alt="WebView2">
  <img src="https://img.shields.io/badge/Language-简中%20%7C%20繁中%20%7C%20EN%20%7C%20日本語-8fabc5?style=flat-square" alt="四种界面语言">
</p>

<p align="center">
  <b>陪伴骑空士的每一次出航。</b><br>
  专注游戏本身，管理不同账户，让常用操作顺手可达。
</p>

<p align="center">
  <a href="https://github.com/rawlkian/grancypher-release/releases/latest"><b>下载最新版</b></a>
  &nbsp; · &nbsp;
  <a href="https://github.com/rawlkian/grancypher-release/releases">更新记录</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/rawlkian/grancypher-release/issues">问题反馈</a>
</p>

---

## 关于 Grancypher

Grancypher 是面向《碧蓝幻想》的 Windows 桌面浏览器，采用原生 WinUI 3 界面和 Microsoft Edge WebView2 引擎。

本仓库用于提供安装包、绿色便携版、更新说明和用户反馈入口。

## 下载与开始使用

前往 **[Releases 下载页](https://github.com/rawlkian/grancypher-release/releases)**，在最新版本的 **Assets** 中选择：

| 版本 | 文件名称 | 使用方式 |
| --- | --- | --- |
| 绿色便携版 | `Grancypher-v版本号-Portable-win-x64.zip` | 解压到可写目录，运行 `Grancypher.exe`；请保留整个文件夹 |
| 安装版 | `Grancypher-v版本号-Setup-win-x64.exe` | 按向导安装到当前用户，无需管理员权限 |
| 校验文件 | `SHA256SUMS-v版本号.txt` | 用于核对下载文件的 SHA-256 值 |

### 首次运行准备

支持 **Windows 10 1809 及以上版本、Windows 11，x64 环境**。发行包未捆绑以下运行组件；已安装的组件无需重复安装：

| 组件 | 版本要求 | 官方入口 |
| --- | --- | --- |
| .NET Runtime | .NET 10，x64 | [下载 .NET](https://dotnet.microsoft.com/download/dotnet/10.0) |
| Windows App SDK Runtime | 2.5.1，x64 | [微软下载页](https://learn.microsoft.com/windows/apps/windows-app-sdk/downloads) |
| Visual C++ Redistributable | x64 | [下载运行库](https://aka.ms/vc14/vc_redist.x64.exe) |
| Microsoft Edge WebView2 Runtime | Evergreen | [下载 WebView2](https://developer.microsoft.com/microsoft-edge/webview2/) |

包内的 `Prerequisites.txt` 也包含这些说明。安装组件后打开 Grancypher，跟随首次运行向导完成设置即可。

## 让桌面游玩更顺手

| 功能 | 体验 |
| --- | --- |
| **专注游戏画面** | 自动裁切与画面适配，支持同一窗口中的双浏览器视图 |
| **独立账户配置** | 设置、Cookies 与窗口位置分别记忆；从账户菜单打开多个实例 |
| **灵活书签栏** | 侧栏聚合、悬浮、顶部或底部布局；支持图标模式、多行显示和大小调整 |
| **键盘与鼠标快捷键** | 支持右键、中键、Mouse4 / Mouse5 和修饰键组合；同一功能可设置多组快捷键 |
| **速达入口** | 右键保存当前网址，左键或快捷键即可跳转 |
| **主题与材质** | 亮色、暗色、强调色，配合 Mica / 亚克力效果与可调侧栏宽度 |
| **太郎与用户脚本** | 加载本地太郎扩展，管理 `.user.js` 脚本，支持太郎窗口吸附与尺寸记忆 |
| **Chrome 插件（实验）** | 加载解包插件，管理权限与工具区图标；自定义指针按网页生效的 CSS 样式同步，支持悬停图像、热点和图片回退 |
| **配置备份与诊断** | 用户配置、书签分别备份；Debug 模式跨重启持续记录日志 |

界面支持简体中文、繁体中文、英语与日语。

## 账户、Cookies 与缓存

工具区最上方的账户按钮可新建配置、用已有配置打开新窗口，或删除不用的账户。默认配置和正在使用的配置会受到保护。

## 太郎与用户脚本

在“设置 → 太郎”中选择解压后的扩展目录，目录顶层应包含 `manifest.json`。启用后使用工具区的太郎入口打开窗口。

太郎窗口支持记忆尺寸与吸附，实时战斗数据桥接目前需要太郎窗口保持打开。WebView2 与 Chrome 的扩展接口有差异，兼容表现可能随插件版本变化。

用户脚本可从设置中添加、启停、重新读取或删除。脚本提供的菜单命令会显示在工具区“更多 → 用户脚本”。目前尚未实现全部 Tampermonkey `GM_*` 接口。

## 遇到问题时

1. 在工具区“更多”中开启 **Debug 模式**。
2. 重现问题；即使关闭并重新启动程序，Debug 记录仍会继续。
3. 手动关闭 Debug 模式，按提示打开日志文件或所在文件夹。
4. 前往 **[Issues](https://github.com/rawlkian/grancypher-release/issues/new)**，附上程序版本、Windows / WebView2 版本、复现步骤，以及相关日志。

Debug 文件位于当前用户配置目录的 `Logs/debug.log`。分享日志或截图前，请检查其中是否包含不希望公开的账号名称、邮箱或本机路径。

<details>
<summary><b>常见问题</b></summary>

**绿色版是否完全不需要安装组件？**

程序本身免安装，但仍依赖上面的运行组件。运行前可先查看包内 `Prerequisites.txt`。

**为什么修改代理或缓存位置后需要重启？**

这些设置需要在创建浏览器环境时生效，程序会提示并协助重启。

**鼠标还有更多侧键，可以使用吗？**

Windows 原生提供 Mouse4 / Mouse5。其它厂商侧键可在鼠标驱动中映射成键盘按键，再录入快捷键设置。

**是否包含自动更新？**

支持。默认启动时检查正式版，发现新版会显示版本与更新内容。选择“更新”开始下载和校验，安装前再次确认；“跳过此版本”按账户保存，同一版本不再提醒，出现新版本仍会提醒；“我知道了”仅关闭窗口，下次启动仍可提醒。可在“更多 → 关于”关闭启动检查或手动检查更新，跳过版本不影响手动更新。

</details>

---

<p align="center">
  <sub>Grancypher 为非官方应用，与 Cygames 无隶属关系。游戏名称与相关素材的权利属于各自权利人。</sub>
</p>

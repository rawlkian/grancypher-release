---
hide:
  - toc
---

<div class="skybound-hero">
<div class="skybound-eyebrow">GRANCYPHER · 1.0.0 BETA</div>
<h1>Grancypher 使用手册</h1>
<p>专为《碧蓝幻想》设计的桌面浏览器。</p>
<div class="skybound-actions"><a href="https://github.com/rawlkian/grancypher-release/releases/tag/v1.0.0">下载 1.0.0 内测版</a><a class="secondary" href="getting-started/">首次使用</a></div>
</div>

!!! warning "旧版升级说明"
    1.0.0 为内测版，已更换浏览器内核与界面框架。**此次无法通过旧版程序内自动更新。** 请前往 [GitHub Release](https://github.com/rawlkian/grancypher-release/releases/tag/v1.0.0) 下载完整安装包或便携包，按照[升级说明](updates.md)重新安装。

<div class="grid cards" markdown>

- **安装与迁移**

    Windows x64 环境要求、安装版与便携版、旧版数据备份。

    [安装说明](install.md) · [升级说明](updates.md)

- **窗口与外观**

    Skybound 主题、双视图、自适应画面、侧栏和悬浮书签。

    [外观与设置](features/settings.md) · [侧栏](features/sidebar.md)

- **账户与资源**

    独立账户配置、共享静态资源缓存、缓存检查与版本清理。

    [账户配置](features/multi-user.md) · [本地缓存](features/local-cache.md)

- **扩展与诊断**

    Chrome 扩展、用户脚本、网络检测与环境报告。

    [扩展](features/chrome-extensions.md) · [故障排查](diagnostics.md)

</div>

## 版本说明

本手册适用于 **Grancypher 1.0.0 内测版**。新版使用 Qt 6 与 Chromium（CEF），发行包包含所需运行文件，无需另行安装 WebView2、.NET 或 Windows App SDK。

程序支持简体中文、繁體中文、English 和日本語。界面语言立即切换；浏览器内部菜单语言在重启后生效。

Grancypher 为非官方应用，与 Cygames 无隶属关系。内测问题请通过 [GitHub Issues](https://github.com/rawlkian/grancypher-release/issues)反馈。

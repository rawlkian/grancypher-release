# Grancypher

专为《碧蓝幻想》设计的桌面浏览器。

**当前正式版本：1.0.5（Windows x64）。** 基于 Qt 6 与 Chromium（CEF），提供 Skybound 界面、独立账户配置、双视图、书签、静态资源缓存及 Chrome 扩展支持。

## 下载与升级

- [下载 1.0.5 正式版](https://github.com/rawlkian/grancypher-release/releases/tag/v1.0.5)
- [使用手册](https://rawlkian.github.io/grancypher-release/)
- [问题反馈](https://github.com/rawlkian/grancypher-release/issues)

**1.x 用户可在“关于 Grancypher”检查并安装更新。0.x 旧版用户需要下载完整安装包或便携包，备份数据后重新安装，不要仅替换主程序文件。** 迁移步骤见[升级说明](https://rawlkian.github.io/grancypher-release/updates/)。

| 发行包 | 使用方式 |
| --- | --- |
| 安装版 EXE | 运行安装程序，按向导完成安装 |
| 便携版 ZIP | 完整解压后运行 Grancypher.exe，保留 portable.flag |

发行包包含所需运行文件，无需额外安装 WebView2、.NET 或 Windows App SDK。支持 Windows 10 1809 及更新的 x64 系统。GitHub 附件提供 SHA-256 摘要，便携包内附运行文件校验清单。

## 文档维护

本仓库保存发行附件说明与 MkDocs 文档。`docs/` 和 `mkdocs.yml` 更新后，GitHub Actions 自动构建并部署使用手册。构建依赖位于 `requirements-docs.txt`。

Grancypher 为非官方应用，与 Cygames 无隶属关系。

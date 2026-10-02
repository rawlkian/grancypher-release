<img src="img/proxy.png">

Grancypher 支持多种代理方式，目前可以使用的代理方式如下：

1. 直接连接（多用于游戏加速器，如 UU 加速器）
2. 系统设置（使用 Windows 的代理配置，多用于 Clash， V2Ray 等场景）
3. 手动设置（一般用于 Clash，V2Ray 以及岛风 Go）
4. PAC 自动代理脚本（一般用于 ACGPower）

### 岛风 Go 配置

官网的 Chrome 配置中有提到在 ZeroOmega 或者 SwitchyOmega 添加指定端口的代理地址，我们在手动设置代理地址中填入那个代理地址即可，一般默认的是 http://127.0.0.1:8099（没有更改端口的情况下）。

### ACGPower 配置

和岛风 Go 原理差不多，在 PAC 脚本地址中填写设置教程中的 PAC 文件地址即可，一般默认的为 http://127.0.0.1:8123/proxy.pac（没有更改端口的情况下）。
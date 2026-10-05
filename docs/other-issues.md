此处的问题均收集自用户实际运行中遇到的情况，可能因人而异，仅供参考。
## OpenGL 后台渲染
问题原帖：[@cy月皇 #210层回复](https://bbs.nga.cn/read.php?pid=883720561&opt=128)
Q：动画和释放技能会卡顿和迟缓。Chrome 浏览器通过在 chrome://flags 更改了 Choose ANGLE graphics backend这个选项为OpenGL，动画才顺畅。 Grancypher 如何解决此问题？
A：#224层回复 
在注册表HKEY_CURRENT_USER\Software\Policies\Microsoft\Edge\WebView2\AdditionalBrowserArguments找到Grancypher.exe项，值修改成 = “--enable-gpu-rasterization --ignore-gpu-blocklist --use-angle=gl”(不要复制双引号)。
--use-angle=gl 在 Grancypher 内已集成到实验性功能，可不加。前两个启动参数为开启 GPU 栅格化和忽略 GPU 黑名单，对大多数用户来说没有用甚至可能导致黑屏、卡顿，故 Grancypher 不内置此两条启动参数，有需要的用户请按照上面的方法手动解决。
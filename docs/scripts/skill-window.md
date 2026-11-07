# 关闭技能窗口动画

!!! note "兼容性说明"
    此页为第三方脚本示例，保留原作者信息与代码。尚未在 1.0.0 内测版逐项验证；请先阅读[用户脚本说明](feature-declaration.md)。

## 脚本来源
AI 编写。

## 功能介绍
关闭战斗界面点击人物头像打开技能窗口的动画及左右切换动画。

## 脚本内容
```javascript
// ==UserScript==
// @name         GBF Disable Battle Animations
// @namespace    gbf
// @version      1.0
// @description  Disable UI transition animations in Granblue Fantasy
// @match        https://game.granbluefantasy.jp/*
// @match        http://game.granbluefantasy.jp/*
// @run-at       document-start
// ==/UserScript==

(function () {
    'use strict';

    const style = document.createElement('style');

    style.textContent = `
        * {
            transition-duration: 0s !important;
            transition-delay: 0s !important;
            animation-duration: 0s !important;
            animation-delay: 0s !important;
        }
    `;

    document.documentElement.appendChild(style);
})();
```

## 使用说明
直接加载后刷新一次读入用户脚本即可。
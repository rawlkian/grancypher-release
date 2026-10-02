## 脚本来源
未知，如知道作者信息可联系我。

## 功能介绍
该用户脚本在玩家完成 Boss 击杀后，自动跳转至结算页面，并再次跳转到支援召唤石选择界面，以达成快速周回的目的。

## 脚本内容
```javascript
// ==UserScript==
// @name         自动周回跳转
// @match        https://game.granbluefantasy.jp/*
// ==/UserScript==

(function() {
    'use strict';

    let executed = false;

    const targetName = "Lv50 オール・モレース";
    const redirectUrl = "https://game.granbluefantasy.jp/#quest/supporter/947431/1/0/10674";

    function checkElements() {
        const nameDiv = document.querySelector('div.name');
        const attackBtn = document.querySelector('div.btn-attack-start.display-off');
        const turninfo = document.querySelector('div.num-turn1');

        if (nameDiv && attackBtn && turninfo &&
            nameDiv.textContent.trim() === targetName &&
            !executed
        ) {
            executed = true;
            triggerRedirects();
        }
    }

    function triggerRedirects() {
        const firstDelay = Math.floor(Math.random() * 11) + 50;
        const secondDelay = Math.floor(Math.random() * 51) + 550;

        setTimeout(() => {
            window.location.href = redirectUrl;
            console.log(`首次跳转，延迟 ${firstDelay}ms`);

            setTimeout(() => {
                window.location.href = redirectUrl;
                console.log(`二次跳转，总延迟 ${firstDelay + secondDelay}ms`);
            }, secondDelay);
        }, firstDelay);
    }

    // 使用 MutationObserver 监听 DOM 变化
    const observer = new MutationObserver(mutations => {
        checkElements();
    });

    observer.observe(document, {
        childList: true,
        subtree: true
    });

    checkElements();
})();
```
## 使用说明
将`const targetName =`后的常量文本更改为需要自动周回跳转的 Boss 名（在战斗界面通过开发者工具获取）。将`const redirectUrl =`后的常量链接改为该 Boss 的选择支援召唤石页面的链接。针对不同的 Boss 可以新建多个不同的用户脚本，更改 @name 参数进行区分即可。添加用户脚本后请多次刷新页面，以加载读取脚本。
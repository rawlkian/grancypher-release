## 脚本来源

NGA用户 @Hina阳菜 编写

相关网址：https://bbs.nga.cn/read.php?pid=883528894&opt=128

## 功能说明
复制救援码后在参加救援界面点击救援码输入框自动粘贴。

## 脚本内容
```javascript
// ==UserScript==
// @name         GBF Auto Paste WebView2 Fixed
// @namespace    http://tampermonkey.net/
// @version      1.4
// @match        https://game.granbluefantasy.jp/*
// @match        http://game.granbluefantasy.jp/*
// @match        https://gbf.game.mbga.jp/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    var debug = true;
    function debugPrint(text, data) {
        if (debug) {
            console.log("[GBF AutoPaste]:", text, data !== undefined ? data : "");
        }
    }

    function insertTextAtCursor(text) {
        var el = document.querySelector("input.frm-battle-key");
        if (!el) {
            debugPrint("未找到输入框 input.frm-battle-key");
            return;
        }
        if (!text) {
            debugPrint("剪贴板内容为空");
            return;
        }

        // 强力清洗：去除所有空格、换行符、不可见字符，并转大写
        var cleanText = text.replace(/[\s\r\n]+/g, '').toUpperCase();
        debugPrint("清洗后的文本:", cleanText);

        const pattern = /^[A-Z0-9]{8}$/;
        if (pattern.test(cleanText)) {
            el.value = cleanText;
            debugPrint("成功填入救援码:", cleanText);
            
            el.dispatchEvent(new Event('input', { bubbles: true }));
            el.dispatchEvent(new Event('change', { bubbles: true }));
        } else {
            debugPrint("清洗后的文本不符合 8 位特征，原始内容长度:", cleanText.length);
        }
    }

    async function handleInputClick(e) {
        debugPrint("输入框被点击，尝试读取剪贴板...");
        try {
            if (navigator.clipboard && navigator.clipboard.readText) {
                const text = await navigator.clipboard.readText();
                insertTextAtCursor(text);
            } else {
                debugPrint("navigator.clipboard.readText 不可用");
            }
        } catch (err) {
            debugPrint("读取剪贴板捕获到错误:", err);
        }
    }

    function initObserver() {
        var obs = new MutationObserver(function() {
            var el = document.querySelector("input.frm-battle-key");
            if (el && !el.dataset.autoPasteBound) {
                el.dataset.autoPasteBound = "true";
                el.addEventListener("mousedown", handleInputClick);
                debugPrint("已成功为输入框绑定点击/按下事件");
            }
        });

        obs.observe(document.body, {
            childList: true,
            attributes: true,
            subtree: true
        });
    }

    if (document.readyState === "complete" || document.readyState === "interactive") {
        initObserver();
    } else {
        window.addEventListener("DOMContentLoaded", initObserver);
    }
})();
```
## 使用说明
直接添加脚本后在救援输入界面刷新即可，注意第一次使用需要先拉宽 Grancypher 的窗口宽度，否则弹出的剪贴板权限申请对话框会被裁切。
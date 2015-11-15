# XSS 跨網站指令碼

## 說明

跨網站指令碼（Cross-site scripting，通常簡稱為XSS或跨站指令碼或跨站指令碼攻擊）

## 如何避免 XSS

在使用者傳過的來字串中

* 去除任何 `<script>` 標籤
* 移除 `onclick`, `onerror`, `onmouseenter` ... 等等事件處理器
* 使用 HTML 黑名單或白名單的方式，留下可執行的 HTML 程式碼
* 避免連結出現 `data:text/html;base64` 的資料


## 參考資料
* [跨網站指令碼](https://zh.wikipedia.org/wiki/%E8%B7%A8%E7%B6%B2%E7%AB%99%E6%8C%87%E4%BB%A4%E7%A2%BC)
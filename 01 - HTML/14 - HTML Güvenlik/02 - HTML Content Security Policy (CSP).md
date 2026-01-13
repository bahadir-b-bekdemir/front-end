# 🛡️ HTML CONTENT SECURITY POLICY (CSP)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) CSP, XSS saldırılarını önlemek için kaynak yükleme politikaları tanımlar.

## 📋 CSP Direktifleri

| Direktif | Açıklama |
| :------- | :------- |
| `default-src` | Varsayılan kaynak politikası |
| `script-src` | JavaScript kaynakları |
| `style-src` | CSS kaynakları |
| `img-src` | Resim kaynakları |
| `connect-src` | AJAX, WebSocket kaynakları |

## 💡 Kullanım Örnekleri

### Meta Tag ile CSP

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="Content-Security-Policy" 
          content="default-src 'self'; script-src 'self' 'unsafe-inline';">
    <title>CSP</title>
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### Sıkı CSP Politikası

```html
<head>
    <meta http-equiv="Content-Security-Policy" 
          content="default-src 'self'; 
                   script-src 'self'; 
                   style-src 'self' 'unsafe-inline'; 
                   img-src 'self' data: https:;">
</head>
```

### Report-Only Modu

```html
<head>
    <meta http-equiv="Content-Security-Policy-Report-Only" 
          content="default-src 'self'; report-uri /csp-report">
</head>
```

## 🎯 Önemli Notlar

- CSP XSS saldırılarını önler
- `'self'` aynı origin'e izin verir
- `'unsafe-inline'` inline script/style'a izin verir (güvensiz)
- Report-only modu test için kullanılır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


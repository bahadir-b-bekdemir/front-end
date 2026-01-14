# 🔐 HTML HTTPS VE GÜVENLİK BAŞLIKLARI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) güvenlik başlıkları web uygulaması güvenliğini artırır.

## 📋 Güvenlik Başlıkları

| Başlık | Açıklama |
| :----- | :------- |
| HSTS | HTTP Strict Transport Security |
| X-Frame-Options | Clickjacking koruması |
| X-Content-Type-Options | MIME type sniffing koruması |
| Referrer-Policy | Referrer bilgisi kontrolü |

## 💡 Kullanım Örnekleri

### HSTS (HTTP Strict Transport Security)

```html
<head>
    <meta http-equiv="Strict-Transport-Security" 
          content="max-age=31536000; includeSubDomains; preload">
</head>
```

### X-Frame-Options

```html
<head>
    <meta http-equiv="X-Frame-Options" content="DENY">
    <!-- veya -->
    <meta http-equiv="X-Frame-Options" content="SAMEORIGIN">
</head>
```

### X-Content-Type-Options

```html
<head>
    <meta http-equiv="X-Content-Type-Options" content="nosniff">
</head>
```

### Referrer-Policy

```html
<head>
    <meta name="referrer" content="no-referrer">
    <!-- veya -->
    <meta name="referrer" content="strict-origin-when-cross-origin">
</head>
```

### Permissions-Policy

```html
<head>
    <meta http-equiv="Permissions-Policy" 
          content="geolocation=(), microphone=(), camera=()">
</head>
```

## 🎯 Önemli Notlar

- Güvenlik başlıkları HTTP header'ları ile de ayarlanabilir
- HSTS HTTPS zorunluluğu sağlar
- X-Frame-Options iframe embedding'i kontrol eder
- X-Content-Type-Options MIME type sniffing'i önler

## ✍️ Yazar

**Bahadır B. Bekdemir**


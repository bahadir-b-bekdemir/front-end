# 📋 HTML HEAD ETİKETLERİ (link, script, style, base, noscript)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) `<head>` bölümü sayfa hakkında meta bilgiler, stil dosyaları, script dosyaları ve diğer kaynakları içerir.

## 📋 Head Bölümü Etiketleri

| Etiket | Açıklama | Kullanım |
| :----- | :------- | :------- |
| `<title>` | Sayfa başlığı | Zorunlu, SEO için önemli |
| `<meta>` | Meta bilgiler | SEO, viewport, charset |
| `<link>` | Dış kaynak bağlantısı | CSS, favicon, preload |
| `<script>` | JavaScript kodu | Inline veya dış dosya |
| `<style>` | CSS kodu | Inline stil tanımları |
| `<base>` | Temel URL | Tüm bağlantılar için base URL |
| `<noscript>` | Script olmadan içerik | JavaScript kapalıysa gösterilir |

## 💡 Kullanım Örnekleri

### Temel Head Yapısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### Link Etiketi Kullanımı

```html
<head>
    <!-- CSS dosyası -->
    <link rel="stylesheet" href="styles.css">
    
    <!-- Favicon -->
    <link rel="icon" type="image/png" href="favicon.png">
    
    <!-- Preload -->
    <link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
    
    <!-- DNS Prefetch -->
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">
</head>
```

### Script Etiketi Kullanımı

```html
<head>
    <!-- Dış JavaScript dosyası -->
    <script src="app.js"></script>
    
    <!-- Inline JavaScript -->
    <script>
        console.log('Sayfa yüklendi');
    </script>
    
    <!-- Async yükleme -->
    <script src="analytics.js" async></script>
    
    <!-- Defer yükleme -->
    <script src="main.js" defer></script>
</head>
```

### Style Etiketi Kullanımı

```html
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        h1 {
            color: #333;
        }
    </style>
</head>
```

### Base Etiketi Kullanımı

```html
<head>
    <base href="https://example.com/">
    <base target="_blank">
</head>
<body>
    <!-- Tüm bağlantılar base URL'e göre çözümlenir -->
    <a href="page.html">Sayfa</a> <!-- https://example.com/page.html -->
</body>
```

### Noscript Etiketi Kullanımı

```html
<body>
    <script>
        document.write('JavaScript aktif');
    </script>
    <noscript>
        <p>JavaScript devre dışı. Lütfen JavaScript'i etkinleştirin.</p>
    </noscript>
</body>
```

## 🎯 Önemli Notlar

- `<title>` etiketi her sayfada zorunludur
- `<meta charset="UTF-8">` her zaman ilk meta etiketi olmalıdır
- Script dosyaları genellikle `</body>` öncesine yerleştirilir
- CSS dosyaları `<head>` içinde yüklenmelidir
- `async` ve `defer` özellikleri script yükleme performansını artırır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


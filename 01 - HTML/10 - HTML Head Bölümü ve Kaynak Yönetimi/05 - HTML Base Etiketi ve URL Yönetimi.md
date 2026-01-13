# 🎯 HTML BASE ETİKETİ VE URL YÖNETİMİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) `<base>` etiketi sayfadaki tüm göreli URL'ler için temel URL tanımlar.

## 📋 Base Etiketi Özellikleri

| Özellik | Açıklama | Örnek |
| :------ | :------- | :---- |
| `href` | Temel URL | `https://example.com/` |
| `target` | Varsayılan hedef | `_blank`, `_self` |

## 💡 Kullanım Örnekleri

### Temel Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Base Etiketi</title>
    <base href="https://example.com/">
</head>
<body>
    <!-- Göreli URL'ler base URL'e göre çözümlenir -->
    <a href="page.html">Sayfa</a> <!-- https://example.com/page.html -->
    <img src="images/logo.png"> <!-- https://example.com/images/logo.png -->
    <link rel="stylesheet" href="css/style.css"> <!-- https://example.com/css/style.css -->
</body>
</html>
```

### Base Target Kullanımı

```html
<head>
    <base href="https://example.com/" target="_blank">
</head>
<body>
    <!-- Tüm bağlantılar yeni sekmede açılır -->
    <a href="page1.html">Sayfa 1</a>
    <a href="page2.html">Sayfa 2</a>
</body>
```

### Alt Klasör Base URL

```html
<head>
    <base href="https://example.com/blog/">
</head>
<body>
    <a href="post1.html">Post 1</a> <!-- https://example.com/blog/post1.html -->
    <a href="../about.html">Hakkında</a> <!-- https://example.com/about.html -->
</body>
```

### Base Olmadan Kullanım

```html
<head>
    <!-- Base etiketi yok -->
</head>
<body>
    <!-- Mutlak URL -->
    <a href="https://example.com/page.html">Sayfa</a>
    
    <!-- Göreli URL (mevcut dizine göre) -->
    <a href="page.html">Sayfa</a>
</body>
```

## 🎯 Önemli Notlar

- `<base>` etiketi `<head>` içinde ve diğer URL içeren etiketlerden önce olmalıdır
- Sayfada sadece bir `<base>` etiketi olabilir
- Base URL mutlak URL olmalıdır (http:// veya https:// ile başlamalı)
- Base etiketi tüm göreli URL'leri etkiler (img, link, script, a, form vb.)
- Fragment (#) ve mutlak URL'ler base etiketinden etkilenmez

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🔍 HTML VALİDASYON VE HATA AYIKLAMA

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) validasyon kod kalitesini artırır.

## 📋 Validasyon Araçları

| Araç | Açıklama |
| :--- | :------- |
| W3C Validator | Resmi HTML validatörü |
| Browser DevTools | Tarayıcı geliştirici araçları |
| HTMLHint | Linter aracı |

## 💡 Kullanım Örnekleri

### W3C Validator Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Valid HTML</title>
</head>
<body>
    <!-- Valid HTML kodu -->
    <h1>Başlık</h1>
    <p>Paragraf</p>
</body>
</html>
```

### Browser DevTools

```html
<body>
    <!-- Console'da hataları kontrol edin -->
    <script>
        console.log('Sayfa yüklendi');
        // Hataları görmek için Console sekmesini açın
    </script>
</body>
```

### Yaygın Hatalar

```html
<!-- ❌ Hatalı - Kapanmamış etiket -->
<div>
    <p>Paragraf

<!-- ✅ Doğru -->
<div>
    <p>Paragraf</p>
</div>

<!-- ❌ Hatalı - Geçersiz özellik -->
<div class="container" class="main">

<!-- ✅ Doğru -->
<div class="container main">
```

## 🎯 Önemli Notlar

- W3C Validator ile kodunuzu kontrol edin
- Browser DevTools ile runtime hatalarını bulun
- Etiketleri düzgün kapatın
- Özellikleri doğru kullanın
- Semantic HTML kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


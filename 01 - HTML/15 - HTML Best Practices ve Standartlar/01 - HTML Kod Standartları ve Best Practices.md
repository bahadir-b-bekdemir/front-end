# ✅ HTML KOD STANDARTLARI VE BEST PRACTICES

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) best practices kod kalitesini ve bakımını artırır.

## 📋 Best Practices

| Kural | Açıklama |
| :---- | :------- |
| Semantic HTML | Anlamlı etiketler kullan |
| Doctype | HTML5 doctype kullan |
| Charset | UTF-8 encoding belirt |
| Alt text | Resimler için alt text ekle |
| Indentation | Tutarlı girintileme |

## 💡 Kullanım Örnekleri

### Semantic HTML

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Semantic HTML</title>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="/">Ana Sayfa</a></li>
                <li><a href="/about">Hakkında</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <h1>Başlık</h1>
            <p>İçerik</p>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2024 Şirket</p>
    </footer>
</body>
</html>
```

### Doğru Etiket Kullanımı

```html
<!-- ✅ İyi -->
<button onclick="handleClick()">Tıkla</button>

<!-- ❌ Kötü -->
<div onclick="handleClick()">Tıkla</div>

<!-- ✅ İyi -->
<img src="image.jpg" alt="Açıklama">

<!-- ❌ Kötü -->
<img src="image.jpg">
```

### Tutarlı Formatlama

```html
<!-- ✅ İyi - Tutarlı girintileme -->
<div>
    <p>Paragraf</p>
    <ul>
        <li>Öğe 1</li>
        <li>Öğe 2</li>
    </ul>
</div>
```

## 🎯 Önemli Notlar

- Semantic etiketler kullanın (header, nav, main, article, footer)
- Alt text her zaman ekleyin
- Tutarlı kod formatı kullanın
- Doctype ve charset belirtin
- Accessibility standartlarına uyun

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


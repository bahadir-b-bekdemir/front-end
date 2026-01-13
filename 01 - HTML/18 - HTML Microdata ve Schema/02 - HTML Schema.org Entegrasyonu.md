# 🏷️ HTML SCHEMA.ORG ENTEGRASYONU

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Schema.org yapılandırılmış veri için standart vocabulary'dir.

## 📋 Schema.org Tipleri

| Tip | Açıklama |
| :-- | :------- |
| Person | Kişi |
| Organization | Organizasyon |
| Product | Ürün |
| Article | Makale |
| LocalBusiness | Yerel işletme |

## 💡 Kullanım Örnekleri

### JSON-LD ile Schema

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Schema.org</title>
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Person",
        "name": "Ahmet Yılmaz",
        "email": "ahmet@example.com",
        "telephone": "+90 555 123 4567"
    }
    </script>
</head>
<body>
    <h1>Ahmet Yılmaz</h1>
</body>
</html>
```

### Ürün Schema

```html
<head>
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Product",
        "name": "Ürün Adı",
        "image": "product.jpg",
        "description": "Ürün açıklaması",
        "offers": {
            "@type": "Offer",
            "price": "199.99",
            "priceCurrency": "TRY"
        }
    }
    </script>
</head>
```

### Organizasyon Schema

```html
<head>
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Organization",
        "name": "Şirket Adı",
        "url": "https://example.com",
        "logo": "logo.png",
        "address": {
            "@type": "PostalAddress",
            "streetAddress": "Cadde, Sokak",
            "addressLocality": "İstanbul",
            "addressCountry": "TR"
        }
    }
    </script>
</head>
```

## 🎯 Önemli Notlar

- JSON-LD önerilen format
- Schema.org vocabulary kullanılır
- Rich snippets için kullanılır
- Arama motorları tarafından okunur

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


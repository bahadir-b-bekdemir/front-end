# 📊 HTML MICRODATA KULLANIMI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Microdata yapılandırılmış veri ekler.

## 📋 Microdata Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| `itemscope` | Öğe kapsamı |
| `itemtype` | Veri tipi |
| `itemprop` | Özellik adı |

## 💡 Kullanım Örnekleri

### Kişi Microdata

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Microdata</title>
</head>
<body>
    <div itemscope itemtype="https://schema.org/Person">
        <h1 itemprop="name">Ahmet Yılmaz</h1>
        <p>Email: <span itemprop="email">ahmet@example.com</span></p>
        <p>Telefon: <span itemprop="telephone">+90 555 123 4567</span></p>
    </div>
</body>
</html>
```

### Ürün Microdata

```html
<body>
    <div itemscope itemtype="https://schema.org/Product">
        <h1 itemprop="name">Ürün Adı</h1>
        <img itemprop="image" src="product.jpg" alt="Ürün">
        <p itemprop="description">Ürün açıklaması</p>
        <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
            <span itemprop="price">199.99</span>
            <span itemprop="priceCurrency">TRY</span>
        </div>
    </div>
</body>
```

### Organizasyon Microdata

```html
<body>
    <div itemscope itemtype="https://schema.org/Organization">
        <h1 itemprop="name">Şirket Adı</h1>
        <p itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
            <span itemprop="streetAddress">Cadde, Sokak</span>
            <span itemprop="addressLocality">İstanbul</span>
        </p>
    </div>
</body>
```

## 🎯 Önemli Notlar

- Schema.org vocabulary kullanılır
- Arama motorları için yapılandırılmış veri
- Rich snippets için kullanılır
- JSON-LD alternatif olarak kullanılabilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


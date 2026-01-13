# 🔗 HTML RDFa

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) RDFa (Resource Description Framework in attributes) yapılandırılmış veri ekler.

## 📋 RDFa Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| `vocab` | Vocabulary URI |
| `typeof` | Kaynak tipi |
| `property` | Özellik |
| `resource` | Kaynak URI |

## 💡 Kullanım Örnekleri

### Temel RDFa

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>RDFa</title>
</head>
<body>
    <div vocab="https://schema.org/" typeof="Person">
        <h1 property="name">Ahmet Yılmaz</h1>
        <p property="email">ahmet@example.com</p>
    </div>
</body>
</html>
```

### Ürün RDFa

```html
<body>
    <div vocab="https://schema.org/" typeof="Product">
        <h1 property="name">Ürün Adı</h1>
        <img property="image" src="product.jpg" alt="Ürün">
        <p property="description">Ürün açıklaması</p>
        <div typeof="Offer">
            <span property="price">199.99</span>
            <span property="priceCurrency">TRY</span>
        </div>
    </div>
</body>
```

## 🎯 Önemli Notlar

- RDFa HTML5 ile uyumludur
- Schema.org vocabulary kullanılır
- Microdata'ya alternatiftir
- JSON-LD daha yaygın kullanılır

## ✍️ Yazar

**Bahadır B. Bekdemir**


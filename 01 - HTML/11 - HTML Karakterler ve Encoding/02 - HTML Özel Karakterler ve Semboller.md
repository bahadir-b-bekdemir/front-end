# ✨ HTML ÖZEL KARAKTERLER VE SEMBOLLER

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) özel karakterler ve semboller entity'ler veya doğrudan Unicode karakterler ile gösterilir.

## 📋 Özel Karakter Kategorileri

| Kategori | Örnekler |
| :------- | :------- |
| Noktalama | `&hellip;`, `&mdash;`, `&ndash;` |
| Matematik | `&sum;`, `&prod;`, `&infin;` |
| Geometrik | `&bull;`, `&diams;`, `&hearts;` |
| Ok İşaretleri | `&larr;`, `&rarr;`, `&uarr;` |
| Para Birimleri | `&euro;`, `&pound;`, `&yen;` |

## 💡 Kullanım Örnekleri

### Noktalama İşaretleri

```html
<body>
    <p>Üç nokta&hellip; Devam ediyor</p>
    <p>Uzun tire&mdash; Uzun çizgi</p>
    <p>Kısa tire&ndash; Kısa çizgi</p>
    <p>Tek tırnak&apos; İçerik&apos;</p>
    <p>&ldquo;Çift tırnak başlangıç&rdquo;</p>
    <p>&lsquo;Tek tırnak başlangıç&rsquo;</p>
</body>
```

### Geometrik Şekiller

```html
<body>
    <p>&bull; Nokta</p>
    <p>&diams; Elmas</p>
    <p>&hearts; Kalp</p>
    <p>&spades; Maça</p>
    <p>&clubs; Sinek</p>
    <p>&loz; Baklava</p>
</body>
```

### Matematiksel Semboller

```html
<body>
    <p>&sum; Toplam sembolü</p>
    <p>&prod; Çarpım sembolü</p>
    <p>&infin; Sonsuz</p>
    <p>&radic; Karekök</p>
    <p>&int; İntegral</p>
    <p>&part; Kısmi türev</p>
    <p>&nabla; Nabla</p>
    <p>&isin; Eleman</p>
    <p>&notin; Eleman değil</p>
    <p>&sub; Alt küme</p>
    <p>&sup; Üst küme</p>
</body>
```

### Ok İşaretleri

```html
<body>
    <p>&larr; Sol ok</p>
    <p>&rarr; Sağ ok</p>
    <p>&uarr; Yukarı ok</p>
    <p>&darr; Aşağı ok</p>
    <p>&harr; Çift yönlü</p>
    <p>&lArr; Çift sol ok</p>
    <p>&rArr; Çift sağ ok</p>
    <p>&uArr; Çift yukarı ok</p>
    <p>&dArr; Çift aşağı ok</p>
</body>
```

### Para Birimleri

```html
<body>
    <p>&cent; Cent işareti</p>
    <p>&pound; Pound işareti</p>
    <p>&yen; Yen işareti</p>
    <p>&euro; Euro işareti</p>
    <p>&#8378; Türk Lirası (₺)</p>
</body>
```

### Yıldız ve Dekoratif

```html
<body>
    <p>&lowast; Yıldız</p>
    <p>&#9733; Dolu yıldız</p>
    <p>&#9734; Boş yıldız</p>
    <p>&#10029; Sparkles</p>
    <p>&#10030; Sparkles</p>
</body>
```

### Unicode Doğrudan Kullanım

```html
<head>
    <meta charset="UTF-8">
</head>
<body>
    <p>© Telif hakkı</p>
    <p>® Kayıtlı marka</p>
    <p>™ Ticari marka</p>
    <p>€ Euro</p>
    <p>£ Pound</p>
    <p>¥ Yen</p>
    <p>₺ Türk Lirası</p>
    <p>→ Ok</p>
    <p>★ Yıldız</p>
    <p>❤ Kalp</p>
</body>
```

## 🎯 Best Practices

- UTF-8 encoding kullanarak çoğu karakteri doğrudan yazabilirsiniz
- Eski tarayıcı uyumluluğu için entity kullanın
- Özel semboller için Unicode karakterleri tercih edin
- Font desteği olmayan karakterler için entity kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


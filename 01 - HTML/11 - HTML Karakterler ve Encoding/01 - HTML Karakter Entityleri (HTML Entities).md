# 🔤 HTML KARAKTER ENTİTY'LERİ (HTML ENTITIES)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) özel karakterler entity'ler kullanılarak gösterilir.

## 📋 Entity Kullanım Formatı

| Format | Açıklama | Örnek |
| :----- | :------- | :---- |
| `&entity_name;` | İsim ile | `&copy;` |
| `&#number;` | Sayısal kod ile | `&#169;` |
| `&#xhex;` | Hexadecimal ile | `&#xA9;` |

## 💡 Yaygın HTML Entity'leri

### Özel Karakterler

```html
<body>
    <!-- Telif hakkı -->
    <p>&copy; 2024 Şirket Adı</p>
    
    <!-- Ticari marka -->
    <p>Ürün&trade; Markası</p>
    
    <!-- Kayıtlı marka -->
    <p>Marka&reg; Kayıtlı</p>
    
    <!-- Tırnak işaretleri -->
    <p>&quot;Alıntı metni&quot;</p>
    <p>&apos;Tek tırnak&apos;</p>
    
    <!-- Küçüktür ve büyüktür -->
    <p>&lt;HTML&gt; etiketi</p>
    
    <!-- Ve işareti -->
    <p>HTML &amp; CSS</p>
    
    <!-- Boşluk (non-breaking) -->
    <p>Kelime&nbsp;Kelime</p>
</body>
```

### Matematiksel Semboller

```html
<body>
    <p>&plusmn; &plusmn; Artı/eksi</p>
    <p>&times; &times; Çarpı</p>
    <p>&divide; &divide; Bölü</p>
    <p>&frac12; &frac12; Yarı</p>
    <p>&frac14; &frac14; Çeyrek</p>
    <p>&infin; &infin; Sonsuz</p>
    <p>&sum; &sum; Toplam</p>
    <p>&prod; &prod; Çarpım</p>
</body>
```

### Yunan Harfleri

```html
<body>
    <p>&Alpha; &Alpha; Alfa</p>
    <p>&Beta; &Beta; Beta</p>
    <p>&Gamma; &Gamma; Gamma</p>
    <p>&Delta; &Delta; Delta</p>
    <p>&pi; &pi; Pi</p>
    <p>&omega; &omega; Omega</p>
</body>
```

### Ok İşaretleri

```html
<body>
    <p>&larr; &larr; Sol ok</p>
    <p>&rarr; &rarr; Sağ ok</p>
    <p>&uarr; &uarr; Yukarı ok</p>
    <p>&darr; &darr; Aşağı ok</p>
    <p>&harr; &harr; Çift yönlü ok</p>
</body>
```

### Para Birimleri

```html
<body>
    <p>&cent; &cent; Cent</p>
    <p>&pound; &pound; Pound</p>
    <p>&yen; &yen; Yen</p>
    <p>&euro; &euro; Euro</p>
</body>
```

### Sayısal Kod Kullanımı

```html
<body>
    <p>&#169; Telif hakkı (169)</p>
    <p>&#174; Kayıtlı marka (174)</p>
    <p>&#8482; Ticari marka (8482)</p>
    <p>&#8364; Euro (8364)</p>
</body>
```

### Hexadecimal Kod Kullanımı

```html
<body>
    <p>&#xA9; Telif hakkı (A9)</p>
    <p>&#xAE; Kayıtlı marka (AE)</p>
    <p>&#x2122; Ticari marka (2122)</p>
    <p>&#x20AC; Euro (20AC)</p>
</body>
```

## 🎯 Önemli Notlar

- Entity'ler `&` ile başlar ve `;` ile biter
- Büyük/küçük harf duyarlıdır
- Sayısal kodlar decimal veya hexadecimal olabilir
- Özel karakterler için entity kullanımı önerilir
- Modern tarayıcılar UTF-8 ile çoğu karakteri doğrudan gösterir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


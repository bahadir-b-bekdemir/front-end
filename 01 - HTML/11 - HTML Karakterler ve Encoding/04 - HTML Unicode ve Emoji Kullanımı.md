# 😀 HTML UNICODE VE EMOJI KULLANIMI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Unicode karakterler ve emoji'ler UTF-8 encoding ile doğrudan kullanılabilir.

## 📋 Unicode Kullanım Yöntemleri

| Yöntem | Format | Örnek |
| :----- | :----- | :---- |
| Doğrudan | Karakter | `😀` |
| Decimal | `&#number;` | `&#128512;` |
| Hexadecimal | `&#xhex;` | `&#x1F600;` |

## 💡 Kullanım Örnekleri

### Doğrudan Emoji Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Emoji Kullanımı</title>
</head>
<body>
    <h1>Emoji Örnekleri 😀</h1>
    
    <p>Yüz ifadeleri: 😀 😃 😄 😁 😆 😅</p>
    <p>El işaretleri: 👍 👎 👌 ✌️ 🤞</p>
    <p>Kalpler: ❤️ 💛 💚 💙 💜 🖤</p>
    <p>Hayvanlar: 🐶 🐱 🐭 🐹 🐰 🦊</p>
    <p>Yemek: 🍕 🍔 🍟 🌭 🍿 🍰</p>
    <p>Ulaşım: 🚗 🚕 🚙 🚌 🚎 🏎️</p>
</body>
</html>
```

### Unicode Decimal Kod ile

```html
<body>
    <p>&#128512; Gülümseyen yüz</p>
    <p>&#128513; Göz kırpan yüz</p>
    <p>&#128514; Kahkaha</p>
    <p>&#128515; Mutlu yüz</p>
    <p>&#128516; Gözleri yıldızlı</p>
</body>
```

### Unicode Hexadecimal Kod ile

```html
<body>
    <p>&#x1F600; Gülümseyen yüz</p>
    <p>&#x1F601; Göz kırpan yüz</p>
    <p>&#x1F602; Kahkaha</p>
    <p>&#x1F603; Mutlu yüz</p>
    <p>&#x1F604; Gözleri yıldızlı</p>
</body>
```

### Emoji ile İkonlar

```html
<body>
    <h2>İkonlar</h2>
    <p>✅ Başarılı</p>
    <p>❌ Hata</p>
    <p>⚠️ Uyarı</p>
    <p>ℹ️ Bilgi</p>
    <p>🔒 Güvenli</p>
    <p>🔓 Açık</p>
    <p>⭐ Yıldız</p>
    <p>🔥 Ateş</p>
</body>
```

### Emoji ile Butonlar

```html
<body>
    <button>👍 Beğen</button>
    <button>❤️ Favori</button>
    <button>💬 Yorum</button>
    <button>📤 Paylaş</button>
    <button>🔔 Bildirim</button>
</body>
```

### Emoji ile Liste

```html
<body>
    <ul>
        <li>📧 E-posta gönder</li>
        <li>📞 Telefon ara</li>
        <li>💬 Mesaj gönder</li>
        <li>📍 Konum paylaş</li>
        <li>📷 Fotoğraf çek</li>
    </ul>
</body>
```

### Emoji Font Boyutu

```html
<head>
    <style>
        .large-emoji {
            font-size: 48px;
        }
        .emoji-button {
            font-size: 24px;
            padding: 10px;
        }
    </style>
</head>
<body>
    <p class="large-emoji">😀 🎉 🚀</p>
    <button class="emoji-button">👍 Beğen</button>
</body>
```

### Emoji Accessibility

```html
<body>
    <!-- Emoji için alternatif metin -->
    <span role="img" aria-label="Gülümseyen yüz">😀</span>
    <span role="img" aria-label="Kalp">❤️</span>
    <span role="img" aria-label="Yıldız">⭐</span>
</body>
```

## 🎯 Önemli Notlar

- UTF-8 encoding kullanılmalıdır
- Emoji'ler farklı platformlarda farklı görünebilir
- Erişilebilirlik için `aria-label` kullanın
- Emoji font desteği tarayıcıya bağlıdır
- Unicode standardı sürekli güncellenmektedir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


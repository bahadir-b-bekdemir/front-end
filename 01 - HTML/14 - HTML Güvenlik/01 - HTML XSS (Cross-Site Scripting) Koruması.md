# 🔒 HTML XSS (CROSS-SITE SCRIPTING) KORUMASI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) XSS saldırılarına karşı koruma önemlidir.

## 📋 XSS Türleri

| Tür | Açıklama |
| :-- | :------- |
| Stored XSS | Veritabanında saklanan kötü amaçlı kod |
| Reflected XSS | URL'den gelen kötü amaçlı kod |
| DOM-based XSS | DOM manipülasyonu ile |

## 💡 Koruma Yöntemleri

### Input Sanitization

```html
<body>
    <input type="text" id="userInput">
    <button onclick="displaySafe()">Güvenli Göster</button>
    <div id="output"></div>
    
    <script>
        function escapeHtml(text) {
            const map = {
                '&': '&amp;',
                '<': '&lt;',
                '>': '&gt;',
                '"': '&quot;',
                "'": '&#039;'
            };
            return text.replace(/[&<>"']/g, m => map[m]);
        }
        
        function displaySafe() {
            const input = document.getElementById('userInput').value;
            const safe = escapeHtml(input);
            document.getElementById('output').innerHTML = safe;
        }
    </script>
</body>
```

### Content Security Policy

```html
<head>
    <meta http-equiv="Content-Security-Policy" 
          content="default-src 'self'; script-src 'self' 'unsafe-inline';">
</head>
```

### DOMPurify Kullanımı

```html
<body>
    <script src="https://cdn.jsdelivr.net/npm/dompurify@2.4.0/dist/purify.min.js"></script>
    <script>
        const dirty = '<img src=x onerror=alert(1)>';
        const clean = DOMPurify.sanitize(dirty);
        document.body.innerHTML = clean;
    </script>
</body>
```

## 🎯 Önemli Notlar

- Kullanıcı girdilerini her zaman sanitize edin
- `innerHTML` yerine `textContent` kullanın
- CSP header'ı ekleyin
- DOMPurify gibi kütüphaneler kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


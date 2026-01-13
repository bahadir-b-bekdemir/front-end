# 🌐 HTML TARAYICI UYUMLULUĞU VE POLYFILLS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tarayıcı uyumluluğu önemlidir.

## 📋 Uyumluluk Kontrolü

| Yöntem | Açıklama |
| :----- | :------- |
| Feature detection | Özellik kontrolü |
| Polyfills | Eksik özellikleri ekleme |
| Can I Use | Uyumluluk kontrolü |

## 💡 Kullanım Örnekleri

### Feature Detection

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Feature Detection</title>
</head>
<body>
    <script>
        // LocalStorage kontrolü
        if (typeof(Storage) !== "undefined") {
            localStorage.setItem("test", "value");
        } else {
            console.log("LocalStorage desteklenmiyor");
        }
        
        // Fetch API kontrolü
        if (window.fetch) {
            fetch('/api/data');
        } else {
            // Fallback
            console.log("Fetch API desteklenmiyor");
        }
    </script>
</body>
</html>
```

### Polyfill Kullanımı

```html
<head>
    <!-- Fetch polyfill -->
    <script src="https://cdn.jsdelivr.net/npm/whatwg-fetch@3.6.2/dist/fetch.umd.js"></script>
    
    <!-- Promise polyfill -->
    <script src="https://cdn.jsdelivr.net/npm/es6-promise@4.2.8/dist/es6-promise.auto.min.js"></script>
</head>
```

### Modernizr ile Feature Detection

```html
<head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/modernizr/2.8.3/modernizr.min.js"></script>
    <script>
        if (Modernizr.localstorage) {
            // LocalStorage kullan
        } else {
            // Fallback
        }
    </script>
</head>
```

## 🎯 Önemli Notlar

- Feature detection kullanın
- Polyfills ile eski tarayıcı desteği ekleyin
- Can I Use ile uyumluluğu kontrol edin
- Progressive enhancement uygulayın
- Graceful degradation sağlayın

## ✍️ Yazar

**Bahadır B. Bekdemir**


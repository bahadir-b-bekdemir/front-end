# 📜 HTML SCRIPT VE JAVASCRIPT ENTEGRASYONU

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) JavaScript kodu `<script>` etiketi ile sayfaya entegre edilir.

## 📋 Script Etiketi Özellikleri

| Özellik | Açıklama | Değerler |
| :------ | :------- | :------- |
| `src` | Dış dosya yolu | `script.js` |
| `type` | Script tipi | `text/javascript`, `module` |
| `async` | Asenkron yükleme | Boolean |
| `defer` | Ertelenmiş yükleme | Boolean |
| `crossorigin` | CORS ayarı | `anonymous`, `use-credentials` |
| `integrity` | Dosya bütünlüğü | SHA hash |

## 💡 Kullanım Örnekleri

### Inline JavaScript

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Inline JavaScript</title>
</head>
<body>
    <h1 id="baslik">Merhaba</h1>
    
    <script>
        document.getElementById('baslik').textContent = 'Merhaba Dünya!';
    </script>
</body>
</html>
```

### Dış JavaScript Dosyası

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Dış JavaScript</title>
    <script src="app.js"></script>
</head>
<body>
    <h1>Sayfa İçeriği</h1>
</body>
</html>
```

### Async Yükleme

```html
<head>
    <!-- Sayfa yüklenirken paralel olarak yüklenir -->
    <script src="analytics.js" async></script>
</head>
```

### Defer Yükleme

```html
<head>
    <!-- HTML parse edildikten sonra çalışır -->
    <script src="main.js" defer></script>
</head>
```

### ES6 Modules

```html
<head>
    <!-- Modül sistemi -->
    <script type="module" src="main.js"></script>
</head>
```

```javascript
// main.js
import { function1 } from './module.js';
```

### Script Integrity (Güvenlik)

```html
<head>
    <!-- Dosya bütünlüğü kontrolü -->
    <script 
        src="https://cdn.example.com/library.js"
        integrity="sha384-oqVuAfXRKap7fdgcCY5uykM6+R9GqQ8K/uxy9rx7HNQlGYl1kPzQho1wx4JwY8wC"
        crossorigin="anonymous">
    </script>
</head>
```

### Script Yükleme Sırası

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Script Sırası</title>
</head>
<body>
    <!-- Önce yüklenir -->
    <script src="jquery.js"></script>
    
    <!-- Sonra yüklenir (jQuery'ye bağımlı) -->
    <script src="app.js"></script>
    
    <!-- En son çalışır -->
    <script>
        $(document).ready(function() {
            console.log('Sayfa hazır');
        });
    </script>
</body>
</html>
```

### Dinamik Script Yükleme

```html
<body>
    <button onclick="loadScript()">Script Yükle</button>
    
    <script>
        function loadScript() {
            const script = document.createElement('script');
            script.src = 'dynamic.js';
            script.async = true;
            document.body.appendChild(script);
        }
    </script>
</body>
```

## 🎯 Best Practices

- Script dosyalarını genellikle `</body>` öncesine yerleştirin
- Kritik olmayan scriptler için `async` veya `defer` kullanın
- Dış kaynaklar için `integrity` özelliğini kullanın
- Modül sistemini kullanarak kodu organize edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


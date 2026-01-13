# 📱 HTML PWA TEMELLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) PWA (Progressive Web App) mobil uygulama benzeri deneyim sağlar.

## 📋 PWA Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Offline çalışma | İnternet olmadan çalışır |
| Installable | Ana ekrana eklenebilir |
| Push notifications | Bildirim gönderir |
| Responsive | Tüm cihazlarda çalışır |

## 💡 Kullanım Örnekleri

### Manifest Dosyası

```json
{
  "name": "PWA Uygulaması",
  "short_name": "PWA",
  "description": "PWA örnek uygulama",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#000000",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

### HTML'de Manifest Bağlantısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#000000">
    <title>PWA Uygulaması</title>
    <link rel="manifest" href="manifest.json">
    <link rel="icon" href="icon-192.png">
</head>
<body>
    <h1>PWA Uygulaması</h1>
    <script>
        // Service Worker kaydı
        if ('serviceWorker' in navigator) {
            navigator.serviceWorker.register('/sw.js');
        }
    </script>
</body>
</html>
```

## 🎯 Önemli Notlar

- Manifest dosyası gerekli
- Service Worker offline çalışma için
- HTTPS gereklidir (localhost hariç)
- İkonlar farklı boyutlarda olmalı

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


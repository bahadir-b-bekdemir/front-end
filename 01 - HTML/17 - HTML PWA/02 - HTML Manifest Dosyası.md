# 📋 HTML MANİFEST DOSYASI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) manifest dosyası PWA yapılandırması için kullanılır.

## 📋 Manifest Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| `name` | Uygulama adı |
| `short_name` | Kısa ad |
| `start_url` | Başlangıç URL'i |
| `display` | Görüntüleme modu |
| `icons` | Uygulama ikonları |

## 💡 Kullanım Örnekleri

### Temel Manifest

```json
{
  "name": "My PWA App",
  "short_name": "PWA",
  "description": "Progressive Web App",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#000000",
  "orientation": "portrait",
  "icons": [
    {
      "src": "icon-72.png",
      "sizes": "72x72",
      "type": "image/png"
    },
    {
      "src": "icon-96.png",
      "sizes": "96x96",
      "type": "image/png"
    },
    {
      "src": "icon-128.png",
      "sizes": "128x128",
      "type": "image/png"
    },
    {
      "src": "icon-144.png",
      "sizes": "144x144",
      "type": "image/png"
    },
    {
      "src": "icon-152.png",
      "sizes": "152x152",
      "type": "image/png"
    },
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-384.png",
      "sizes": "384x384",
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

### HTML'de Bağlantı

```html
<head>
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#000000">
</head>
```

## 🎯 Önemli Notlar

- Manifest JSON formatında olmalı
- İkonlar farklı boyutlarda sağlanmalı
- `display: "standalone"` tam ekran modu
- `theme-color` tarayıcı rengini ayarlar

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📴 HTML OFFLINE ÇALIŞMA

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) offline çalışma Service Worker ile sağlanır.

## 📋 Offline Stratejileri

| Strateji | Açıklama |
| :------- | :------- |
| Cache First | Önce cache'den yükle |
| Network First | Önce network'ten yükle |
| Stale While Revalidate | Cache göster, arka planda güncelle |

## 💡 Kullanım Örnekleri

### Service Worker ile Cache

```javascript
// sw.js
const CACHE_NAME = 'my-cache-v1';
const urlsToCache = [
    '/',
    '/index.html',
    '/style.css',
    '/script.js',
    '/offline.html'
];

self.addEventListener('install', function(event) {
    event.waitUntil(
        caches.open(CACHE_NAME)
            .then(function(cache) {
                return cache.addAll(urlsToCache);
            })
    );
});

self.addEventListener('fetch', function(event) {
    event.respondWith(
        caches.match(event.request)
            .then(function(response) {
                if (response) {
                    return response;
                }
                return fetch(event.request).catch(function() {
                    return caches.match('/offline.html');
                });
            })
    );
});
```

### Offline Sayfası

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Offline</title>
</head>
<body>
    <h1>İnternet bağlantınız yok</h1>
    <p>Lütfen bağlantınızı kontrol edin.</p>
</body>
</html>
```

## 🎯 Önemli Notlar

- Service Worker cache yönetimi yapar
- Offline sayfası sağlanmalı
- Cache stratejisi seçilmeli
- Cache güncelleme mekanizması eklenmeli

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🔧 HTML SERVICE WORKERS (PWA)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Service Workers, Progressive Web App (PWA) özellikleri için kullanılır.

## 📋 Service Worker Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Offline çalışma | İnternet olmadan çalışır |
| Cache yönetimi | Dosyaları cache'ler |
| Push notifications | Bildirim gönderir |
| Background sync | Arka plan senkronizasyonu |

## 💡 Kullanım Örnekleri

### Service Worker Kaydı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Service Worker</title>
</head>
<body>
    <h1>Service Worker Örneği</h1>
    <button onclick="registerServiceWorker()">Kayıt Et</button>
    
    <script>
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', function() {
                navigator.serviceWorker.register('/sw.js')
                    .then(function(registration) {
                        console.log('Service Worker kayıtlı:', registration.scope);
                    })
                    .catch(function(error) {
                        console.log('Service Worker kaydı başarısız:', error);
                    });
            });
        }
    </script>
</body>
</html>
```

### Service Worker Dosyası (sw.js)

```javascript
// sw.js
const CACHE_NAME = 'my-cache-v1';
const urlsToCache = [
    '/',
    '/index.html',
    '/style.css',
    '/script.js'
];

// Install event
self.addEventListener('install', function(event) {
    event.waitUntil(
        caches.open(CACHE_NAME)
            .then(function(cache) {
                return cache.addAll(urlsToCache);
            })
    );
});

// Fetch event
self.addEventListener('fetch', function(event) {
    event.respondWith(
        caches.match(event.request)
            .then(function(response) {
                if (response) {
                    return response;
                }
                return fetch(event.request);
            })
    );
});
```

### Cache Stratejileri

```javascript
// sw.js - Cache First
self.addEventListener('fetch', function(event) {
    event.respondWith(
        caches.match(event.request)
            .then(function(response) {
                return response || fetch(event.request);
            })
    );
});

// Network First
self.addEventListener('fetch', function(event) {
    event.respondWith(
        fetch(event.request)
            .then(function(response) {
                const responseClone = response.clone();
                caches.open(CACHE_NAME).then(function(cache) {
                    cache.put(event.request, responseClone);
                });
                return response;
            })
            .catch(function() {
                return caches.match(event.request);
            })
    );
});
```

### Push Notification

```html
<body>
    <button onclick="requestNotification()">Bildirim İzni İste</button>
    <button onclick="showNotification()">Bildirim Göster</button>
    
    <script>
        function requestNotification() {
            Notification.requestPermission().then(function(permission) {
                console.log('İzin:', permission);
            });
        }
        
        function showNotification() {
            if (Notification.permission === 'granted') {
                new Notification('Başlık', {
                    body: 'Bildirim metni',
                    icon: '/icon.png'
                });
            }
        }
    </script>
</body>
```

## 🎯 Önemli Notlar

- Service Worker HTTPS gerektirir (localhost hariç)
- Service Worker arka planda çalışır
- Cache API ile dosyalar saklanır
- Push API ile bildirimler gönderilir
- Background Sync ile offline işlemler senkronize edilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


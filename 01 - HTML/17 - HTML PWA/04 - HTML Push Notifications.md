# 🔔 HTML PUSH NOTIFICATIONS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) push notifications kullanıcıları bilgilendirir.

## 📋 Notification API

| API | Açıklama |
| :-- | :------- |
| Notification.requestPermission() | İzin ister |
| new Notification() | Bildirim gösterir |
| Service Worker | Arka plan bildirimleri |

## 💡 Kullanım Örnekleri

### Bildirim İzni

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Push Notifications</title>
</head>
<body>
    <button onclick="requestPermission()">Bildirim İzni İste</button>
    <button onclick="showNotification()">Bildirim Göster</button>
    
    <script>
        function requestPermission() {
            if ('Notification' in window) {
                Notification.requestPermission().then(function(permission) {
                    console.log('İzin:', permission);
                });
            }
        }
        
        function showNotification() {
            if (Notification.permission === 'granted') {
                new Notification('Başlık', {
                    body: 'Bildirim metni',
                    icon: '/icon.png',
                    badge: '/badge.png'
                });
            }
        }
    </script>
</body>
</html>
```

### Service Worker Bildirimi

```javascript
// sw.js
self.addEventListener('push', function(event) {
    const options = {
        body: event.data.text(),
        icon: '/icon.png',
        badge: '/badge.png'
    };
    
    event.waitUntil(
        self.registration.showNotification('Bildirim', options)
    );
});
```

## 🎯 Önemli Notlar

- Kullanıcı izni gerekir
- Service Worker arka plan bildirimleri için
- Bildirim içeriği dikkatli seçilmeli
- İkon ve badge eklenebilir

## ✍️ Yazar

**Bahadır B. Bekdemir**


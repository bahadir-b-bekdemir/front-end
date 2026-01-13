# 📡 HTML SERVER-SENT EVENTS (SSE)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Server-Sent Events, sunucudan istemciye tek yönlü veri akışı sağlar.

## 📋 SSE Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Tek yönlü | Sunucudan istemciye |
| Otomatik yeniden bağlanma | Bağlantı kesilirse tekrar bağlanır |
| Basit API | EventSource ile kullanım |

## 💡 Kullanım Örnekleri

### Temel SSE Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Server-Sent Events</title>
</head>
<body>
    <h1>Server-Sent Events Örneği</h1>
    <div id="messages"></div>
    
    <script>
        if (typeof(EventSource) !== "undefined") {
            const eventSource = new EventSource("sse.php");
            
            eventSource.onmessage = function(event) {
                document.getElementById("messages").innerHTML += 
                    "<p>" + event.data + "</p>";
            };
            
            eventSource.onerror = function(event) {
                console.log("SSE hatası");
            };
        } else {
            document.getElementById("messages").innerHTML = 
                "SSE desteklenmiyor";
        }
    </script>
</body>
</html>
```

### Özel Event Tipleri

```html
<body>
    <div id="updates"></div>
    <div id="notifications"></div>
    
    <script>
        const eventSource = new EventSource("events.php");
        
        // Varsayılan message event
        eventSource.onmessage = function(event) {
            document.getElementById("updates").innerHTML += 
                "<p>" + event.data + "</p>";
        };
        
        // Özel event tipi
        eventSource.addEventListener("notification", function(event) {
            document.getElementById("notifications").innerHTML += 
                "<p>Bildirim: " + event.data + "</p>";
        });
    </script>
</body>
```

### SSE Bağlantı Yönetimi

```html
<body>
    <button onclick="connectSSE()">Bağlan</button>
    <button onclick="disconnectSSE()">Bağlantıyı Kes</button>
    <div id="messages"></div>
    
    <script>
        let eventSource;
        
        function connectSSE() {
            eventSource = new EventSource("events.php");
            
            eventSource.onopen = function(event) {
                console.log("Bağlantı açıldı");
            };
            
            eventSource.onmessage = function(event) {
                document.getElementById("messages").innerHTML += 
                    "<p>" + event.data + "</p>";
            };
        }
        
        function disconnectSSE() {
            if (eventSource) {
                eventSource.close();
                console.log("Bağlantı kapatıldı");
            }
        }
    </script>
</body>
```

### PHP SSE Örneği (sse.php)

```php
<?php
header('Content-Type: text/event-stream');
header('Cache-Control: no-cache');
header('Connection: keep-alive');

while (true) {
    $data = json_encode([
        'time' => date('H:i:s'),
        'message' => 'Sunucu mesajı'
    ]);
    
    echo "data: " . $data . "\n\n";
    flush();
    
    sleep(1);
}
?>
```

## 🎯 Önemli Notlar

- SSE tek yönlü iletişim sağlar (sunucudan istemciye)
- WebSocket'e göre daha basittir
- Otomatik yeniden bağlanma özelliği vardır
- `text/event-stream` content-type kullanılmalıdır
- Sunucu tarafında keep-alive bağlantı gerekir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


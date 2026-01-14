# 🔌 HTML WEBSOCKET API

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) WebSocket API, gerçek zamanlı çift yönlü iletişim sağlar.

## 📋 WebSocket Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Çift yönlü | İstemci-sunucu arası |
| Gerçek zamanlı | Düşük gecikme |
| Tek bağlantı | HTTP handshake sonrası |

## 💡 Kullanım Örnekleri

### Temel WebSocket Bağlantısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>WebSocket</title>
</head>
<body>
    <div id="messages"></div>
    <input type="text" id="messageInput">
    <button onclick="sendMessage()">Gönder</button>
    
    <script>
        const ws = new WebSocket("ws://localhost:8080");
        
        ws.onopen = function(event) {
            console.log("WebSocket bağlantısı açıldı");
        };
        
        ws.onmessage = function(event) {
            document.getElementById("messages").innerHTML += 
                "<p>" + event.data + "</p>";
        };
        
        ws.onerror = function(error) {
            console.log("WebSocket hatası:", error);
        };
        
        ws.onclose = function(event) {
            console.log("WebSocket bağlantısı kapandı");
        };
        
        function sendMessage() {
            const message = document.getElementById("messageInput").value;
            ws.send(message);
            document.getElementById("messageInput").value = "";
        }
    </script>
</body>
</html>
```

### Güvenli WebSocket (WSS)

```html
<body>
    <script>
        // HTTPS için WSS kullanılmalı
        const ws = new WebSocket("wss://example.com/ws");
        
        ws.onopen = function() {
            console.log("Güvenli bağlantı açıldı");
        };
    </script>
</body>
```

### WebSocket Durum Kontrolü

```html
<body>
    <div id="status"></div>
    <button onclick="checkStatus()">Durum Kontrol</button>
    
    <script>
        const ws = new WebSocket("ws://localhost:8080");
        
        function checkStatus() {
            const states = {
                0: 'CONNECTING',
                1: 'OPEN',
                2: 'CLOSING',
                3: 'CLOSED'
            };
            
            document.getElementById("status").innerHTML = 
                "Durum: " + states[ws.readyState];
        }
    </script>
</body>
```

### JSON Veri Gönderme

```html
<body>
    <button onclick="sendJSON()">JSON Gönder</button>
    
    <script>
        const ws = new WebSocket("ws://localhost:8080");
        
        function sendJSON() {
            const data = {
                type: "message",
                content: "Merhaba",
                timestamp: new Date().toISOString()
            };
            
            ws.send(JSON.stringify(data));
        }
        
        ws.onmessage = function(event) {
            const data = JSON.parse(event.data);
            console.log("Alınan veri:", data);
        };
    </script>
</body>
```

### WebSocket Yeniden Bağlanma

```html
<body>
    <script>
        let ws;
        let reconnectInterval;
        
        function connect() {
            ws = new WebSocket("ws://localhost:8080");
            
            ws.onopen = function() {
                console.log("Bağlandı");
                clearInterval(reconnectInterval);
            };
            
            ws.onclose = function() {
                console.log("Bağlantı kesildi, yeniden bağlanılıyor...");
                reconnectInterval = setInterval(connect, 3000);
            };
            
            ws.onerror = function(error) {
                console.log("Hata:", error);
            };
        }
        
        connect();
    </script>
</body>
```

## 🎯 Önemli Notlar

- WebSocket çift yönlü iletişim sağlar
- `ws://` HTTP için, `wss://` HTTPS için kullanılır
- `readyState` ile bağlantı durumu kontrol edilir
- JSON veri göndermek için `JSON.stringify()` kullanılır
- Bağlantı kesilirse yeniden bağlanma mekanizması eklenmelidir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# ⚙️ HTML WEB WORKERS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Web Workers, arka planda JavaScript kodunu çalıştırmak için kullanılır.

## 📋 Web Worker Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Arka plan işleme | UI'ı bloklamadan çalışır |
| Thread benzeri | Ayrı thread'de çalışır |
| Mesajlaşma | `postMessage` ile iletişim |

## 💡 Kullanım Örnekleri

### Temel Web Worker

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Web Worker</title>
</head>
<body>
    <button onclick="startWorker()">Worker Başlat</button>
    <button onclick="stopWorker()">Worker Durdur</button>
    <div id="result"></div>
    
    <script>
        let worker;
        
        function startWorker() {
            if (typeof(Worker) !== "undefined") {
                if (typeof(worker) == "undefined") {
                    worker = new Worker("worker.js");
                }
                worker.onmessage = function(event) {
                    document.getElementById("result").innerHTML = event.data;
                };
            } else {
                document.getElementById("result").innerHTML = "Web Worker desteklenmiyor";
            }
        }
        
        function stopWorker() {
            worker.terminate();
            worker = undefined;
        }
    </script>
</body>
</html>
```

### Worker Dosyası (worker.js)

```javascript
// worker.js
let i = 0;

function timedCount() {
    i = i + 1;
    postMessage(i);
    setTimeout("timedCount()", 500);
}

timedCount();
```

### Inline Web Worker

```html
<body>
    <button onclick="startInlineWorker()">Inline Worker</button>
    <div id="result"></div>
    
    <script>
        function startInlineWorker() {
            const blob = new Blob([
                `let i = 0;
                function timedCount() {
                    i = i + 1;
                    postMessage(i);
                    setTimeout("timedCount()", 500);
                }
                timedCount();`
            ], { type: 'application/javascript' });
            
            const worker = new Worker(URL.createObjectURL(blob));
            
            worker.onmessage = function(event) {
                document.getElementById("result").innerHTML = event.data;
            };
        }
    </script>
</body>
```

### Worker ile Hesaplama

```html
<body>
    <input type="number" id="number" value="1000000">
    <button onclick="calculate()">Hesapla</button>
    <div id="result"></div>
    
    <script>
        function calculate() {
            const number = document.getElementById("number").value;
            const worker = new Worker("calculator.js");
            
            worker.postMessage(number);
            
            worker.onmessage = function(event) {
                document.getElementById("result").innerHTML = "Sonuç: " + event.data;
                worker.terminate();
            };
        }
    </script>
</body>
```

### Calculator Worker (calculator.js)

```javascript
// calculator.js
onmessage = function(event) {
    const number = event.data;
    let sum = 0;
    
    for (let i = 0; i < number; i++) {
        sum += i;
    }
    
    postMessage(sum);
};
```

## 🎯 Önemli Notlar

- Web Workers DOM'a erişemez
- `postMessage` ile ana thread ile iletişim kurulur
- Worker'lar ayrı dosyada veya Blob olarak tanımlanabilir
- `terminate()` ile worker sonlandırılır
- Shared Workers birden fazla sayfa ile paylaşılabilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


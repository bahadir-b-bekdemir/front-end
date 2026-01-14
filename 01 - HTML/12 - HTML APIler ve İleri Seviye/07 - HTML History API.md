# 📜 HTML HISTORY API

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) History API, tarayıcı geçmişini yönetmek için kullanılır.

## 📋 History API Özellikleri

| Metod | Açıklama |
| :---- | :------- |
| `pushState()` | Yeni state ekler |
| `replaceState()` | Mevcut state'i değiştirir |
| `popstate` | Geri/ileri butonları için event |

## 💡 Kullanım Örnekleri

### Temel History API

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>History API</title>
</head>
<body>
    <button onclick="goToPage1()">Sayfa 1</button>
    <button onclick="goToPage2()">Sayfa 2</button>
    <div id="content"></div>
    
    <script>
        function goToPage1() {
            history.pushState({page: 1}, "Sayfa 1", "/page1");
            document.getElementById('content').innerHTML = '<h1>Sayfa 1</h1>';
        }
        
        function goToPage2() {
            history.pushState({page: 2}, "Sayfa 2", "/page2");
            document.getElementById('content').innerHTML = '<h1>Sayfa 2</h1>';
        }
        
        window.addEventListener('popstate', function(event) {
            if (event.state) {
                document.getElementById('content').innerHTML = 
                    '<h1>Sayfa ' + event.state.page + '</h1>';
            }
        });
    </script>
</body>
</html>
```

### SPA (Single Page Application) Routing

```html
<body>
    <nav>
        <a href="/" onclick="route(event)">Ana Sayfa</a>
        <a href="/about" onclick="route(event)">Hakkında</a>
        <a href="/contact" onclick="route(event)">İletişim</a>
    </nav>
    <div id="app"></div>
    
    <script>
        const routes = {
            '/': '<h1>Ana Sayfa</h1>',
            '/about': '<h1>Hakkında</h1>',
            '/contact': '<h1>İletişim</h1>'
        };
        
        function route(event) {
            event.preventDefault();
            const path = event.target.getAttribute('href');
            history.pushState({path: path}, '', path);
            render(path);
        }
        
        function render(path) {
            document.getElementById('app').innerHTML = routes[path] || '<h1>404</h1>';
        }
        
        window.addEventListener('popstate', function(event) {
            render(window.location.pathname);
        });
        
        // İlk yükleme
        render(window.location.pathname);
    </script>
</body>
```

### ReplaceState Kullanımı

```html
<body>
    <button onclick="updateState()">State Güncelle</button>
    <div id="state"></div>
    
    <script>
        function updateState() {
            history.replaceState({count: 1}, "Güncellendi", "/updated");
            document.getElementById('state').innerHTML = 
                'State güncellendi: ' + JSON.stringify(history.state);
        }
    </script>
</body>
```

### History State ile Veri Saklama

```html
<body>
    <input type="text" id="input" placeholder="Metin girin">
    <button onclick="saveState()">Kaydet</button>
    <div id="saved"></div>
    
    <script>
        function saveState() {
            const text = document.getElementById('input').value;
            history.pushState({text: text}, "Kaydedildi", "/saved");
            document.getElementById('saved').innerHTML = 
                'Kaydedilen: ' + text;
        }
        
        window.addEventListener('popstate', function(event) {
            if (event.state && event.state.text) {
                document.getElementById('saved').innerHTML = 
                    'Geri alındı: ' + event.state.text;
            }
        });
    </script>
</body>
```

## 🎯 Önemli Notlar

- `pushState()` yeni state ekler, geri butonu çalışır
- `replaceState()` mevcut state'i değiştirir, geri butonu çalışmaz
- `popstate` event geri/ileri butonları için tetiklenir
- State verisi JSON formatında saklanabilir
- URL değişikliği sayfa yenilemeden yapılır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


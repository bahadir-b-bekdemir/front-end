# 💾 HTML5 LOCAL STORAGE VE SESSION STORAGE

**HTML5** ile birlikte tarayıcıda veri saklama için `localStorage` ve `sessionStorage` API'leri eklendi. Bu API'ler JavaScript ile kullanılır.

## 📋 Storage API'leri

### `localStorage`

Tarayıcıda kalıcı veri saklar. Tarayıcı kapatılsa bile veri kalır.

### `sessionStorage`

Tarayıcı sekmesi açık olduğu sürece veri saklar. Sekme kapanınca veri silinir.

## 📋 Storage Metodları

### `setItem(key, value)`

Veri kaydetme.

### `getItem(key)`

Veri okuma.

### `removeItem(key)`

Veri silme.

### `clear()`

Tüm verileri silme.

### `key(index)`

İndekse göre anahtar alma.

### `length`

Saklanan öğe sayısı.

## 💡 Kullanım Örnekleri

### LocalStorage Temel Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>LocalStorage Temel</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        input, button {
            padding: 10px;
            margin: 5px;
            border: 1px solid #ddd;
            border-radius: 3px;
        }
        
        button {
            background-color: #3498db;
            color: white;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #2980b9;
        }
    </style>
</head>
<body>
    <h1>LocalStorage Örneği</h1>
    
    <div class="container">
        <h2>Veri Kaydetme</h2>
        <input type="text" id="keyInput" placeholder="Anahtar">
        <input type="text" id="valueInput" placeholder="Değer">
        <button onclick="saveData()">Kaydet</button>
    </div>
    
    <div class="container">
        <h2>Veri Okuma</h2>
        <input type="text" id="readKey" placeholder="Anahtar">
        <button onclick="readData()">Oku</button>
        <p id="readResult"></p>
    </div>
    
    <div class="container">
        <h2>Veri Silme</h2>
        <input type="text" id="deleteKey" placeholder="Anahtar">
        <button onclick="deleteData()">Sil</button>
    </div>
    
    <div class="container">
        <h2>Tüm Verileri Sil</h2>
        <button onclick="clearAll()">Tümünü Sil</button>
    </div>
    
    <script>
        function saveData() {
            const key = document.getElementById('keyInput').value;
            const value = document.getElementById('valueInput').value;
            
            if (key && value) {
                localStorage.setItem(key, value);
                alert('Veri kaydedildi!');
                document.getElementById('keyInput').value = '';
                document.getElementById('valueInput').value = '';
            } else {
                alert('Lütfen anahtar ve değer girin!');
            }
        }
        
        function readData() {
            const key = document.getElementById('readKey').value;
            const value = localStorage.getItem(key);
            
            if (value) {
                document.getElementById('readResult').textContent = `Değer: ${value}`;
            } else {
                document.getElementById('readResult').textContent = 'Veri bulunamadı!';
            }
        }
        
        function deleteData() {
            const key = document.getElementById('deleteKey').value;
            localStorage.removeItem(key);
            alert('Veri silindi!');
            document.getElementById('deleteKey').value = '';
        }
        
        function clearAll() {
            if (confirm('Tüm verileri silmek istediğinize emin misiniz?')) {
                localStorage.clear();
                alert('Tüm veriler silindi!');
            }
        }
    </script>
</body>
</html>
```

### SessionStorage Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>SessionStorage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        input, button {
            padding: 10px;
            margin: 5px;
            border: 1px solid #ddd;
            border-radius: 3px;
        }
        
        button {
            background-color: #27ae60;
            color: white;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>SessionStorage Örneği</h1>
    <p><small>SessionStorage verileri sekme kapanınca silinir.</small></p>
    
    <div class="container">
        <h2>Veri Kaydetme</h2>
        <input type="text" id="keyInput" placeholder="Anahtar">
        <input type="text" id="valueInput" placeholder="Değer">
        <button onclick="saveData()">Kaydet</button>
    </div>
    
    <div class="container">
        <h2>Veri Okuma</h2>
        <input type="text" id="readKey" placeholder="Anahtar">
        <button onclick="readData()">Oku</button>
        <p id="readResult"></p>
    </div>
    
    <script>
        function saveData() {
            const key = document.getElementById('keyInput').value;
            const value = document.getElementById('valueInput').value;
            
            if (key && value) {
                sessionStorage.setItem(key, value);
                alert('Veri kaydedildi!');
            }
        }
        
        function readData() {
            const key = document.getElementById('readKey').value;
            const value = sessionStorage.getItem(key);
            
            if (value) {
                document.getElementById('readResult').textContent = `Değer: ${value}`;
            } else {
                document.getElementById('readResult').textContent = 'Veri bulunamadı!';
            }
        }
    </script>
</body>
</html>
```

### Kullanıcı Tercihlerini Saklama

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kullanıcı Tercihleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
            transition: background-color 0.3s, color 0.3s;
        }
        
        .dark-mode {
            background-color: #2c3e50;
            color: white;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        .dark-mode .container {
            background-color: #34495e;
        }
        
        button {
            padding: 10px 20px;
            margin: 5px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            background-color: #3498db;
            color: white;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        select {
            padding: 10px;
            margin: 5px;
            border: 1px solid #ddd;
            border-radius: 3px;
        }
    </style>
</head>
<body id="body">
    <h1>Kullanıcı Tercihleri</h1>
    
    <div class="container">
        <h2>Tema</h2>
        <button onclick="toggleTheme()">Tema Değiştir</button>
    </div>
    
    <div class="container">
        <h2>Dil</h2>
        <select id="language" onchange="saveLanguage()">
            <option value="tr">Türkçe</option>
            <option value="en">English</option>
            <option value="de">Deutsch</option>
        </select>
    </div>
    
    <div class="container">
        <h2>Font Boyutu</h2>
        <select id="fontSize" onchange="saveFontSize()">
            <option value="small">Küçük</option>
            <option value="medium">Orta</option>
            <option value="large">Büyük</option>
        </select>
    </div>
    
    <script>
        // Sayfa yüklendiğinde tercihleri yükle
        window.addEventListener('DOMContentLoaded', function() {
            loadPreferences();
        });
        
        function loadPreferences() {
            // Tema
            const theme = localStorage.getItem('theme');
            if (theme === 'dark') {
                document.body.classList.add('dark-mode');
            }
            
            // Dil
            const language = localStorage.getItem('language');
            if (language) {
                document.getElementById('language').value = language;
            }
            
            // Font boyutu
            const fontSize = localStorage.getItem('fontSize');
            if (fontSize) {
                document.getElementById('fontSize').value = fontSize;
                applyFontSize(fontSize);
            }
        }
        
        function toggleTheme() {
            document.body.classList.toggle('dark-mode');
            const theme = document.body.classList.contains('dark-mode') ? 'dark' : 'light';
            localStorage.setItem('theme', theme);
        }
        
        function saveLanguage() {
            const language = document.getElementById('language').value;
            localStorage.setItem('language', language);
            alert('Dil tercihi kaydedildi!');
        }
        
        function saveFontSize() {
            const fontSize = document.getElementById('fontSize').value;
            localStorage.setItem('fontSize', fontSize);
            applyFontSize(fontSize);
        }
        
        function applyFontSize(size) {
            const sizes = {
                small: '14px',
                medium: '16px',
                large: '18px'
            };
            document.body.style.fontSize = sizes[size];
        }
    </script>
</body>
</html>
```

### Alışveriş Sepeti Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Alışveriş Sepeti</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .product {
            border: 1px solid #ddd;
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
        }
        
        button {
            padding: 8px 15px;
            margin: 5px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            background-color: #27ae60;
            color: white;
        }
        
        .cart {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Alışveriş Sepeti</h1>
    
    <div class="product">
        <h3>Ürün 1 - 100 TL</h3>
        <button onclick="addToCart('Ürün 1', 100)">Sepete Ekle</button>
    </div>
    
    <div class="product">
        <h3>Ürün 2 - 200 TL</h3>
        <button onclick="addToCart('Ürün 2', 200)">Sepete Ekle</button>
    </div>
    
    <div class="product">
        <h3>Ürün 3 - 150 TL</h3>
        <button onclick="addToCart('Ürün 3', 150)">Sepete Ekle</button>
    </div>
    
    <div class="cart">
        <h2>Sepetim</h2>
        <div id="cartItems"></div>
        <p><strong>Toplam: <span id="total">0</span> TL</strong></p>
        <button onclick="clearCart()">Sepeti Temizle</button>
    </div>
    
    <script>
        // Sepeti yükle
        loadCart();
        
        function addToCart(productName, price) {
            let cart = JSON.parse(localStorage.getItem('cart') || '[]');
            
            cart.push({
                name: productName,
                price: price
            });
            
            localStorage.setItem('cart', JSON.stringify(cart));
            loadCart();
        }
        
        function loadCart() {
            const cart = JSON.parse(localStorage.getItem('cart') || '[]');
            const cartItems = document.getElementById('cartItems');
            const total = document.getElementById('total');
            
            cartItems.innerHTML = '';
            let totalPrice = 0;
            
            cart.forEach((item, index) => {
                const div = document.createElement('div');
                div.innerHTML = `
                    ${item.name} - ${item.price} TL 
                    <button onclick="removeFromCart(${index})">Kaldır</button>
                `;
                cartItems.appendChild(div);
                totalPrice += item.price;
            });
            
            total.textContent = totalPrice;
        }
        
        function removeFromCart(index) {
            let cart = JSON.parse(localStorage.getItem('cart') || '[]');
            cart.splice(index, 1);
            localStorage.setItem('cart', JSON.stringify(cart));
            loadCart();
        }
        
        function clearCart() {
            localStorage.removeItem('cart');
            loadCart();
        }
    </script>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Veri Tipi**: Storage'da sadece string saklanır. Objeler için `JSON.stringify()` ve `JSON.parse()` kullanın.

2. **Boyut Limiti**: LocalStorage genellikle 5-10 MB sınırına sahiptir.

3. **Güvenlik**: Hassas veriler localStorage'da saklanmamalıdır.

4. **Tarayıcı Desteği**: Modern tarayıcılar storage API'lerini destekler.

5. **Fark**: `localStorage` kalıcı, `sessionStorage` geçicidir.

## 🎯 İyi Pratikler

- Objeler için JSON kullanın
- Veri boyutunu kontrol edin
- Hassas veriler saklamayın
- Hata yönetimi yapın
- Kullanıcı tercihlerini saklayın
- Alışveriş sepeti gibi geçici veriler için kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


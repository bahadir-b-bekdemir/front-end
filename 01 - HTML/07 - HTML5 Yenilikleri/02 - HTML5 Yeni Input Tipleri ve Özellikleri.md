# 📝 HTML5 YENİ INPUT TİPLERİ VE ÖZELLİKLERİ

**HTML5** ile birlikte birçok yeni input tipi ve özellik eklendi. Bu yenilikler kullanıcı deneyimini iyileştirir ve validasyonu kolaylaştırır.

## 📋 Yeni Input Tipleri

| Tip | Açıklama | Kullanım |
| :-- | :------- | :------- |
| `email` | E-posta girişi | E-posta adresi |
| `url` | URL girişi | Web adresi |
| `tel` | Telefon girişi | Telefon numarası |
| `search` | Arama girişi | Arama kutusu |
| `number` | Sayı girişi | Sayısal değer |
| `range` | Aralık seçici | Slider |
| `date` | Tarih seçici | Tarih |
| `time` | Saat seçici | Saat |
| `datetime-local` | Tarih ve saat | Tarih + saat |
| `month` | Ay seçici | Ay |
| `week` | Hafta seçici | Hafta |
| `color` | Renk seçici | Renk |

## 📋 Yeni Özellikler

### `placeholder` Özelliği

Kullanıcıya rehberlik eden örnek metin.

### `autocomplete` Özelliği

Tarayıcı otomatik tamamlama kontrolü.

### `autofocus` Özelliği

Sayfa yüklendiğinde otomatik odaklanma.

### `required` Özelliği

Alanın doldurulması zorunludur.

### `pattern` Özelliği

Düzenli ifade ile format kontrolü.

### `min`, `max`, `step` Özellikleri

Sayısal değerler için sınırlar.

## 💡 Kullanım Örnekleri

### Yeni Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Yeni Input Tipleri</title>
    <style>
        form {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h2>HTML5 Yeni Input Tipleri</h2>
    <form>
        <label for="email">E-posta:</label>
        <input type="email" id="email" name="email" placeholder="ornek@email.com">
        
        <label for="url">Web Sitesi:</label>
        <input type="url" id="url" name="url" placeholder="https://www.example.com">
        
        <label for="tel">Telefon:</label>
        <input type="tel" id="tel" name="tel" placeholder="0555 123 45 67">
        
        <label for="search">Arama:</label>
        <input type="search" id="search" name="search" placeholder="Ara...">
        
        <label for="number">Sayı:</label>
        <input type="number" id="number" name="number" min="0" max="100" step="1">
        
        <label for="range">Aralık:</label>
        <input type="range" id="range" name="range" min="0" max="100" value="50">
        <output for="range">50</output>
        
        <label for="date">Tarih:</label>
        <input type="date" id="date" name="date">
        
        <label for="time">Saat:</label>
        <input type="time" id="time" name="time">
        
        <label for="datetime">Tarih ve Saat:</label>
        <input type="datetime-local" id="datetime" name="datetime">
        
        <label for="month">Ay:</label>
        <input type="month" id="month" name="month">
        
        <label for="week">Hafta:</label>
        <input type="week" id="week" name="week">
        
        <label for="color">Renk:</label>
        <input type="color" id="color" name="color" value="#3498db">
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Placeholder ve Autocomplete

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Placeholder ve Autocomplete</title>
    <style>
        form {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h2>Placeholder ve Autocomplete</h2>
    <form autocomplete="on">
        <label for="isim">İsim:</label>
        <input 
            type="text" 
            id="isim" 
            name="isim" 
            placeholder="Adınızı girin"
            autocomplete="name">
        
        <label for="email">E-posta:</label>
        <input 
            type="email" 
            id="email" 
            name="email" 
            placeholder="ornek@email.com"
            autocomplete="email">
        
        <label for="adres">Adres:</label>
        <input 
            type="text" 
            id="adres" 
            name="adres" 
            placeholder="Adresinizi girin"
            autocomplete="street-address">
        
        <label for="sehir">Şehir:</label>
        <input 
            type="text" 
            id="sehir" 
            name="sehir" 
            placeholder="Şehrinizi girin"
            autocomplete="address-level2">
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Pattern ve Validasyon

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Pattern ve Validasyon</title>
    <style>
        form {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
        
        input:invalid {
            border-color: #e74c3c;
        }
        
        input:valid {
            border-color: #27ae60;
        }
    </style>
</head>
<body>
    <h2>Pattern ve Validasyon</h2>
    <form>
        <label for="telefon">Telefon (555-123-4567):</label>
        <input 
            type="tel" 
            id="telefon" 
            name="telefon" 
            pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
            placeholder="555-123-4567"
            title="Format: 555-123-4567"
            required>
        
        <label for="posta">Posta Kodu (5 haneli):</label>
        <input 
            type="text" 
            id="posta" 
            name="posta" 
            pattern="[0-9]{5}"
            placeholder="06100"
            title="5 haneli posta kodu"
            required>
        
        <label for="kullanici_adi">Kullanıcı Adı (sadece harf ve sayı):</label>
        <input 
            type="text" 
            id="kullanici_adi" 
            name="kullanici_adi" 
            pattern="[A-Za-z0-9]+"
            minlength="3"
            maxlength="15"
            title="Sadece harf ve sayı, 3-15 karakter"
            required>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Min, Max, Step ve Range

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Min, Max, Step</title>
    <style>
        form {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
        
        output {
            display: block;
            margin-top: -10px;
            margin-bottom: 15px;
            font-weight: bold;
            color: #3498db;
        }
    </style>
</head>
<body>
    <h2>Min, Max, Step ve Range</h2>
    <form>
        <label for="yas">Yaş (18-100):</label>
        <input 
            type="number" 
            id="yas" 
            name="yas" 
            min="18" 
            max="100"
            step="1"
            required>
        
        <label for="puan">Puan (0-100, 0.5 artış):</label>
        <input 
            type="number" 
            id="puan" 
            name="puan" 
            min="0" 
            max="100"
            step="0.5"
            required>
        
        <label for="fiyat">Fiyat (0-10000, 10 artış):</label>
        <input 
            type="number" 
            id="fiyat" 
            name="fiyat" 
            min="0" 
            max="10000"
            step="10"
            required>
        
        <label for="hacim">Hacim (0-100):</label>
        <input 
            type="range" 
            id="hacim" 
            name="hacim" 
            min="0" 
            max="100" 
            value="50"
            step="1">
        <output for="hacim">50</output>
        
        <button type="submit">Gönder</button>
    </form>
    
    <script>
        const range = document.getElementById('hacim');
        const output = document.querySelector('output[for="hacim"]');
        
        range.addEventListener('input', function() {
            output.textContent = this.value;
        });
    </script>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı HTML5 Input Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        form {
            background-color: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
        }
        
        fieldset {
            border: 2px solid #3498db;
            border-radius: 5px;
            padding: 20px;
            margin-bottom: 20px;
        }
        
        legend {
            padding: 0 15px;
            font-weight: bold;
            color: #2c3e50;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #2c3e50;
        }
        
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box;
        }
        
        input:focus {
            outline: none;
            border-color: #3498db;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
        }
        
        input:invalid:not(:focus):not(:placeholder-shown) {
            border-color: #e74c3c;
        }
        
        input:valid:not(:focus):not(:placeholder-shown) {
            border-color: #27ae60;
        }
        
        output {
            display: block;
            margin-top: -10px;
            margin-bottom: 15px;
            font-weight: bold;
            color: #3498db;
        }
        
        button {
            background-color: #27ae60;
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }
    </style>
</head>
<body>
    <h1>HTML5 Yeni Input Özellikleri</h1>
    
    <form method="POST" action="/form" autocomplete="on">
        <fieldset>
            <legend>İletişim Bilgileri</legend>
            
            <label for="email">E-posta:</label>
            <input 
                type="email" 
                id="email" 
                name="email" 
                placeholder="ornek@email.com"
                autocomplete="email"
                required>
            
            <label for="url">Web Sitesi:</label>
            <input 
                type="url" 
                id="url" 
                name="url" 
                placeholder="https://www.example.com"
                autocomplete="url">
            
            <label for="tel">Telefon:</label>
            <input 
                type="tel" 
                id="tel" 
                name="tel" 
                pattern="[0-9]{10,11}"
                placeholder="05551234567"
                autocomplete="tel"
                required>
        </fieldset>
        
        <fieldset>
            <legend>Tarih ve Sayı</legend>
            
            <label for="dogum">Doğum Tarihi:</label>
            <input type="date" id="dogum" name="dogum" required>
            
            <label for="yas">Yaş:</label>
            <input 
                type="number" 
                id="yas" 
                name="yas" 
                min="18" 
                max="100"
                step="1"
                required>
            
            <label for="puan">Puan (0-100):</label>
            <input 
                type="range" 
                id="puan" 
                name="puan" 
                min="0" 
                max="100" 
                value="50"
                step="1">
            <output for="puan">50</output>
        </fieldset>
        
        <fieldset>
            <legend>Diğer</legend>
            
            <label for="renk">Favori Renk:</label>
            <input type="color" id="renk" name="renk" value="#3498db">
            
            <label for="arama">Arama:</label>
            <input 
                type="search" 
                id="arama" 
                name="arama" 
                placeholder="Ara...">
        </fieldset>
        
        <button type="submit">Gönder</button>
    </form>
    
    <script>
        const puanRange = document.getElementById('puan');
        const puanOutput = document.querySelector('output[for="puan"]');
        
        puanRange.addEventListener('input', function() {
            puanOutput.textContent = this.value;
        });
    </script>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Tarayıcı Desteği**: Bazı input tipleri eski tarayıcılarda text olarak görünebilir.

2. **Mobil Uyumluluk**: `date`, `time` gibi tipler mobilde özel klavye açar.

3. **Validasyon**: HTML5 input tipleri otomatik validasyon sağlar.

4. **Autocomplete**: Tarayıcı otomatik tamamlama için `autocomplete` kullanır.

5. **Pattern**: Düzenli ifade ile format kontrolü yapılabilir.

## 🎯 İyi Pratikler

- Uygun input tipini seçin
- `placeholder` ile kullanıcıya rehberlik edin
- `autocomplete` ile kullanıcı deneyimini iyileştirin
- `pattern` ile format kontrolü yapın
- `min`, `max`, `step` ile sınırlar belirleyin
- `required` ile zorunlu alanları işaretleyin
- Mobil uyumluluğu test edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


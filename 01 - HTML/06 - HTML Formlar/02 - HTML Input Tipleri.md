# 📝 HTML INPUT TİPLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) farklı veri tipleri için farklı `input` tipleri kullanılır. `type` özelliği ile belirtilir.

## 📋 Input Tipleri

| Tip | Açıklama | Kullanım |
| :-- | :------- | :------- |
| `text` | Metin girişi | Genel metin |
| `email` | E-posta girişi | E-posta adresi |
| `password` | Şifre girişi | Şifre |
| `number` | Sayı girişi | Sayısal değer |
| `tel` | Telefon girişi | Telefon numarası |
| `url` | URL girişi | Web adresi |
| `date` | Tarih seçici | Tarih |
| `time` | Saat seçici | Saat |
| `datetime-local` | Tarih ve saat | Tarih ve saat |
| `month` | Ay seçici | Ay |
| `week` | Hafta seçici | Hafta |
| `color` | Renk seçici | Renk |
| `range` | Aralık seçici | Aralık |
| `file` | Dosya seçici | Dosya yükleme |
| `checkbox` | Onay kutusu | Çoklu seçim |
| `radio` | Radyo butonu | Tekli seçim |
| `submit` | Gönder butonu | Form gönderme |
| `reset` | Sıfırla butonu | Form sıfırlama |
| `button` | Buton | Genel buton |
| `hidden` | Gizli alan | Gizli veri |

## 💡 Kullanım Örnekleri

### Metin Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Metin Input Tipleri</title>
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
    <h2>Metin Input Tipleri</h2>
    <form>
        <label for="text">Metin (text):</label>
        <input type="text" id="text" name="text" placeholder="Metin girin">
        
        <label for="email">E-posta (email):</label>
        <input type="email" id="email" name="email" placeholder="ornek@email.com">
        
        <label for="password">Şifre (password):</label>
        <input type="password" id="password" name="password" placeholder="Şifre girin">
        
        <label for="url">URL (url):</label>
        <input type="url" id="url" name="url" placeholder="https://www.example.com">
        
        <label for="tel">Telefon (tel):</label>
        <input type="tel" id="tel" name="tel" placeholder="0555 123 45 67">
        
        <label for="search">Arama (search):</label>
        <input type="search" id="search" name="search" placeholder="Ara...">
    </form>
</body>
</html>
```

### Sayısal Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sayısal Input Tipleri</title>
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
    <h2>Sayısal Input Tipleri</h2>
    <form>
        <label for="number">Sayı (number):</label>
        <input type="number" id="number" name="number" min="0" max="100" step="1">
        
        <label for="range">Aralık (range):</label>
        <input type="range" id="range" name="range" min="0" max="100" value="50">
        <output for="range">50</output>
        
        <label for="price">Fiyat:</label>
        <input type="number" id="price" name="price" min="0" step="0.01" placeholder="0.00">
    </form>
</body>
</html>
```

### Tarih ve Saat Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Tarih ve Saat Input Tipleri</title>
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
    <h2>Tarih ve Saat Input Tipleri</h2>
    <form>
        <label for="date">Tarih (date):</label>
        <input type="date" id="date" name="date">
        
        <label for="time">Saat (time):</label>
        <input type="time" id="time" name="time">
        
        <label for="datetime">Tarih ve Saat (datetime-local):</label>
        <input type="datetime-local" id="datetime" name="datetime">
        
        <label for="month">Ay (month):</label>
        <input type="month" id="month" name="month">
        
        <label for="week">Hafta (week):</label>
        <input type="week" id="week" name="week">
    </form>
</body>
</html>
```

### Seçim Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Seçim Input Tipleri</title>
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
        
        input[type="checkbox"], input[type="radio"] {
            width: auto;
            margin-right: 5px;
        }
        
        .checkbox-group, .radio-group {
            margin-bottom: 15px;
        }
    </style>
</head>
<body>
    <h2>Seçim Input Tipleri</h2>
    <form>
        <fieldset>
            <legend>Hobiler (Checkbox)</legend>
            <div class="checkbox-group">
                <input type="checkbox" id="hobi1" name="hobiler" value="okuma">
                <label for="hobi1">Okuma</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="hobi2" name="hobiler" value="spor">
                <label for="hobi2">Spor</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="hobi3" name="hobiler" value="muzik">
                <label for="hobi3">Müzik</label>
            </div>
        </fieldset>
        
        <fieldset>
            <legend>Cinsiyet (Radio)</legend>
            <div class="radio-group">
                <input type="radio" id="erkek" name="cinsiyet" value="erkek">
                <label for="erkek">Erkek</label>
            </div>
            <div class="radio-group">
                <input type="radio" id="kadin" name="cinsiyet" value="kadin">
                <label for="kadin">Kadın</label>
            </div>
        </fieldset>
    </form>
</body>
</html>
```

### Dosya ve Diğer Input Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Dosya ve Diğer Input Tipleri</title>
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
        
        input[type="color"] {
            height: 50px;
        }
        
        input[type="file"] {
            padding: 5px;
        }
    </style>
</head>
<body>
    <h2>Dosya ve Diğer Input Tipleri</h2>
    <form>
        <label for="file">Dosya (file):</label>
        <input type="file" id="file" name="file" accept="image/*">
        
        <label for="color">Renk (color):</label>
        <input type="color" id="color" name="color" value="#3498db">
        
        <label for="range">Aralık (range):</label>
        <input type="range" id="range" name="range" min="0" max="100" value="50">
        <output for="range">50</output>
    </form>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Input Tipleri</title>
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
        
        input, select, textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box;
        }
        
        input[type="checkbox"], input[type="radio"] {
            width: auto;
            margin-right: 8px;
        }
        
        .checkbox-group, .radio-group {
            margin-bottom: 10px;
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
    <h1>Kapsamlı Form Örneği</h1>
    
    <form method="POST" action="/form">
        <fieldset>
            <legend>Kişisel Bilgiler</legend>
            
            <label for="ad">Ad:</label>
            <input type="text" id="ad" name="ad" required>
            
            <label for="email">E-posta:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="telefon">Telefon:</label>
            <input type="tel" id="telefon" name="telefon">
            
            <label for="website">Web Sitesi:</label>
            <input type="url" id="website" name="website">
        </fieldset>
        
        <fieldset>
            <legend>Tarih ve Sayı</legend>
            
            <label for="dogum">Doğum Tarihi:</label>
            <input type="date" id="dogum" name="dogum">
            
            <label for="yas">Yaş:</label>
            <input type="number" id="yas" name="yas" min="0" max="120">
            
            <label for="puan">Puan (0-100):</label>
            <input type="range" id="puan" name="puan" min="0" max="100" value="50">
            <output for="puan">50</output>
        </fieldset>
        
        <fieldset>
            <legend>Seçimler</legend>
            
            <label>Cinsiyet:</label>
            <div class="radio-group">
                <input type="radio" id="erkek" name="cinsiyet" value="erkek">
                <label for="erkek">Erkek</label>
            </div>
            <div class="radio-group">
                <input type="radio" id="kadin" name="cinsiyet" value="kadin">
                <label for="kadin">Kadın</label>
            </div>
            
            <label>Hobiler:</label>
            <div class="checkbox-group">
                <input type="checkbox" id="okuma" name="hobiler" value="okuma">
                <label for="okuma">Okuma</label>
            </div>
            <div class="checkbox-group">
                <input type="checkbox" id="spor" name="hobiler" value="spor">
                <label for="spor">Spor</label>
            </div>
        </fieldset>
        
        <fieldset>
            <legend>Dosya ve Renk</legend>
            
            <label for="resim">Resim Yükle:</label>
            <input type="file" id="resim" name="resim" accept="image/*">
            
            <label for="renk">Favori Renk:</label>
            <input type="color" id="renk" name="renk" value="#3498db">
        </fieldset>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Tarayıcı Desteği**: Bazı input tipleri eski tarayıcılarda desteklenmeyebilir.

2. **Validasyon**: `email`, `url`, `number` gibi tipler otomatik validasyon sağlar.

3. **Mobil Uyumluluk**: `date`, `time` gibi tipler mobilde özel klavye açar.

4. **name Özelliği**: Tüm input'lar için `name` özelliği zorunludur (form gönderme için).

5. **required**: Zorunlu alanlar için `required` özelliği kullanılır.

## 🎯 İyi Pratikler

- Uygun input tipini seçin
- `name` özelliğini mutlaka ekleyin
- Zorunlu alanlar için `required` kullanın
- `placeholder` ile kullanıcıya rehberlik edin
- `min`, `max`, `step` ile sayısal sınırlar belirleyin
- Erişilebilirlik için `label` kullanın
- Mobil uyumluluğu test edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


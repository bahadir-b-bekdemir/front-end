# 📝 HTML TEXTAREA VE SELECT

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) çok satırlı metin girişi için `<textarea>` ve seçim listesi için `<select>` etiketleri kullanılır.

## 📋 Textarea Etiketi

### `<textarea>...</textarea>`

Çok satırlı metin girişi için kullanılır. Kapatılır ve içinde varsayılan metin olabilir.

### `rows` Özelliği

Textarea'nın görünen satır sayısı.

### `cols` Özelliği

Textarea'nın görünen sütun sayısı (artık önerilmiyor, CSS kullanın).

## 📋 Select Etiketi

### `<select>...</select>`

Açılır liste (dropdown) oluşturur. İçinde `<option>` etiketleri bulunur.

### `<option>...</option>`

Seçim listesindeki her bir seçenek.

### `<optgroup>...</optgroup>`

Seçenekleri gruplamak için kullanılır.

## 💡 Kullanım Örnekleri

### Temel Textarea

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Textarea</title>
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
        
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
    </style>
</head>
<body>
    <h2>Textarea Örnekleri</h2>
    <form>
        <label for="mesaj1">Mesaj (3 satır):</label>
        <textarea id="mesaj1" name="mesaj1" rows="3"></textarea>
        
        <label for="mesaj2">Açıklama (5 satır):</label>
        <textarea id="mesaj2" name="mesaj2" rows="5" placeholder="Açıklama yazın..."></textarea>
        
        <label for="mesaj3">Varsayılan Metin:</label>
        <textarea id="mesaj3" name="mesaj3" rows="4">Bu varsayılan metindir.</textarea>
    </form>
</body>
</html>
```

### Temel Select

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Select</title>
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
        
        select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h2>Select Örnekleri</h2>
    <form>
        <label for="sehir">Şehir:</label>
        <select id="sehir" name="sehir">
            <option value="">Seçiniz...</option>
            <option value="istanbul">İstanbul</option>
            <option value="ankara">Ankara</option>
            <option value="izmir">İzmir</option>
            <option value="antalya">Antalya</option>
        </select>
        
        <label for="ulke">Ülke:</label>
        <select id="ulke" name="ulke" required>
            <option value="tr">Türkiye</option>
            <option value="us">Amerika</option>
            <option value="uk">İngiltere</option>
            <option value="de">Almanya</option>
        </select>
    </form>
</body>
</html>
```

### Optgroup ile Gruplama

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Optgroup Örneği</title>
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
        
        select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h2>Optgroup ile Gruplama</h2>
    <form>
        <label for="kategori">Kategori:</label>
        <select id="kategori" name="kategori">
            <optgroup label="Elektronik">
                <option value="laptop">Laptop</option>
                <option value="telefon">Telefon</option>
                <option value="tablet">Tablet</option>
            </optgroup>
            <optgroup label="Giyim">
                <option value="gomlek">Gömlek</option>
                <option value="pantolon">Pantolon</option>
                <option value="ayakkabi">Ayakkabı</option>
            </optgroup>
            <optgroup label="Ev Eşyası">
                <option value="mobilya">Mobilya</option>
                <option value="mutfak">Mutfak</option>
            </optgroup>
        </select>
    </form>
</body>
</html>
```

### Multiple Select

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Multiple Select</title>
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
        
        select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
        
        select[multiple] {
            height: 150px;
        }
    </style>
</head>
<body>
    <h2>Çoklu Seçim (Multiple)</h2>
    <form>
        <label for="diller">Bildiğiniz Diller (Ctrl/Cmd ile çoklu seçim):</label>
        <select id="diller" name="diller" multiple size="5">
            <option value="turkce">Türkçe</option>
            <option value="ingilizce">İngilizce</option>
            <option value="almanca">Almanca</option>
            <option value="fransizca">Fransızca</option>
            <option value="ispanyolca">İspanyolca</option>
        </select>
        <p><small>Çoklu seçim için Ctrl (Windows) veya Cmd (Mac) tuşuna basılı tutun.</small></p>
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
    <title>Kapsamlı Textarea ve Select</title>
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
            font-family: Arial, sans-serif;
        }
        
        textarea {
            resize: vertical;
            min-height: 100px;
        }
        
        select[multiple] {
            height: 120px;
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
    <h1>İletişim ve Seçim Formu</h1>
    
    <form method="POST" action="/form">
        <fieldset>
            <legend>İletişim Bilgileri</legend>
            
            <label for="ad">Ad Soyad:</label>
            <input type="text" id="ad" name="ad" required>
            
            <label for="email">E-posta:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="konu">Konu:</label>
            <select id="konu" name="konu" required>
                <option value="">Seçiniz...</option>
                <option value="bilgi">Bilgi</option>
                <option value="destek">Destek</option>
                <option value="siparis">Sipariş</option>
                <option value="diger">Diğer</option>
            </select>
        </fieldset>
        
        <fieldset>
            <legend>Mesaj</legend>
            
            <label for="mesaj">Mesajınız:</label>
            <textarea 
                id="mesaj" 
                name="mesaj" 
                rows="6" 
                placeholder="Mesajınızı buraya yazın..."
                required></textarea>
        </fieldset>
        
        <fieldset>
            <legend>Tercihler</legend>
            
            <label for="sehir">Şehir:</label>
            <select id="sehir" name="sehir" required>
                <optgroup label="Marmara">
                    <option value="istanbul">İstanbul</option>
                    <option value="bursa">Bursa</option>
                </optgroup>
                <optgroup label="İç Anadolu">
                    <option value="ankara">Ankara</option>
                    <option value="konya">Konya</option>
                </optgroup>
                <optgroup label="Ege">
                    <option value="izmir">İzmir</option>
                    <option value="antalya">Antalya</option>
                </optgroup>
            </select>
            
            <label for="ilgi_alanlari">İlgi Alanları (Çoklu seçim):</label>
            <select id="ilgi_alanlari" name="ilgi_alanlari" multiple size="4">
                <option value="teknoloji">Teknoloji</option>
                <option value="spor">Spor</option>
                <option value="sanat">Sanat</option>
                <option value="bilim">Bilim</option>
                <option value="edebiyat">Edebiyat</option>
            </select>
            <p><small>Çoklu seçim için Ctrl/Cmd tuşuna basılı tutun.</small></p>
        </fieldset>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Textarea**: `cols` özelliği artık önerilmiyor, genişlik için **CSS** kullanın.

2. **resize**: Textarea'nın boyutlandırılabilirliği **CSS** `resize` özelliği ile kontrol edilir.

3. **Select**: `multiple` özelliği ile çoklu seçim yapılabilir.

4. **Optgroup**: Seçenekleri gruplamak için kullanılır, görsel olarak ayırır.

5. **name Özelliği**: Her `textarea` ve `select` için `name` özelliği zorunludur.

6. **required**: Zorunlu alanlar için `required` özelliği kullanılır.

## 🎯 İyi Pratikler

- Textarea için uygun `rows` değeri kullanın
- Select için varsayılan seçenek ekleyin ("Seçiniz...")
- Optgroup ile seçenekleri gruplayın
- Çoklu seçim için `multiple` kullanın
- `name` özelliğini mutlaka ekleyin
- Zorunlu alanlar için `required` kullanın
- Erişilebilirlik için `label` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


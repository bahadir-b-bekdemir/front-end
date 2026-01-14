# ✅ HTML FORM VALİDASYONU

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) form validasyonu için HTML5 validasyon özellikleri kullanılır. Tarayıcı tarafında otomatik validasyon sağlar.

## 📋 Validasyon Özellikleri

### `required` Özelliği

Alanın doldurulması zorunludur.

### `pattern` Özelliği

Düzenli ifade (regex) ile format kontrolü.

### `min` ve `max` Özellikleri

Sayısal değerler için minimum ve maksimum sınırlar.

### `minlength` ve `maxlength` Özellikleri

Metin uzunluğu için minimum ve maksimum sınırlar.

### `type` Özelliği

Input tipine göre otomatik validasyon (email, url, number vb.).

## 💡 Kullanım Örnekleri

### required Validasyonu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>required Validasyonu</title>
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
        
        .required {
            color: #e74c3c;
        }
    </style>
</head>
<body>
    <h2>Zorunlu Alanlar</h2>
    <form>
        <label for="isim">
            İsim <span class="required">*</span>
        </label>
        <input type="text" id="isim" name="isim" required>
        
        <label for="email">
            E-posta <span class="required">*</span>
        </label>
        <input type="email" id="email" name="email" required>
        
        <label for="telefon">Telefon</label>
        <input type="tel" id="telefon" name="telefon">
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### pattern Validasyonu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>pattern Validasyonu</title>
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
    <h2>Pattern Validasyonu</h2>
    <form>
        <label for="telefon">Telefon (555-123-4567 formatı):</label>
        <input 
            type="tel" 
            id="telefon" 
            name="telefon" 
            pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
            placeholder="555-123-4567"
            title="Format: 555-123-4567">
        
        <label for="posta">Posta Kodu (5 haneli):</label>
        <input 
            type="text" 
            id="posta" 
            name="posta" 
            pattern="[0-9]{5}"
            placeholder="06100"
            title="5 haneli posta kodu">
        
        <label for="kullanici_adi">Kullanıcı Adı (sadece harf ve sayı):</label>
        <input 
            type="text" 
            id="kullanici_adi" 
            name="kullanici_adi" 
            pattern="[A-Za-z0-9]+"
            title="Sadece harf ve sayı">
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### min, max, minlength, maxlength

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>min, max, length Validasyonu</title>
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
    <h2>Sayı ve Uzunluk Validasyonu</h2>
    <form>
        <label for="yas">Yaş (18-100):</label>
        <input 
            type="number" 
            id="yas" 
            name="yas" 
            min="18" 
            max="100"
            required>
        
        <label for="puan">Puan (0-100):</label>
        <input 
            type="number" 
            id="puan" 
            name="puan" 
            min="0" 
            max="100"
            step="1"
            required>
        
        <label for="sifre">Şifre (en az 8 karakter):</label>
        <input 
            type="password" 
            id="sifre" 
            name="sifre" 
            minlength="8"
            maxlength="20"
            required>
        
        <label for="kullanici_adi">Kullanıcı Adı (3-15 karakter):</label>
        <input 
            type="text" 
            id="kullanici_adi" 
            name="kullanici_adi" 
            minlength="3"
            maxlength="15"
            required>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Kapsamlı Validasyon Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Validasyon</title>
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
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #2c3e50;
        }
        
        input, select {
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
        
        .required {
            color: #e74c3c;
        }
        
        .help-text {
            font-size: 0.85em;
            color: #666;
            margin-top: -10px;
            margin-bottom: 15px;
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
        
        button:hover {
            background-color: #229954;
        }
    </style>
</head>
<body>
    <h1>Kayıt Formu (Validasyonlu)</h1>
    
    <form method="POST" action="/kayit" novalidate>
        <label for="kullanici_adi">
            Kullanıcı Adı <span class="required">*</span>
        </label>
        <input 
            type="text" 
            id="kullanici_adi" 
            name="kullanici_adi" 
            pattern="[A-Za-z0-9_]{3,15}"
            minlength="3"
            maxlength="15"
            required
            placeholder="En az 3, en fazla 15 karakter">
        <p class="help-text">Sadece harf, sayı ve alt çizgi. 3-15 karakter arası.</p>
        
        <label for="email">
            E-posta <span class="required">*</span>
        </label>
        <input 
            type="email" 
            id="email" 
            name="email" 
            required
            placeholder="ornek@email.com">
        
        <label for="sifre">
            Şifre <span class="required">*</span>
        </label>
        <input 
            type="password" 
            id="sifre" 
            name="sifre" 
            minlength="8"
            maxlength="20"
            required
            placeholder="En az 8 karakter">
        <p class="help-text">En az 8 karakter olmalıdır.</p>
        
        <label for="telefon">
            Telefon <span class="required">*</span>
        </label>
        <input 
            type="tel" 
            id="telefon" 
            name="telefon" 
            pattern="[0-9]{10,11}"
            required
            placeholder="05551234567">
        <p class="help-text">10 veya 11 haneli telefon numarası.</p>
        
        <label for="yas">
            Yaş <span class="required">*</span>
        </label>
        <input 
            type="number" 
            id="yas" 
            name="yas" 
            min="18"
            max="100"
            required>
        <p class="help-text">18-100 yaş arası.</p>
        
        <label for="website">Web Sitesi</label>
        <input 
            type="url" 
            id="website" 
            name="website" 
            placeholder="https://www.example.com">
        
        <button type="submit">Kayıt Ol</button>
    </form>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Tarayıcı Validasyonu**: HTML5 validasyon tarayıcı tarafında otomatik çalışır.

2. **novalidate**: Form özelliği ile tarayıcı validasyonu kapatılabilir (JavaScript validasyonu için).

3. **title Özelliği**: `pattern` kullanıldığında `title` ile hata mesajı özelleştirilebilir.

4. **CSS Pseudo-classes**: `:valid`, `:invalid`, `:required` ile stil verilebilir.

5. **JavaScript**: Daha gelişmiş validasyon için JavaScript kullanılabilir.

6. **Sunucu Validasyonu**: Her zaman sunucu tarafında da validasyon yapılmalıdır.

## 🎯 İyi Pratikler

- Zorunlu alanlar için `required` kullanın
- Format kontrolü için `pattern` kullanın
- Sayısal sınırlar için `min` ve `max` kullanın
- Metin uzunluğu için `minlength` ve `maxlength` kullanın
- `title` ile kullanıcıya rehberlik edin
- CSS ile görsel geri bildirim sağlayın
- Sunucu tarafında da validasyon yapın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


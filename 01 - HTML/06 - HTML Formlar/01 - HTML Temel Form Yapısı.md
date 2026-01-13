# 📝 HTML TEMEL FORM YAPISI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) kullanıcıdan veri almak için formlar kullanılır. Formlar `<form>` etiketi ile oluşturulur.

## 📋 Form Etiketleri

### `<form>...</form>`

Form kapsayıcısı. Tüm form elemanları bu etiket içinde yer alır.

### `<input>`

Kullanıcı girişi için kullanılan etiket. Kapatılmaz (self-closing tag).

### `<label>...</label>`

Form elemanları için etiket. Erişilebilirlik için önemlidir.

### `<button>...</button>`

Buton etiketi. Form gönderme veya işlemler için kullanılır.

**Temel kullanım:**
```html
<form>
    <label for="isim">İsim:</label>
    <input type="text" id="isim" name="isim">
    <button type="submit">Gönder</button>
</form>
```

## 📋 Form Özellikleri

### `action` Özelliği

Formun gönderileceği URL. Sunucu tarafı işleme için kullanılır.

### `method` Özelliği

Form gönderme yöntemi. `GET` veya `POST` değerlerini alır.

### `name` Özelliği

Form elemanının adı. Sunucuya gönderilirken kullanılır.

### `id` Özelliği

Form elemanının benzersiz kimliği. `label` ile ilişkilendirme için kullanılır.

## 💡 Kullanım Örnekleri

### Basit Form

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Basit Form</title>
    <style>
        form {
            max-width: 400px;
            margin: 20px auto;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
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
        
        button {
            background-color: #3498db;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #2980b9;
        }
    </style>
</head>
<body>
    <h2>İletişim Formu</h2>
    <form>
        <label for="isim">İsim:</label>
        <input type="text" id="isim" name="isim" required>
        
        <label for="email">E-posta:</label>
        <input type="email" id="email" name="email" required>
        
        <label for="mesaj">Mesaj:</label>
        <textarea id="mesaj" name="mesaj" rows="5" required></textarea>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### GET ve POST Metodları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>GET ve POST</title>
</head>
<body>
    <h2>GET Metodu (Arama)</h2>
    <form method="GET" action="/arama">
        <label for="arama">Ara:</label>
        <input type="text" id="arama" name="q" placeholder="Arama yapın...">
        <button type="submit">Ara</button>
    </form>
    
    <h2>POST Metodu (Gizli Veri)</h2>
    <form method="POST" action="/giris">
        <label for="kullanici">Kullanıcı Adı:</label>
        <input type="text" id="kullanici" name="username" required>
        
        <label for="sifre">Şifre:</label>
        <input type="password" id="sifre" name="password" required>
        
        <button type="submit">Giriş Yap</button>
    </form>
</body>
</html>
```

### Label ile İlişkilendirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Label İlişkilendirme</title>
    <style>
        form {
            max-width: 400px;
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
    <h2>Label İlişkilendirme</h2>
    
    <!-- Yöntem 1: for ve id kullanımı -->
    <form>
        <label for="isim1">İsim (for/id):</label>
        <input type="text" id="isim1" name="isim1">
    </form>
    
    <!-- Yöntem 2: İç içe kullanım -->
    <form>
        <label>
            İsim (iç içe):
            <input type="text" name="isim2">
        </label>
    </form>
</body>
</html>
```

### Form Grupları (fieldset, legend)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Form Grupları</title>
    <style>
        form {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }
        
        fieldset {
            border: 2px solid #3498db;
            border-radius: 5px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        legend {
            padding: 0 10px;
            font-weight: bold;
            color: #3498db;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
        }
        
        input {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 3px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h2>Kayıt Formu</h2>
    <form>
        <fieldset>
            <legend>Kişisel Bilgiler</legend>
            <label for="ad">Ad:</label>
            <input type="text" id="ad" name="ad" required>
            
            <label for="soyad">Soyad:</label>
            <input type="text" id="soyad" name="soyad" required>
            
            <label for="dogum">Doğum Tarihi:</label>
            <input type="date" id="dogum" name="dogum" required>
        </fieldset>
        
        <fieldset>
            <legend>İletişim Bilgileri</legend>
            <label for="email">E-posta:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="telefon">Telefon:</label>
            <input type="tel" id="telefon" name="telefon" required>
        </fieldset>
        
        <button type="submit">Kayıt Ol</button>
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
    <title>Kapsamlı Form Örneği</title>
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
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
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
            font-size: 1.1em;
            color: #2c3e50;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #2c3e50;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box;
            font-size: 1em;
        }
        
        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #3498db;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
        }
        
        button {
            background-color: #27ae60;
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 5px;
            font-size: 1em;
            cursor: pointer;
            width: 100%;
        }
        
        button:hover {
            background-color: #229954;
        }
        
        .required {
            color: #e74c3c;
        }
    </style>
</head>
<body>
    <h1>Üyelik Formu</h1>
    
    <form method="POST" action="/kayit">
        <fieldset>
            <legend>Hesap Bilgileri</legend>
            
            <label for="kullanici_adi">
                Kullanıcı Adı <span class="required">*</span>
            </label>
            <input type="text" id="kullanici_adi" name="kullanici_adi" required>
            
            <label for="sifre">
                Şifre <span class="required">*</span>
            </label>
            <input type="password" id="sifre" name="sifre" required>
            
            <label for="sifre_tekrar">
                Şifre Tekrar <span class="required">*</span>
            </label>
            <input type="password" id="sifre_tekrar" name="sifre_tekrar" required>
        </fieldset>
        
        <fieldset>
            <legend>Kişisel Bilgiler</legend>
            
            <label for="ad">
                Ad <span class="required">*</span>
            </label>
            <input type="text" id="ad" name="ad" required>
            
            <label for="soyad">
                Soyad <span class="required">*</span>
            </label>
            <input type="text" id="soyad" name="soyad" required>
            
            <label for="email">
                E-posta <span class="required">*</span>
            </label>
            <input type="email" id="email" name="email" required>
            
            <label for="telefon">Telefon</label>
            <input type="tel" id="telefon" name="telefon">
        </fieldset>
        
        <button type="submit">Kayıt Ol</button>
    </form>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **action**: Formun gönderileceği URL. Boş bırakılırsa aynı sayfaya gönderilir.

2. **method**: `GET` URL'de görünür, `POST` gizlidir. Hassas veriler için `POST` kullanın.

3. **name**: Form elemanının adı. Sunucuya gönderilirken kullanılır, zorunludur.

4. **id ve for**: `label` ile `input` ilişkilendirmesi için kullanılır.

5. **required**: Zorunlu alanlar için kullanılır.

6. **Erişilebilirlik**: Her `input` için `label` kullanın.

## 🎯 İyi Pratikler

- Her form elemanı için `label` kullanın
- `id` ve `for` ile ilişkilendirme yapın
- Zorunlu alanlar için `required` kullanın
- Hassas veriler için `POST` metodunu kullanın
- Form grupları için `fieldset` ve `legend` kullanın
- Erişilebilirlik için anlamsal HTML kullanın
- Form validasyonu ekleyin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


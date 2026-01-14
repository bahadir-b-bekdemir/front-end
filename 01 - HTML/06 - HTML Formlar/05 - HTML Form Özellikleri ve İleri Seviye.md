# 🚀 HTML FORM ÖZELLİKLERİ VE İLERİ SEVİYE

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) formlar için gelişmiş özellikler ve iyi pratikler bulunmaktadır.

## 📋 İleri Seviye Özellikler

### `autocomplete` Özelliği

Tarayıcının otomatik tamamlama özelliğini kontrol eder.

### `autofocus` Özelliği

Sayfa yüklendiğinde otomatik odaklanma.

### `disabled` Özelliği

Form elemanını devre dışı bırakır.

### `readonly` Özelliği

Form elemanını salt okunur yapar.

### `placeholder` Özelliği

Kullanıcıya rehberlik eden örnek metin.

### `form` Özelliği

Form elemanını dışarıdaki bir form ile ilişkilendirir.

## 💡 Kullanım Örnekleri

### Autocomplete ve Autofocus

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Autocomplete ve Autofocus</title>
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
    <h2>Autocomplete ve Autofocus</h2>
    <form autocomplete="on">
        <label for="isim">İsim:</label>
        <input type="text" id="isim" name="isim" autofocus>
        
        <label for="email">E-posta:</label>
        <input type="email" id="email" name="email" autocomplete="email">
        
        <label for="adres">Adres:</label>
        <input type="text" id="adres" name="adres" autocomplete="street-address">
        
        <label for="sehir">Şehir:</label>
        <input type="text" id="sehir" name="sehir" autocomplete="address-level2">
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Disabled ve Readonly

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Disabled ve Readonly</title>
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
        
        input:disabled {
            background-color: #f5f5f5;
            cursor: not-allowed;
        }
        
        input:read-only {
            background-color: #e8e8e8;
        }
    </style>
</head>
<body>
    <h2>Disabled ve Readonly</h2>
    <form>
        <label for="kullanici_id">Kullanıcı ID (Readonly):</label>
        <input type="text" id="kullanici_id" name="kullanici_id" value="12345" readonly>
        
        <label for="kullanici_adi">Kullanıcı Adı:</label>
        <input type="text" id="kullanici_adi" name="kullanici_adi">
        
        <label for="eski_sifre">Eski Şifre (Disabled):</label>
        <input type="password" id="eski_sifre" name="eski_sifre" value="********" disabled>
        
        <label for="yeni_sifre">Yeni Şifre:</label>
        <input type="password" id="yeni_sifre" name="yeni_sifre">
        
        <button type="submit">Güncelle</button>
    </form>
</body>
</html>
```

### Form İlişkilendirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Form İlişkilendirme</title>
    <style>
        body {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
        }
        
        form {
            margin-bottom: 30px;
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
    </style>
</head>
<body>
    <h2>Form İlişkilendirme</h2>
    
    <form id="ana-form">
        <label for="isim">İsim:</label>
        <input type="text" id="isim" name="isim">
        
        <label for="email">E-posta:</label>
        <input type="email" id="email" name="email">
    </form>
    
    <!-- Form dışında ama form ile ilişkili -->
    <label for="telefon">Telefon:</label>
    <input type="tel" id="telefon" name="telefon" form="ana-form">
    
    <button type="submit" form="ana-form">Gönder</button>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Form Özellikleri</title>
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
        
        input:focus {
            outline: none;
            border-color: #3498db;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
        }
        
        input:disabled {
            background-color: #f5f5f5;
            cursor: not-allowed;
        }
        
        input:read-only {
            background-color: #e8e8e8;
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
    </style>
</head>
<body>
    <h1>Gelişmiş Form Özellikleri</h1>
    
    <form method="POST" action="/form" autocomplete="on">
        <fieldset>
            <legend>Otomatik Tamamlama</legend>
            
            <label for="isim">İsim:</label>
            <input 
                type="text" 
                id="isim" 
                name="isim" 
                autocomplete="name"
                autofocus>
            
            <label for="email">E-posta:</label>
            <input 
                type="email" 
                id="email" 
                name="email" 
                autocomplete="email"
                placeholder="ornek@email.com">
        </fieldset>
        
        <fieldset>
            <legend>Disabled ve Readonly</legend>
            
            <label for="kullanici_id">Kullanıcı ID:</label>
            <input 
                type="text" 
                id="kullanici_id" 
                name="kullanici_id" 
                value="USR-12345"
                readonly>
            <p class="help-text">Bu alan değiştirilemez (readonly).</p>
            
            <label for="eski_alan">Eski Alan:</label>
            <input 
                type="text" 
                id="eski_alan" 
                name="eski_alan" 
                value="Devre Dışı"
                disabled>
            <p class="help-text">Bu alan devre dışı (disabled).</p>
        </fieldset>
        
        <fieldset>
            <legend>Validasyon</legend>
            
            <label for="telefon">Telefon:</label>
            <input 
                type="tel" 
                id="telefon" 
                name="telefon" 
                pattern="[0-9]{10,11}"
                placeholder="05551234567"
                title="10 veya 11 haneli telefon numarası">
            
            <label for="yas">Yaş:</label>
            <input 
                type="number" 
                id="yas" 
                name="yas" 
                min="18"
                max="100"
                placeholder="18-100">
        </fieldset>
        
        <button type="submit">Gönder</button>
        <button type="reset" style="background-color: #e74c3c; margin-top: 10px;">Sıfırla</button>
    </form>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **autocomplete**: Tarayıcı otomatik tamamlama için `autocomplete` özelliğini kullanır.

2. **autofocus**: Sayfa yüklendiğinde otomatik odaklanma sağlar (erişilebilirlik için dikkatli kullanın).

3. **disabled vs readonly**: `disabled` form gönderiminde dahil edilmez, `readonly` dahil edilir.

4. **form Özelliği**: Form elemanını dışarıdaki bir form ile ilişkilendirmek için kullanılır.

5. **placeholder**: Kullanıcıya rehberlik eder, `label` yerine kullanılmamalıdır.

## 🎯 İyi Pratikler

- `autocomplete` ile kullanıcı deneyimini iyileştirin
- `autofocus` kullanırken erişilebilirliği düşünün
- `placeholder` ile rehberlik sağlayın
- `disabled` ve `readonly` arasındaki farkı bilin
- Form ilişkilendirme için `form` özelliğini kullanın
- Erişilebilirlik için her zaman `label` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


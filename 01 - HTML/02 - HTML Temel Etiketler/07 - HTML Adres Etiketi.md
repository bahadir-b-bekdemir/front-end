# 📧 HTML ADRES ETİKETİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) iletişim bilgilerini, adres bilgilerini ve yazar bilgilerini belirtmek için `<address>` etiketi kullanılır.

## 📋 Adres Etiketi

### `<address>...</address>`

İletişim bilgilerini, adres bilgilerini veya belge yazarının bilgilerini belirtmek için kullanılır. Genellikle italik görüntülenir.

**Temel kullanım:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Adres Örneği</title>
</head>
<body>
    <address>
        ABC Şirketi<br>
        İstanbul Caddesi, No: 123<br>
        Çankaya, Ankara<br>
        Tel: 0312 123 45 67<br>
        Email: info@abc.com
    </address>
</body>
</html>
```

## 💡 Kullanım Örnekleri

### İletişim Bilgileri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>İletişim Bilgileri</title>
    <style>
        address {
            font-style: normal;
            line-height: 1.8;
            padding: 20px;
            background-color: #f8f9fa;
            border-left: 4px solid #3498db;
        }
    </style>
</head>
<body>
    <h1>İletişim Bilgileri</h1>
    
    <address>
        <strong>ABC Teknoloji A.Ş.</strong><br>
        İstanbul Caddesi, No: 123<br>
        Çankaya, Ankara<br>
        Posta Kodu: 06100<br>
        <br>
        Telefon: 0312 123 45 67<br>
        Faks: 0312 123 45 68<br>
        Email: <a href="mailto:info@abc.com">info@abc.com</a><br>
        Web: <a href="https://www.abc.com">www.abc.com</a>
    </address>
</body>
</html>
```

### Sayfa Alt Bilgisi (Footer)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sayfa Alt Bilgisi</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        main {
            min-height: 80vh;
            padding: 20px;
        }
        
        footer {
            background-color: #2c3e50;
            color: #ecf0f1;
            padding: 30px;
            text-align: center;
        }
        
        address {
            font-style: normal;
            line-height: 2;
        }
        
        address a {
            color: #3498db;
            text-decoration: none;
        }
        
        address a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <main>
        <h1>Ana İçerik</h1>
        <p>Sayfa içeriği burada yer alır.</p>
    </main>
    
    <footer>
        <address>
            <strong>Web Sitesi</strong><br>
            İstanbul Caddesi, No: 123<br>
            Çankaya, Ankara<br>
            <br>
            Telefon: 0312 123 45 67<br>
            Email: <a href="mailto:info@example.com">info@example.com</a><br>
            <br>
            &copy; 2024 Tüm hakları saklıdır.
        </address>
    </footer>
</body>
</html>
```

### Makale Yazar Bilgisi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Makale Yazar Bilgisi</title>
    <style>
        article {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            font-family: Arial, sans-serif;
            line-height: 1.6;
        }
        
        address {
            font-style: normal;
            margin-top: 30px;
            padding: 20px;
            background-color: #f8f9fa;
            border-top: 2px solid #3498db;
        }
        
        .author-name {
            font-weight: bold;
            font-size: 1.1em;
            color: #2c3e50;
        }
    </style>
</head>
<body>
    <article>
        <h1>Web Geliştirme Rehberi</h1>
        
        <p>Bu makale HTML, CSS ve JavaScript hakkında temel bilgiler içermektedir.</p>
        
        <h2>HTML Nedir?</h2>
        <p>HTML, web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir.</p>
        
        <h2>CSS Nedir?</h2>
        <p>CSS, web sayfalarının görsel tasarımını yapmak için kullanılan bir stil dilidir.</p>
        
        <h2>JavaScript Nedir?</h2>
        <p>JavaScript, web sayfalarına etkileşim eklemek için kullanılan bir programlama dilidir.</p>
        
        <address>
            <span class="author-name">Yazar: Ahmet Yılmaz</span><br>
            Email: <a href="mailto:ahmet@example.com">ahmet@example.com</a><br>
            Web: <a href="https://www.ahmetyilmaz.com">www.ahmetyilmaz.com</a><br>
            <br>
            Yayın Tarihi: 15 Ocak 2024
        </address>
    </article>
</body>
</html>
```

### Çoklu Adres Bilgileri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu Adres Bilgileri</title>
    <style>
        .address-container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            padding: 20px;
        }
        
        address {
            font-style: normal;
            flex: 1;
            min-width: 250px;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
            border-left: 4px solid #3498db;
        }
        
        address h3 {
            margin-top: 0;
            color: #2c3e50;
        }
        
        address a {
            color: #3498db;
            text-decoration: none;
        }
        
        address a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>İletişim Bilgileri</h1>
    
    <div class="address-container">
        <address>
            <h3>Merkez Ofis</h3>
            <strong>ABC Şirketi</strong><br>
            İstanbul Caddesi, No: 123<br>
            Çankaya, Ankara<br>
            Posta Kodu: 06100<br>
            <br>
            Telefon: 0312 123 45 67<br>
            Email: <a href="mailto:merkez@abc.com">merkez@abc.com</a>
        </address>
        
        <address>
            <h3>İstanbul Şubesi</h3>
            <strong>ABC Şirketi</strong><br>
            Taksim Meydanı, No: 456<br>
            Beyoğlu, İstanbul<br>
            Posta Kodu: 34430<br>
            <br>
            Telefon: 0212 234 56 78<br>
            Email: <a href="mailto:istanbul@abc.com">istanbul@abc.com</a>
        </address>
        
        <address>
            <h3>İzmir Şubesi</h3>
            <strong>ABC Şirketi</strong><br>
            Konak Meydanı, No: 789<br>
            Konak, İzmir<br>
            Posta Kodu: 35250<br>
            <br>
            Telefon: 0232 345 67 89<br>
            Email: <a href="mailto:izmir@abc.com">izmir@abc.com</a>
        </address>
    </div>
</body>
</html>
```

### E-posta ve Telefon Linkleri ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>E-posta ve Telefon Linkleri</title>
    <style>
        address {
            font-style: normal;
            padding: 20px;
            background-color: #ecf0f1;
            border-radius: 5px;
            line-height: 2;
        }
        
        address a {
            color: #3498db;
            text-decoration: none;
            font-weight: bold;
        }
        
        address a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>İletişim</h1>
    
    <address>
        <strong>ABC Teknoloji A.Ş.</strong><br>
        İstanbul Caddesi, No: 123<br>
        Çankaya, Ankara<br>
        <br>
        <strong>Telefon:</strong><br>
        <a href="tel:+903121234567">+90 312 123 45 67</a><br>
        <a href="tel:+903121234568">+90 312 123 45 68</a><br>
        <br>
        <strong>E-posta:</strong><br>
        <a href="mailto:info@abc.com">info@abc.com</a><br>
        <a href="mailto:destek@abc.com">destek@abc.com</a><br>
        <a href="mailto:satis@abc.com">satis@abc.com</a><br>
        <br>
        <strong>Web:</strong><br>
        <a href="https://www.abc.com">www.abc.com</a>
    </address>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: `<address>` etiketi anlamsal HTML'in bir parçasıdır ve iletişim bilgilerini belirtmek için kullanılır.

2. **İtalik Görünüm**: Varsayılan olarak italik görüntülenir, ancak **CSS** ile `font-style: normal;` yapılarak değiştirilebilir.

3. **Kullanım Yeri**: Genellikle sayfa alt bilgisi (footer) veya makale yazar bilgisi için kullanılır.

4. **İçerik**: İçinde başka HTML etiketleri (örn: `<a>`, `<br>`, `<strong>`) kullanılabilir.

5. **E-posta ve Telefon**: E-posta için `mailto:` ve telefon için `tel:` protokolleri kullanılabilir.

## 🎯 İyi Pratikler

- İletişim bilgileri için `<address>` etiketini kullanın
- E-posta adresleri için `mailto:` linklerini kullanın
- Telefon numaraları için `tel:` linklerini kullanın
- Sayfa alt bilgisi (footer) içinde kullanın
- Makale yazar bilgileri için kullanın
- Stil için **CSS** kullanın, varsayılan italik görünümü değiştirebilirsiniz
- Anlamsal HTML kullanarak **SEO**'yu iyileştirin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


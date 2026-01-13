# 🔗 HTML BAĞLANTILAR (a)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) bağlantılar, sayfalar arasında veya sayfa içinde gezinmeyi sağlar. Bağlantılar `<a>` (anchor) etiketi ile oluşturulur.

## 📋 Bağlantı Yapısı

### `<a>...</a>`

Bağlantı etiketi. `href` özelliği ile hedef URL belirtilir.

**Temel kullanım:**
```html
<a href="https://www.example.com">Bağlantı Metni</a>
```

## 📋 Bağlantı Özellikleri

### `href` Özelliği

Bağlantının hedef URL'sini belirler. Zorunludur.

### `target` Özelliği

Bağlantının nasıl açılacağını belirler.

| Değer | Açıklama |
| :---- | :------- |
| `_self` | Aynı sekmede açar (varsayılan) |
| `_blank` | Yeni sekmede açar |
| `_parent` | Üst çerçevede açar |
| `_top` | Tüm çerçevelerde açar |

### `rel` Özelliği

Bağlantının ilişkisini belirtir. **SEO** için önemlidir.

### `download` Özelliği

Dosyayı indirmek için kullanılır.

### `title` Özelliği

Fare ile üzerine gelindiğinde görüntülenecek açıklama.

## 💡 Kullanım Örnekleri

### Temel Bağlantılar

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Bağlantılar</title>
</head>
<body>
    <h2>Dış Bağlantılar</h2>
    <p><a href="https://www.google.com">Google'a Git</a></p>
    <p><a href="https://www.github.com">GitHub'a Git</a></p>
    
    <h2>İç Bağlantılar</h2>
    <p><a href="hakkimizda.html">Hakkımızda</a></p>
    <p><a href="iletisim.html">İletişim</a></p>
</body>
</html>
```

### Yeni Sekmede Açma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Yeni Sekmede Açma</title>
</head>
<body>
    <h2>Dış Bağlantılar (Yeni Sekmede)</h2>
    <p>
        <a href="https://www.google.com" target="_blank">Google</a> - 
        Yeni sekmede açılır
    </p>
    <p>
        <a href="https://www.github.com" target="_blank" rel="noopener noreferrer">
            GitHub
        </a> - Güvenli yeni sekme açma
    </p>
</body>
</html>
```

### Sayfa İçi Bağlantılar (Anchor)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sayfa İçi Bağlantılar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
        }
        
        section {
            min-height: 500px;
            padding: 20px;
            margin: 20px 0;
            border: 1px solid #ddd;
        }
        
        .nav {
            position: fixed;
            top: 0;
            background-color: #2c3e50;
            padding: 15px;
            width: 100%;
        }
        
        .nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            padding: 10px;
        }
        
        .nav a:hover {
            background-color: #3498db;
        }
    </style>
</head>
<body>
    <nav class="nav">
        <a href="#bolum1">Bölüm 1</a>
        <a href="#bolum2">Bölüm 2</a>
        <a href="#bolum3">Bölüm 3</a>
        <a href="#bolum4">Bölüm 4</a>
    </nav>
    
    <div style="margin-top: 80px;">
        <section id="bolum1">
            <h2>Bölüm 1</h2>
            <p>Bu bölümün içeriği burada yer alır.</p>
            <p>Sayfa içi bağlantılar ile bu bölüme geçiş yapılabilir.</p>
        </section>
        
        <section id="bolum2">
            <h2>Bölüm 2</h2>
            <p>Bu bölümün içeriği burada yer alır.</p>
            <a href="#bolum1">Bölüm 1'e dön</a>
        </section>
        
        <section id="bolum3">
            <h2>Bölüm 3</h2>
            <p>Bu bölümün içeriği burada yer alır.</p>
            <a href="#bolum1">Bölüm 1'e dön</a>
        </section>
        
        <section id="bolum4">
            <h2>Bölüm 4</h2>
            <p>Bu bölümün içeriği burada yer alır.</p>
            <a href="#bolum1">Bölüm 1'e dön</a>
        </section>
    </div>
</body>
</html>
```

### E-posta Bağlantıları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>E-posta Bağlantıları</title>
</head>
<body>
    <h2>İletişim</h2>
    <p>
        Bize ulaşmak için: 
        <a href="mailto:info@example.com">info@example.com</a>
    </p>
    
    <p>
        <a href="mailto:destek@example.com?subject=Destek%20Talebi&body=Merhaba,">
            Destek için e-posta gönder
        </a>
    </p>
    
    <p>
        <a href="mailto:satis@example.com?subject=Sipariş&body=Sipariş%20detayları:">
            Satış için e-posta gönder
        </a>
    </p>
</body>
</html>
```

### Telefon Bağlantıları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Telefon Bağlantıları</title>
</head>
<body>
    <h2>İletişim Bilgileri</h2>
    <p>
        Telefon: <a href="tel:+903121234567">+90 312 123 45 67</a>
    </p>
    
    <p>
        Mobil: <a href="tel:+905551234567">+90 555 123 45 67</a>
    </p>
    
    <p>
        Faks: <a href="tel:+903121234568">+90 312 123 45 68</a>
    </p>
</body>
</html>
```

### Dosya İndirme Bağlantıları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Dosya İndirme</title>
    <style>
        .download-link {
            display: inline-block;
            padding: 10px 20px;
            background-color: #3498db;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            margin: 10px 5px;
        }
        
        .download-link:hover {
            background-color: #2980b9;
        }
    </style>
</head>
<body>
    <h2>İndirilebilir Dosyalar</h2>
    
    <p>
        <a href="dosya.pdf" download class="download-link">
            PDF Dosyasını İndir
        </a>
    </p>
    
    <p>
        <a href="dokuman.docx" download="yeni-isim.docx" class="download-link">
            Word Belgesini İndir
        </a>
    </p>
    
    <p>
        <a href="resim.jpg" download class="download-link">
            Resmi İndir
        </a>
    </p>
</body>
</html>
```

### Bağlantı Stilleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Bağlantı Stilleri</title>
    <style>
        /* Varsayılan bağlantı stilleri */
        a {
            color: #3498db;
            text-decoration: none;
        }
        
        /* Ziyaret edilmiş bağlantılar */
        a:visited {
            color: #9b59b6;
        }
        
        /* Fare ile üzerine gelindiğinde */
        a:hover {
            color: #2980b9;
            text-decoration: underline;
        }
        
        /* Aktif (tıklanırken) */
        a:active {
            color: #e74c3c;
        }
        
        /* Özel buton stili */
        .button-link {
            display: inline-block;
            padding: 12px 24px;
            background-color: #27ae60;
            color: white;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        
        .button-link:hover {
            background-color: #229954;
            text-decoration: none;
        }
        
        /* İkonlu bağlantı */
        .icon-link::before {
            content: "🔗 ";
        }
    </style>
</head>
<body>
    <h2>Farklı Bağlantı Stilleri</h2>
    
    <p>
        <a href="#normal">Normal Bağlantı</a>
    </p>
    
    <p>
        <a href="#button" class="button-link">Buton Stili Bağlantı</a>
    </p>
    
    <p>
        <a href="#icon" class="icon-link">İkonlu Bağlantı</a>
    </p>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Bağlantı Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
        }
        
        nav {
            background-color: #2c3e50;
            padding: 15px;
            margin-bottom: 30px;
            border-radius: 5px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            padding: 10px 15px;
            display: inline-block;
        }
        
        nav a:hover {
            background-color: #3498db;
            border-radius: 3px;
        }
        
        .section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .external-link {
            color: #e74c3c;
        }
        
        .external-link::after {
            content: " ↗";
        }
        
        .email-link {
            color: #27ae60;
        }
        
        .email-link::before {
            content: "✉ ";
        }
        
        .phone-link {
            color: #3498db;
        }
        
        .phone-link::before {
            content: "📞 ";
        }
    </style>
</head>
<body>
    <h1>Bağlantı Örnekleri</h1>
    
    <nav>
        <a href="#anasayfa">Ana Sayfa</a>
        <a href="#hakkimizda">Hakkımızda</a>
        <a href="#hizmetler">Hizmetler</a>
        <a href="#iletisim">İletişim</a>
    </nav>
    
    <div class="section" id="anasayfa">
        <h2>Ana Sayfa</h2>
        <p>Hoş geldiniz! Web sitemize bağlantılar:</p>
        <ul>
            <li><a href="https://www.w3.org" target="_blank" rel="noopener" class="external-link">W3C</a></li>
            <li><a href="https://developer.mozilla.org" target="_blank" rel="noopener" class="external-link">MDN</a></li>
            <li><a href="https://www.github.com" target="_blank" rel="noopener" class="external-link">GitHub</a></li>
        </ul>
    </div>
    
    <div class="section" id="hakkimizda">
        <h2>Hakkımızda</h2>
        <p>Sayfa içi bağlantılar:</p>
        <ul>
            <li><a href="#anasayfa">Ana Sayfaya Dön</a></li>
            <li><a href="#hizmetler">Hizmetlerimiz</a></li>
            <li><a href="#iletisim">İletişim</a></li>
        </ul>
    </div>
    
    <div class="section" id="hizmetler">
        <h2>Hizmetlerimiz</h2>
        <p>Hizmetlerimiz hakkında bilgi almak için:</p>
        <ul>
            <li><a href="#anasayfa">Ana Sayfa</a></li>
            <li><a href="#hakkimizda">Hakkımızda</a></li>
        </ul>
    </div>
    
    <div class="section" id="iletisim">
        <h2>İletişim</h2>
        <p>Bize ulaşın:</p>
        <ul>
            <li>
                E-posta: 
                <a href="mailto:info@example.com" class="email-link">info@example.com</a>
            </li>
            <li>
                Telefon: 
                <a href="tel:+903121234567" class="phone-link">+90 312 123 45 67</a>
            </li>
            <li>
                <a href="mailto:destek@example.com?subject=Destek&body=Merhaba," class="email-link">
                    Destek için e-posta gönder
                </a>
            </li>
        </ul>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **href Özelliği**: Bağlantı için `href` özelliği zorunludur (sayfa içi anchor için `#` kullanılabilir).

2. **Güvenlik**: Dış bağlantılar için `rel="noopener noreferrer"` kullanılmalıdır.

3. **Erişilebilirlik**: Bağlantı metinleri açıklayıcı olmalıdır. "Tıklayın" gibi genel ifadelerden kaçınılmalıdır.

4. **SEO**: `rel` özelliği ile bağlantı ilişkileri belirtilmelidir.

5. **title Özelliği**: Ek açıklama için `title` özelliği kullanılabilir.

## 🎯 İyi Pratikler

- Açıklayıcı bağlantı metinleri kullanın
- Dış bağlantılar için `target="_blank"` ve `rel="noopener noreferrer"` kullanın
- E-posta ve telefon bağlantıları için `mailto:` ve `tel:` protokollerini kullanın
- Bağlantı stillerini **CSS** ile özelleştirin
- Sayfa içi bağlantılar için anchor (`#`) kullanın
- Dosya indirme için `download` özelliğini kullanın
- Anlamsal HTML kullanarak erişilebilirliği artırın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


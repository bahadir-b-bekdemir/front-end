# ♿ HTML ERİŞİLEBİLİRLİK (ACCESSIBILITY)

**Erişilebilirlik** (Accessibility), web sitelerinin tüm kullanıcılar tarafından erişilebilir olmasını sağlar. **HTML** yapısı erişilebilirlik için kritik öneme sahiptir.

## 📋 Erişilebilirlik Öğeleri

### ARIA Özellikleri

- `aria-label` - Açıklayıcı etiket
- `aria-labelledby` - Etiket ilişkilendirme
- `aria-describedby` - Açıklama ilişkilendirme
- `aria-hidden` - Gizleme
- `role` - Rol tanımlama

### Semantic HTML

- Anlamsal etiketler
- Doğru başlık hiyerarşisi
- Form etiketleri

### Klavye Erişilebilirliği

- Tab sırası
- Klavye navigasyonu
- Focus yönetimi

## 💡 Kullanım Örnekleri

### ARIA Özellikleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>ARIA Özellikleri</title>
</head>
<body>
    <!-- aria-label -->
    <button aria-label="Kapat">X</button>
    
    <!-- aria-labelledby -->
    <div>
        <h2 id="form-title">Kayıt Formu</h2>
        <form aria-labelledby="form-title">
            <input type="text" name="isim">
        </form>
    </div>
    
    <!-- aria-describedby -->
    <label for="email">E-posta:</label>
    <input type="email" id="email" aria-describedby="email-help">
    <span id="email-help">E-posta adresinizi girin</span>
    
    <!-- aria-hidden -->
    <span aria-hidden="true">*</span>
    <span class="sr-only">Zorunlu alan</span>
    
    <!-- role -->
    <div role="button" tabindex="0" onclick="handleClick()">
        Tıklanabilir div
    </div>
</body>
</html>
```

### Semantic HTML Yapısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Semantic HTML</title>
</head>
<body>
    <!-- Semantic yapı -->
    <header>
        <h1>Web Sitesi Başlığı</h1>
        <nav aria-label="Ana navigasyon">
            <ul>
                <li><a href="#anasayfa">Ana Sayfa</a></li>
                <li><a href="#hakkimizda">Hakkımızda</a></li>
                <li><a href="#iletisim">İletişim</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <header>
                <h2>Makale Başlığı</h2>
                <time datetime="2024-01-15">15 Ocak 2024</time>
            </header>
            
            <section>
                <h3>Bölüm 1</h3>
                <p>İçerik...</p>
            </section>
        </article>
        
        <aside aria-label="Yan içerik">
            <h2>İlgili Makaleler</h2>
            <ul>
                <li><a href="#">Makale 1</a></li>
                <li><a href="#">Makale 2</a></li>
            </ul>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 Tüm hakları saklıdır.</p>
    </footer>
</body>
</html>
```

### Form Erişilebilirliği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Form Erişilebilirliği</title>
    <style>
        .error {
            color: red;
        }
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }
    </style>
</head>
<body>
    <h1>Kayıt Formu</h1>
    
    <form>
        <!-- Label ile ilişkilendirme -->
        <label for="isim">İsim <span aria-label="zorunlu alan">*</span></label>
        <input 
            type="text" 
            id="isim" 
            name="isim" 
            required
            aria-required="true"
            aria-describedby="isim-error">
        <span id="isim-error" class="error" role="alert" aria-live="polite"></span>
        
        <!-- Fieldset ve legend -->
        <fieldset>
            <legend>Cinsiyet</legend>
            <input type="radio" id="erkek" name="cinsiyet" value="erkek">
            <label for="erkek">Erkek</label>
            
            <input type="radio" id="kadin" name="cinsiyet" value="kadin">
            <label for="kadin">Kadın</label>
        </fieldset>
        
        <!-- Checkbox grup -->
        <fieldset>
            <legend>Hobiler</legend>
            <div>
                <input type="checkbox" id="okuma" name="hobiler" value="okuma">
                <label for="okuma">Okuma</label>
            </div>
            <div>
                <input type="checkbox" id="spor" name="hobiler" value="spor">
                <label for="spor">Spor</label>
            </div>
        </fieldset>
        
        <!-- Hata mesajı -->
        <div role="alert" aria-live="assertive" id="form-error"></div>
        
        <button type="submit">Gönder</button>
    </form>
</body>
</html>
```

### Resim Erişilebilirliği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Resim Erişilebilirliği</title>
</head>
<body>
    <h1>Resim Erişilebilirliği</h1>
    
    <!-- İyi: Açıklayıcı alt text -->
    <img 
        src="dag.jpg" 
        alt="Yüksek dağlar ve bulutların görüntüsü, güneşli bir günde çekilmiş manzara fotoğrafı"
        width="800"
        height="600">
    
    <!-- Dekoratif resim -->
    <img 
        src="dekoratif-cizgi.jpg" 
        alt=""
        role="presentation"
        aria-hidden="true">
    
    <!-- Bağlantılı resim -->
    <a href="buyuk-resim.jpg">
        <img 
            src="kucuk-resim.jpg" 
            alt="Büyük resmi görmek için tıklayın - Dağ manzarası">
    </a>
    
    <!-- Figure ile açıklama -->
    <figure>
        <img src="grafik.jpg" alt="2024 yılı satış grafiği">
        <figcaption>2024 yılı aylık satış grafiği</figcaption>
    </figure>
</body>
</html>
```

### Tablo Erişilebilirliği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Tablo Erişilebilirliği</title>
</head>
<body>
    <h1>Tablo Erişilebilirliği</h1>
    
    <table>
        <caption>Öğrenci Not Listesi</caption>
        <thead>
            <tr>
                <th scope="col">Öğrenci No</th>
                <th scope="col">Ad Soyad</th>
                <th scope="col">Matematik</th>
                <th scope="col">Türkçe</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th scope="row">101</th>
                <td>Ahmet Yılmaz</td>
                <td>85</td>
                <td>90</td>
            </tr>
            <tr>
                <th scope="row">102</th>
                <td>Ayşe Demir</td>
                <td>92</td>
                <td>88</td>
            </tr>
        </tbody>
    </table>
    
    <!-- Karmaşık tablo için headers -->
    <table>
        <caption>Haftalık Ders Programı</caption>
        <thead>
            <tr>
                <th id="time" scope="col">Saat</th>
                <th id="mon" scope="col">Pazartesi</th>
                <th id="tue" scope="col">Salı</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th id="hour1" scope="row">09:00</th>
                <td headers="mon hour1">Matematik</td>
                <td headers="tue hour1">Türkçe</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### Klavye Erişilebilirliği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Klavye Erişilebilirliği</title>
    <style>
        button:focus,
        a:focus,
        input:focus {
            outline: 3px solid #3498db;
            outline-offset: 2px;
        }
        
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: #2c3e50;
            color: white;
            padding: 8px;
            text-decoration: none;
        }
        
        .skip-link:focus {
            top: 0;
        }
    </style>
</head>
<body>
    <!-- Skip link -->
    <a href="#main-content" class="skip-link">Ana içeriğe geç</a>
    
    <header>
        <nav>
            <ul>
                <li><a href="#anasayfa">Ana Sayfa</a></li>
                <li><a href="#hakkimizda">Hakkımızda</a></li>
            </ul>
        </nav>
    </header>
    
    <main id="main-content">
        <h1>Ana İçerik</h1>
        
        <!-- Tab sırası -->
        <button tabindex="1">Buton 1</button>
        <button tabindex="2">Buton 2</button>
        <button tabindex="-1">Atlanan buton</button>
        
        <!-- Klavye ile çalışan öğe -->
        <div 
            role="button" 
            tabindex="0"
            onkeypress="if(event.key==='Enter'||event.key===' '){handleClick()}"
            onclick="handleClick()">
            Tıklanabilir div (Klavye ile de çalışır)
        </div>
    </main>
    
    <script>
        function handleClick() {
            alert('Tıklandı!');
        }
    </script>
</body>
</html>
```

### Kapsamlı Erişilebilirlik Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kapsamlı Erişilebilirlik</title>
    <style>
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }
        
        button:focus,
        a:focus {
            outline: 3px solid #3498db;
            outline-offset: 2px;
        }
    </style>
</head>
<body>
    <!-- Skip link -->
    <a href="#main-content" class="sr-only">Ana içeriğe geç</a>
    
    <header role="banner">
        <h1>Web Sitesi</h1>
        <nav aria-label="Ana navigasyon" role="navigation">
            <ul>
                <li><a href="#anasayfa">Ana Sayfa</a></li>
                <li><a href="#hakkimizda">Hakkımızda</a></li>
                <li><a href="#iletisim">İletişim</a></li>
            </ul>
        </nav>
    </header>
    
    <main id="main-content" role="main">
        <article>
            <header>
                <h2>Makale Başlığı</h2>
                <time datetime="2024-01-15">15 Ocak 2024</time>
            </header>
            
            <section>
                <h3>Bölüm 1</h3>
                <p>İçerik...</p>
                
                <figure>
                    <img 
                        src="resim.jpg" 
                        alt="Açıklayıcı resim açıklaması"
                        width="800"
                        height="600">
                    <figcaption>Resim açıklaması</figcaption>
                </figure>
            </section>
        </article>
        
        <aside aria-label="Yan içerik" role="complementary">
            <h2>İlgili Makaleler</h2>
            <ul>
                <li><a href="#">Makale 1</a></li>
                <li><a href="#">Makale 2</a></li>
            </ul>
        </aside>
    </main>
    
    <footer role="contentinfo">
        <p>&copy; 2024 Tüm hakları saklıdır.</p>
    </footer>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **ARIA**: Semantic HTML yeterli değilse ARIA kullanın.

2. **Alt Text**: Tüm resimler için açıklayıcı alt text.

3. **Label**: Tüm form elemanları için label.

4. **Klavye**: Tüm işlevler klavye ile erişilebilir olmalı.

5. **Focus**: Focus görünür olmalı.

6. **Semantic HTML**: Önce semantic HTML, sonra ARIA.

## 🎯 İyi Pratikler

- Semantic HTML kullanın
- ARIA özelliklerini doğru kullanın
- Tüm resimler için alt text
- Tüm form elemanları için label
- Klavye erişilebilirliği sağlayın
- Focus yönetimi yapın
- Ekran okuyucularla test edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


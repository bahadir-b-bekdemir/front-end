# 📖 HTML TANIM LİSTELERİ (dl, dt, dd)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tanım listeleri, terimler ve açıklamalarını göstermek için kullanılır. Tanım listeleri `<dl>` (description list) etiketi ile oluşturulur, terimler `<dt>` (description term) ve açıklamalar `<dd>` (description definition) etiketleri ile tanımlanır.

## 📋 Tanım Liste Yapısı

### `<dl>...</dl>`

Tanım liste kapsayıcısı. İçinde `<dt>` ve `<dd>` etiketleri bulunur.

### `<dt>...</dt>`

Tanım terimi. Açıklanacak terim veya başlık.

### `<dd>...</dd>`

Tanım açıklaması. Terimin açıklaması veya tanımı.

**Temel kullanım:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Tanım Liste Örneği</title>
</head>
<body>
    <dl>
        <dt>HTML</dt>
        <dd>Hyper Text Markup Language - Web sayfaları oluşturmak için kullanılan işaretleme dili</dd>
        
        <dt>CSS</dt>
        <dd>Cascading Style Sheets - Web sayfalarının stilini belirlemek için kullanılan dil</dd>
        
        <dt>JavaScript</dt>
        <dd>Web sayfalarına etkileşim eklemek için kullanılan programlama dili</dd>
    </dl>
</body>
</html>
```

## 💡 Kullanım Örnekleri

### Temel Tanım Listesi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Tanım Listesi</title>
    <style>
        dl {
            margin: 20px 0;
        }
        
        dt {
            font-weight: bold;
            margin-top: 15px;
            color: #2c3e50;
        }
        
        dd {
            margin-left: 20px;
            margin-bottom: 10px;
            color: #555;
        }
    </style>
</head>
<body>
    <h2>Web Teknolojileri Sözlüğü</h2>
    <dl>
        <dt>HTML</dt>
        <dd>Hyper Text Markup Language - Web sayfalarının yapısını oluşturmak için kullanılan işaretleme dili</dd>
        
        <dt>CSS</dt>
        <dd>Cascading Style Sheets - Web sayfalarının görsel tasarımını yapmak için kullanılan stil dili</dd>
        
        <dt>JavaScript</dt>
        <dd>Web sayfalarına etkileşim ve dinamik özellikler eklemek için kullanılan programlama dili</dd>
        
        <dt>API</dt>
        <dd>Application Programming Interface - Uygulamalar arası iletişimi sağlayan arayüz</dd>
    </dl>
</body>
</html>
```

### Çoklu Açıklamalar

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu Açıklamalar</title>
    <style>
        dt {
            font-weight: bold;
            margin-top: 15px;
            color: #e74c3c;
        }
        
        dd {
            margin-left: 20px;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <h2>Programlama Dilleri</h2>
    <dl>
        <dt>Python</dt>
        <dd>Yüksek seviyeli, genel amaçlı bir programlama dilidir.</dd>
        <dd>Öğrenmesi kolay ve okunabilir sözdizimine sahiptir.</dd>
        <dd>Web geliştirme, veri bilimi ve yapay zeka alanlarında yaygın olarak kullanılır.</dd>
        
        <dt>JavaScript</dt>
        <dd>Web tarayıcılarında çalışan bir programlama dilidir.</dd>
        <dd>Node.js ile sunucu tarafında da kullanılabilir.</dd>
        <dd>Modern web uygulamalarının vazgeçilmez bir parçasıdır.</dd>
    </dl>
</body>
</html>
```

### Sözlük Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sözlük Örneği</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        dl {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        dt {
            font-weight: bold;
            font-size: 1.1em;
            margin-top: 20px;
            color: #2c3e50;
            border-bottom: 2px solid #3498db;
            padding-bottom: 5px;
        }
        
        dt:first-child {
            margin-top: 0;
        }
        
        dd {
            margin-left: 20px;
            margin-top: 10px;
            margin-bottom: 15px;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>Bilgisayar Terimleri Sözlüğü</h1>
    
    <dl>
        <dt>CPU</dt>
        <dd>Central Processing Unit - Merkezi işlem birimi. Bilgisayarın beyni olarak görev yapar.</dd>
        
        <dt>RAM</dt>
        <dd>Random Access Memory - Rastgele erişimli bellek. Geçici veri depolama birimi.</dd>
        
        <dt>SSD</dt>
        <dd>Solid State Drive - Katı hal sürücü. Geleneksel hard disklerden daha hızlıdır.</dd>
        
        <dt>GPU</dt>
        <dd>Graphics Processing Unit - Grafik işlem birimi. Görüntü işleme ve oyunlar için kullanılır.</dd>
        
        <dt>HTTP</dt>
        <dd>Hypertext Transfer Protocol - Web'de veri iletişimi için kullanılan protokol.</dd>
        
        <dt>HTTPS</dt>
        <dd>Hypertext Transfer Protocol Secure - Güvenli web iletişimi için şifrelenmiş protokol.</dd>
        
        <dt>URL</dt>
        <dd>Uniform Resource Locator - Web adreslerini belirtmek için kullanılan format.</dd>
        
        <dt>DNS</dt>
        <dd>Domain Name System - Alan adlarını IP adreslerine çeviren sistem.</dd>
    </dl>
</body>
</html>
```

### FAQ (Sık Sorulan Sorular) Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>FAQ Örneği</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        h1 {
            color: #2c3e50;
            text-align: center;
        }
        
        dl {
            margin: 30px 0;
        }
        
        dt {
            font-weight: bold;
            font-size: 1.1em;
            margin-top: 25px;
            padding: 15px;
            background-color: #3498db;
            color: white;
            border-radius: 5px;
            cursor: pointer;
        }
        
        dt:hover {
            background-color: #2980b9;
        }
        
        dd {
            margin-left: 0;
            margin-top: 10px;
            padding: 15px;
            background-color: #ecf0f1;
            border-left: 4px solid #3498db;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>Sık Sorulan Sorular</h1>
    
    <dl>
        <dt>HTML nedir?</dt>
        <dd>HTML (Hyper Text Markup Language), web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir. Web sayfalarının temel yapı taşını oluşturur.</dd>
        
        <dt>CSS nedir?</dt>
        <dd>CSS (Cascading Style Sheets), web sayfalarının görsel tasarımını yapmak için kullanılan bir stil dilidir. Renkler, fontlar, düzenler gibi görsel özellikleri belirler.</dd>
        
        <dt>JavaScript nedir?</dt>
        <dd>JavaScript, web sayfalarına etkileşim ve dinamik özellikler eklemek için kullanılan bir programlama dilidir. Modern web uygulamalarının vazgeçilmez bir parçasıdır.</dd>
        
        <dt>Web sitesi nasıl oluşturulur?</dt>
        <dd>Web sitesi oluşturmak için HTML ile yapıyı, CSS ile tasarımı ve JavaScript ile etkileşimi ekleyerek başlayabilirsiniz. Ardından bir web sunucusuna yükleyerek yayınlayabilirsiniz.</dd>
        
        <dt>Responsive tasarım nedir?</dt>
        <dd>Responsive tasarım, web sitelerinin farklı ekran boyutlarına (mobil, tablet, masaüstü) uyum sağlaması için kullanılan bir tasarım yaklaşımıdır.</dd>
    </dl>
</body>
</html>
```

### Meta Veri Gösterimi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Meta Veri Gösterimi</title>
    <style>
        .metadata {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        .metadata dt {
            font-weight: bold;
            color: #2c3e50;
            margin-top: 10px;
            display: inline-block;
            width: 150px;
        }
        
        .metadata dd {
            display: inline;
            margin-left: 10px;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>Dosya Bilgileri</h1>
    
    <div class="metadata">
        <dl>
            <dt>Dosya Adı:</dt>
            <dd>ornek-dosya.html</dd>
            
            <dt>Boyut:</dt>
            <dd>15.2 KB</dd>
            
            <dt>Oluşturulma:</dt>
            <dd>15 Ocak 2024</dd>
            
            <dt>Son Değişiklik:</dt>
            <dd>20 Ocak 2024</dd>
            
            <dt>Yazar:</dt>
            <dd>Ahmet Yılmaz</dd>
            
            <dt>Versiyon:</dt>
            <dd>1.0.0</dd>
        </dl>
    </div>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Tanım Listesi</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
        }
        
        .section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .section h2 {
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
        }
        
        dt {
            font-weight: bold;
            font-size: 1.1em;
            margin-top: 20px;
            color: #e74c3c;
        }
        
        dt:first-child {
            margin-top: 0;
        }
        
        dd {
            margin-left: 25px;
            margin-top: 8px;
            margin-bottom: 15px;
            color: #555;
            line-height: 1.8;
        }
        
        .highlight {
            background-color: #fff3cd;
            padding: 2px 5px;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <h1>Web Geliştirme Terimleri</h1>
    
    <div class="section">
        <h2>Frontend Teknolojileri</h2>
        <dl>
            <dt>HTML</dt>
            <dd>Hyper Text Markup Language - Web sayfalarının yapısını oluşturmak için kullanılan işaretleme dili. Web geliştirmenin temelidir.</dd>
            
            <dt>CSS</dt>
            <dd>Cascading Style Sheets - Web sayfalarının görsel tasarımını yapmak için kullanılan stil dili. <span class="highlight">Flexbox</span> ve <span class="highlight">Grid</span> gibi modern özellikler içerir.</dd>
            
            <dt>JavaScript</dt>
            <dd>Web sayfalarına etkileşim eklemek için kullanılan programlama dili. <span class="highlight">ES6+</span> ile modern özellikler kazanmıştır.</dd>
            
            <dt>React</dt>
            <dd>Facebook tarafından geliştirilen, kullanıcı arayüzü oluşturmak için kullanılan JavaScript kütüphanesi.</dd>
            
            <dt>Vue.js</dt>
            <dd>Progressive JavaScript framework'ü. Küçük projelerden büyük uygulamalara kadar ölçeklenebilir.</dd>
        </dl>
    </div>
    
    <div class="section">
        <h2>Backend Teknolojileri</h2>
        <dl>
            <dt>Node.js</dt>
            <dd>JavaScript'in sunucu tarafında çalışmasını sağlayan runtime ortamı. Asenkron programlama için idealdir.</dd>
            
            <dt>Python</dt>
            <dd>Yüksek seviyeli, genel amaçlı programlama dili. <span class="highlight">Django</span> ve <span class="highlight">Flask</span> gibi web framework'leri içerir.</dd>
            
            <dt>PHP</dt>
            <dd>Web geliştirme için özel olarak tasarlanmış sunucu tarafı programlama dili. Yaygın olarak kullanılır.</dd>
        </dl>
    </div>
    
    <div class="section">
        <h2>Veritabanı Teknolojileri</h2>
        <dl>
            <dt>MySQL</dt>
            <dd>Açık kaynaklı ilişkisel veritabanı yönetim sistemi. Web uygulamalarında yaygın olarak kullanılır.</dd>
            
            <dt>PostgreSQL</dt>
            <dd>Güçlü, açık kaynaklı ilişkisel veritabanı sistemi. Gelişmiş özellikler sunar.</dd>
            
            <dt>MongoDB</dt>
            <dd>NoSQL veritabanı sistemi. Belge tabanlı veri saklama yöntemi kullanır.</dd>
        </dl>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: Tanım listeleri terim-açıklama ilişkilerini göstermek için kullanılmalıdır.

2. **Çoklu Açıklamalar**: Bir terim için birden fazla `<dd>` etiketi kullanılabilir.

3. **Erişilebilirlik**: Ekran okuyucular tanım listelerini doğru şekilde yorumlar.

4. **Stil**: Tanım listelerinin görünümü **CSS** ile tamamen özelleştirilebilir.

5. **Kullanım Alanları**: Sözlükler, FAQ'ler, meta veri gösterimi, terim açıklamaları için idealdir.

## 🎯 İyi Pratikler

- Terim-açıklama ilişkileri için tanım listeleri kullanın
- Sözlük ve FAQ sayfaları için idealdir
- Meta veri gösterimi için kullanın
- Liste stillerini **CSS** ile özelleştirin
- Anlamsal HTML kullanarak erişilebilirliği artırın
- Bir terim için birden fazla açıklama ekleyebilirsiniz

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


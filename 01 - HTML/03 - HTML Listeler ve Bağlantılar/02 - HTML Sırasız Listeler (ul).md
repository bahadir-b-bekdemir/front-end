# 📋 HTML SIRASIZ LİSTELER (ul)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) sırasız listeler, numaralandırılmamış öğeleri göstermek için kullanılır. Sırasız listeler `<ul>` (unordered list) etiketi ile oluşturulur ve her liste öğesi `<li>` (list item) etiketi ile tanımlanır.

## 📋 Sırasız Liste Yapısı

### `<ul>...</ul>`

Sırasız liste kapsayıcısı. İçinde `<li>` etiketleri bulunur.

### `<li>...</li>`

Liste öğesi. Her `<li>` etiketi bir liste maddesini temsil eder.

**Temel kullanım:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sırasız Liste Örneği</title>
</head>
<body>
    <ul>
        <li>İlk öğe</li>
        <li>İkinci öğe</li>
        <li>Üçüncü öğe</li>
    </ul>
</body>
</html>
```

## 📋 Liste İşaretçi Tipleri

### `type` Özelliği (HTML4, artık önerilmiyor)

Liste işaretçi tipini belirler. **CSS** ile yapılması önerilir.

| Değer | Açıklama | Görünüm |
| :---- | :------- | :------ |
| `disc` | Dolu daire (varsayılan) | • |
| `circle` | Boş daire | ○ |
| `square` | Kare | ■ |

## 💡 Kullanım Örnekleri

### Temel Sırasız Liste

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Sırasız Liste</title>
</head>
<body>
    <h2>Alışveriş Listesi</h2>
    <ul>
        <li>Ekmek</li>
        <li>Süt</li>
        <li>Yumurta</li>
        <li>Peynir</li>
        <li>Domates</li>
    </ul>
</body>
</html>
```

### Farklı İşaretçi Tipleri (CSS ile)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Farklı İşaretçi Tipleri</title>
    <style>
        .disc {
            list-style-type: disc;
        }
        
        .circle {
            list-style-type: circle;
        }
        
        .square {
            list-style-type: square;
        }
        
        .none {
            list-style-type: none;
        }
    </style>
</head>
<body>
    <h2>Dolu Daire (varsayılan)</h2>
    <ul class="disc">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ul>
    
    <h2>Boş Daire</h2>
    <ul class="circle">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ul>
    
    <h2>Kare</h2>
    <ul class="square">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ul>
    
    <h2>İşaretçi Yok</h2>
    <ul class="none">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ul>
</body>
</html>
```

### İç İçe Sırasız Listeler

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>İç İçe Sırasız Listeler</title>
    <style>
        ul {
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <h2>Menü Yapısı</h2>
    <ul>
        <li>Ana Sayfa</li>
        <li>Hakkımızda</li>
        <li>Hizmetlerimiz
            <ul>
                <li>Web Tasarım</li>
                <li>Web Geliştirme</li>
                <li>SEO Hizmetleri</li>
            </ul>
        </li>
        <li>İletişim</li>
        <li>Blog
            <ul>
                <li>HTML Dersleri</li>
                <li>CSS Dersleri</li>
                <li>JavaScript Dersleri</li>
            </ul>
        </li>
    </ul>
</body>
</html>
```

### Navigasyon Menüsü

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Navigasyon Menüsü</title>
    <style>
        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            background-color: #2c3e50;
            overflow: hidden;
        }
        
        nav li {
            float: left;
        }
        
        nav li a {
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }
        
        nav li a:hover {
            background-color: #3498db;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#anasayfa">Ana Sayfa</a></li>
            <li><a href="#hakkimizda">Hakkımızda</a></li>
            <li><a href="#hizmetler">Hizmetler</a></li>
            <li><a href="#iletisim">İletişim</a></li>
        </ul>
    </nav>
</body>
</html>
```

### Özel İşaretçiler (CSS ile)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Özel İşaretçiler</title>
    <style>
        .checkmark {
            list-style-type: none;
            padding-left: 0;
        }
        
        .checkmark li {
            padding-left: 30px;
            position: relative;
            margin: 5px 0;
        }
        
        .checkmark li::before {
            content: "✓";
            position: absolute;
            left: 0;
            color: #27ae60;
            font-weight: bold;
            font-size: 1.2em;
        }
        
        .arrow {
            list-style-type: none;
            padding-left: 0;
        }
        
        .arrow li {
            padding-left: 25px;
            position: relative;
            margin: 5px 0;
        }
        
        .arrow li::before {
            content: "→";
            position: absolute;
            left: 0;
            color: #3498db;
            font-weight: bold;
        }
        
        .star {
            list-style-type: none;
            padding-left: 0;
        }
        
        .star li {
            padding-left: 30px;
            position: relative;
            margin: 5px 0;
        }
        
        .star li::before {
            content: "★";
            position: absolute;
            left: 0;
            color: #f39c12;
        }
    </style>
</head>
<body>
    <h2>Onay İşaretli Liste</h2>
    <ul class="checkmark">
        <li>Görev 1 tamamlandı</li>
        <li>Görev 2 tamamlandı</li>
        <li>Görev 3 tamamlandı</li>
    </ul>
    
    <h2>Ok İşaretli Liste</h2>
    <ul class="arrow">
        <li>Birinci adım</li>
        <li>İkinci adım</li>
        <li>Üçüncü adım</li>
    </ul>
    
    <h2>Yıldız İşaretli Liste</h2>
    <ul class="star">
        <li>Önemli öğe 1</li>
        <li>Önemli öğe 2</li>
        <li>Önemli öğe 3</li>
    </ul>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Sırasız Liste Örneği</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        ul {
            margin: 15px 0;
        }
        
        li {
            margin: 8px 0;
        }
        
        .feature-list {
            list-style-type: none;
            padding-left: 0;
        }
        
        .feature-list li {
            padding-left: 30px;
            position: relative;
            margin: 10px 0;
        }
        
        .feature-list li::before {
            content: "✓";
            position: absolute;
            left: 0;
            color: #27ae60;
            font-weight: bold;
            font-size: 1.2em;
        }
        
        .category {
            background-color: #f8f9fa;
            padding: 15px;
            margin: 15px 0;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>Web Geliştirme Teknolojileri</h1>
    
    <div class="category">
        <h2>Frontend Teknolojileri</h2>
        <ul>
            <li>HTML
                <ul>
                    <li>HTML5</li>
                    <li>Semantic HTML</li>
                </ul>
            </li>
            <li>CSS
                <ul>
                    <li>CSS3</li>
                    <li>Flexbox</li>
                    <li>Grid</li>
                </ul>
            </li>
            <li>JavaScript
                <ul>
                    <li>ES6+</li>
                    <li>React</li>
                    <li>Vue.js</li>
                </ul>
            </li>
        </ul>
    </div>
    
    <div class="category">
        <h2>Backend Teknolojileri</h2>
        <ul>
            <li>Node.js</li>
            <li>Python
                <ul>
                    <li>Django</li>
                    <li>Flask</li>
                </ul>
            </li>
            <li>PHP</li>
            <li>Java</li>
        </ul>
    </div>
    
    <div class="category">
        <h2>Özellikler</h2>
        <ul class="feature-list">
            <li>Responsive tasarım</li>
            <li>SEO optimizasyonu</li>
            <li>Hızlı yükleme</li>
            <li>Güvenli yapı</li>
            <li>Modern teknolojiler</li>
        </ul>
    </div>
</body>
</html>
```

### Liste İçinde Bağlantılar

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Liste İçinde Bağlantılar</title>
    <style>
        .link-list {
            list-style-type: none;
            padding-left: 0;
        }
        
        .link-list li {
            margin: 10px 0;
            padding: 10px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .link-list a {
            color: #3498db;
            text-decoration: none;
            font-weight: bold;
        }
        
        .link-list a:hover {
            text-decoration: underline;
            color: #2980b9;
        }
    </style>
</head>
<body>
    <h2>Faydalı Kaynaklar</h2>
    <ul class="link-list">
        <li><a href="https://www.w3.org">W3C</a> - Web standartları</li>
        <li><a href="https://developer.mozilla.org">MDN</a> - Web dokümantasyonu</li>
        <li><a href="https://www.github.com">GitHub</a> - Kod paylaşım platformu</li>
        <li><a href="https://stackoverflow.com">Stack Overflow</a> - Programlama soruları</li>
    </ul>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: Sırasız listeler, sıralama önemli olmadığında kullanılmalıdır.

2. **CSS Stil**: Liste görünümü **CSS** ile tamamen özelleştirilebilir.

3. **Erişilebilirlik**: Ekran okuyucular liste yapısını anlar ve kullanıcıya sunar.

4. **type Özelliği**: HTML5'te `type` özelliği artık önerilmiyor, **CSS** kullanılmalıdır.

5. **Navigasyon**: Sırasız listeler navigasyon menüleri için yaygın olarak kullanılır.

## 🎯 İyi Pratikler

- Sıralama önemli değilse sırasız listeler kullanın
- Navigasyon menüleri için sırasız listeler kullanın
- Liste stillerini **CSS** ile özelleştirin
- Anlamsal HTML kullanarak erişilebilirliği artırın
- İç içe listeler için farklı işaretçi tipleri kullanın
- `type` özelliği yerine **CSS** kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


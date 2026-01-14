# 📱 HTML RESPONSIVE TABLOLAR

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tabloların mobil cihazlarda düzgün görüntülenmesi için responsive tasarım teknikleri kullanılır.

## 📋 Responsive Teknikler

### Overflow Tekniği

Tablonun yatay kaydırılabilir olmasını sağlar.

### Stack Tekniği

Mobilde tabloyu kart görünümüne dönüştürür.

### Hide Columns Tekniği

Küçük ekranlarda bazı sütunları gizler.

## 💡 Kullanım Örnekleri

### Overflow ile Responsive Tablo

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Overflow Tekniği</title>
    <style>
        .table-container {
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 600px;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        
        th {
            background-color: #3498db;
            color: white;
        }
    </style>
</head>
<body>
    <h2>Yatay Kaydırılabilir Tablo</h2>
    <div class="table-container">
        <table>
            <tr>
                <th>Ad</th>
                <th>Soyad</th>
                <th>E-posta</th>
                <th>Telefon</th>
                <th>Adres</th>
                <th>Şehir</th>
            </tr>
            <tr>
                <td>Ahmet</td>
                <td>Yılmaz</td>
                <td>ahmet@example.com</td>
                <td>0555 123 45 67</td>
                <td>İstanbul Caddesi No:123</td>
                <td>Ankara</td>
            </tr>
        </table>
    </div>
</body>
</html>
```

### Stack Tekniği (Kart Görünümü)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stack Tekniği</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th {
            display: none;
        }
        
        td {
            display: block;
            border: none;
            border-bottom: 1px solid #ddd;
            padding: 10px;
            text-align: right;
        }
        
        td::before {
            content: attr(data-label);
            float: left;
            font-weight: bold;
        }
        
        @media (min-width: 768px) {
            th {
                display: table-cell;
                background-color: #3498db;
                color: white;
                padding: 12px;
            }
            
            td {
                display: table-cell;
                text-align: left;
            }
            
            td::before {
                display: none;
            }
        }
    </style>
</head>
<body>
    <h2>Responsive Tablo (Stack)</h2>
    <table>
        <thead>
            <tr>
                <th>Ad</th>
                <th>Soyad</th>
                <th>E-posta</th>
                <th>Telefon</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td data-label="Ad">Ahmet</td>
                <td data-label="Soyad">Yılmaz</td>
                <td data-label="E-posta">ahmet@example.com</td>
                <td data-label="Telefon">0555 123 45 67</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### Hide Columns Tekniği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hide Columns</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
        }
        
        .hide-mobile {
            display: none;
        }
        
        @media (min-width: 768px) {
            .hide-mobile {
                display: table-cell;
            }
        }
    </style>
</head>
<body>
    <h2>Responsive Tablo (Hide Columns)</h2>
    <table>
        <tr>
            <th>Ad</th>
            <th>Soyad</th>
            <th class="hide-mobile">E-posta</th>
            <th class="hide-mobile">Telefon</th>
            <th>Şehir</th>
        </tr>
        <tr>
            <td>Ahmet</td>
            <td>Yılmaz</td>
            <td class="hide-mobile">ahmet@example.com</td>
            <td class="hide-mobile">0555 123 45 67</td>
            <td>Ankara</td>
        </tr>
    </table>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Viewport**: Responsive tablolar için `viewport` meta etiketi gereklidir.

2. **Media Queries**: Farklı ekran boyutları için **CSS** media queries kullanılır.

3. **Touch Scrolling**: Mobilde yatay kaydırma için `-webkit-overflow-scrolling: touch;` kullanılır.

4. **Performans**: Büyük tablolarda performans sorunları olabilir.

## 🎯 İyi Pratikler

- Viewport meta etiketi ekleyin
- Mobilde önemli sütunları gösterin
- Yatay kaydırma için overflow kullanın
- Stack tekniği ile kart görünümü oluşturun
- Test edin (farklı cihazlarda)

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


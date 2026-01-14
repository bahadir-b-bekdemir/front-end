# ♿ HTML TABLO ERİŞİLEBİLİRLİK (caption, scope)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tabloların erişilebilir olması için `<caption>`, `scope` ve diğer erişilebilirlik özellikleri kullanılmalıdır.

## 📋 Erişilebilirlik Özellikleri

### `<caption>...</caption>`

Tablo başlığı. Tablonun ne hakkında olduğunu açıklar.

### `scope` Özelliği

Başlık hücresinin hangi hücrelere ait olduğunu belirtir (`row`, `col`, `rowgroup`, `colgroup`).

### `headers` Özelliği

Hücrenin hangi başlıklara ait olduğunu belirtir.

### `id` ve `headers` Kullanımı

Karmaşık tablolarda hücre-başlık ilişkisini belirtmek için kullanılır.

## 💡 Kullanım Örnekleri

### caption ile Tablo Başlığı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>caption Örneği</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        caption {
            font-size: 1.2em;
            font-weight: bold;
            padding: 10px;
            background-color: #3498db;
            color: white;
            caption-side: top;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        
        th {
            background-color: #2c3e50;
            color: white;
        }
    </style>
</head>
<body>
    <table>
        <caption>Öğrenci Not Listesi - 2024 Bahar Dönemi</caption>
        <thead>
            <tr>
                <th>Öğrenci No</th>
                <th>Ad Soyad</th>
                <th>Matematik</th>
                <th>Türkçe</th>
                <th>Ortalama</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>101</td>
                <td>Ahmet Yılmaz</td>
                <td>85</td>
                <td>90</td>
                <td>87.5</td>
            </tr>
            <tr>
                <td>102</td>
                <td>Ayşe Demir</td>
                <td>92</td>
                <td>88</td>
                <td>90.0</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### scope ile Başlık İlişkisi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>scope Örneği</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        
        th {
            background-color: #27ae60;
            color: white;
        }
    </style>
</head>
<body>
    <table>
        <caption>Çalışan Maaş Listesi</caption>
        <thead>
            <tr>
                <th scope="col">Ad Soyad</th>
                <th scope="col">Departman</th>
                <th scope="col">Maaş</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th scope="row">Ahmet Yılmaz</th>
                <td>Yazılım</td>
                <td>25.000 TL</td>
            </tr>
            <tr>
                <th scope="row">Ayşe Demir</th>
                <td>Tasarım</td>
                <td>20.000 TL</td>
            </tr>
            <tr>
                <th scope="row">Mehmet Kaya</th>
                <td>Pazarlama</td>
                <td>22.000 TL</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### Karmaşık Tablo (id ve headers)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>id ve headers Örneği</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        
        th {
            background-color: #2c3e50;
            color: white;
        }
        
        caption {
            font-weight: bold;
            font-size: 1.1em;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <table>
        <caption>Haftalık Ders Programı</caption>
        <thead>
            <tr>
                <th id="time" scope="col">Saat</th>
                <th id="mon" scope="col">Pazartesi</th>
                <th id="tue" scope="col">Salı</th>
                <th id="wed" scope="col">Çarşamba</th>
                <th id="thu" scope="col">Perşembe</th>
                <th id="fri" scope="col">Cuma</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th id="hour1" scope="row">09:00</th>
                <td headers="mon hour1">Matematik</td>
                <td headers="tue hour1">Türkçe</td>
                <td headers="wed hour1">Fen</td>
                <td headers="thu hour1">İngilizce</td>
                <td headers="fri hour1">Beden</td>
            </tr>
            <tr>
                <th id="hour2" scope="row">10:00</th>
                <td headers="mon hour2">Tarih</td>
                <td headers="tue hour2">Coğrafya</td>
                <td headers="wed hour2">Matematik</td>
                <td headers="thu hour2">Türkçe</td>
                <td headers="fri hour2">Müzik</td>
            </tr>
            <tr>
                <th id="hour3" scope="row">11:00</th>
                <td headers="mon hour3">Fen</td>
                <td headers="tue hour3">Matematik</td>
                <td headers="wed hour3">İngilizce</td>
                <td headers="thu hour3">Beden</td>
                <td headers="fri hour3">Resim</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

### scope="rowgroup" ve scope="colgroup"

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>rowgroup ve colgroup</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        
        thead th {
            background-color: #3498db;
            color: white;
        }
        
        tbody th {
            background-color: #2c3e50;
            color: white;
        }
        
        tfoot th {
            background-color: #27ae60;
            color: white;
        }
    </style>
</head>
<body>
    <table>
        <caption>Satış Raporu</caption>
        <thead>
            <tr>
                <th scope="col">Ürün</th>
                <th scope="colgroup" colspan="2">2023</th>
                <th scope="colgroup" colspan="2">2024</th>
            </tr>
            <tr>
                <th></th>
                <th scope="col">Q1</th>
                <th scope="col">Q2</th>
                <th scope="col">Q1</th>
                <th scope="col">Q2</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th scope="row">Laptop</th>
                <td>100</td>
                <td>120</td>
                <td>130</td>
                <td>140</td>
            </tr>
            <tr>
                <th scope="row">Telefon</th>
                <td>80</td>
                <td>90</td>
                <td>95</td>
                <td>100</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th scope="row">Toplam</th>
                <td>180</td>
                <td>210</td>
                <td>225</td>
                <td>240</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### Kapsamlı Erişilebilir Tablo

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Erişilebilir Tablo</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        caption {
            font-size: 1.3em;
            font-weight: bold;
            padding: 15px;
            background-color: #2c3e50;
            color: white;
            caption-side: top;
            text-align: left;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px 15px;
            text-align: left;
        }
        
        thead th {
            background-color: #3498db;
            color: white;
            font-weight: bold;
        }
        
        tbody th {
            background-color: #ecf0f1;
            font-weight: bold;
        }
        
        tbody tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        
        tbody tr:hover {
            background-color: #e8f4f8;
        }
        
        tfoot {
            background-color: #2c3e50;
            color: white;
        }
        
        tfoot th, tfoot td {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <table>
        <caption>
            Aylık Satış Raporu - Ocak 2024
            <br>
            <span style="font-size: 0.8em; font-weight: normal;">
                Bu tablo, her satış kaydının detaylarını göstermektedir.
            </span>
        </caption>
        <thead>
            <tr>
                <th scope="col">Tarih</th>
                <th scope="col">Müşteri</th>
                <th scope="col">Ürün</th>
                <th scope="col">Miktar</th>
                <th scope="col">Birim Fiyat</th>
                <th scope="col">Toplam</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>01.01.2024</td>
                <td>Ahmet Yılmaz</td>
                <td>Laptop</td>
                <td>1</td>
                <td>25.000 TL</td>
                <td>25.000 TL</td>
            </tr>
            <tr>
                <td>05.01.2024</td>
                <td>Ayşe Demir</td>
                <td>Telefon</td>
                <td>2</td>
                <td>8.000 TL</td>
                <td>16.000 TL</td>
            </tr>
            <tr>
                <td>10.01.2024</td>
                <td>Mehmet Kaya</td>
                <td>Tablet</td>
                <td>1</td>
                <td>12.000 TL</td>
                <td>12.000 TL</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th scope="row" colspan="5">Toplam Satış</th>
                <td>53.000 TL</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### caption-side ile Başlık Konumu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>caption-side</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        caption {
            padding: 10px;
            font-weight: bold;
            background-color: #3498db;
            color: white;
        }
        
        .top {
            caption-side: top;
        }
        
        .bottom {
            caption-side: bottom;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        
        th {
            background-color: #2c3e50;
            color: white;
        }
    </style>
</head>
<body>
    <h2>Üstte Başlık</h2>
    <table class="top">
        <caption>Öğrenci Listesi</caption>
        <tr>
            <th>Ad</th>
            <th>Soyad</th>
            <th>Not</th>
        </tr>
        <tr>
            <td>Ahmet</td>
            <td>Yılmaz</td>
            <td>85</td>
        </tr>
    </table>
    
    <h2>Altta Başlık</h2>
    <table class="bottom">
        <caption>Öğrenci Listesi</caption>
        <tr>
            <th>Ad</th>
            <th>Soyad</th>
            <th>Not</th>
        </tr>
        <tr>
            <td>Ahmet</td>
            <td>Yılmaz</td>
            <td>85</td>
        </tr>
    </table>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **caption**: Her tablo için bir `<caption>` eklenmelidir. Tablonun ne hakkında olduğunu açıklar.

2. **scope**: Başlık hücrelerinin hangi hücrelere ait olduğunu belirtir. Ekran okuyucular için önemlidir.

3. **id ve headers**: Karmaşık tablolarda hücre-başlık ilişkisini belirtmek için kullanılır.

4. **Erişilebilirlik**: Tablolar ekran okuyucular tarafından doğru şekilde yorumlanmalıdır.

5. **ARIA**: Gerekli durumlarda ARIA özellikleri de kullanılabilir.

## 🎯 İyi Pratikler

- Her tablo için `<caption>` ekleyin
- Başlık hücreleri için `scope` özelliği kullanın
- Karmaşık tablolarda `id` ve `headers` kullanın
- Anlamsal HTML kullanın (`<thead>`, `<tbody>`, `<tfoot>`)
- Tablo yapısını basit tutun, gerekirse bölün
- Ekran okuyucularla test edin
- Açıklayıcı başlıklar kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


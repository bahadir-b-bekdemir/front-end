# 📋 HTML TABLO BAŞLIKLARI (thead, tbody, tfoot)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tabloları yapılandırmak için `<thead>`, `<tbody>` ve `<tfoot>` etiketleri kullanılır. Bu etiketler tabloyu anlamsal olarak bölümlere ayırır.

## 📋 Tablo Bölüm Etiketleri

### `<thead>...</thead>`

Table header - Tablo başlık bölümü. Tablonun üst kısmındaki başlık satırlarını içerir.

### `<tbody>...</tbody>`

Table body - Tablo gövde bölümü. Tablonun ana veri satırlarını içerir.

### `<tfoot>...</tfoot>`

Table footer - Tablo alt bilgi bölümü. Tablonun alt kısmındaki özet bilgileri içerir.

**Temel kullanım:**
```html
<table>
    <thead>
        <tr>
            <th>Başlık 1</th>
            <th>Başlık 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Veri 1</td>
            <td>Veri 2</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Toplam</td>
            <td>100</td>
        </tr>
    </tfoot>
</table>
```

## 💡 Kullanım Örnekleri

### Temel Yapı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Tablo Yapısı</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        thead {
            background-color: #3498db;
            color: white;
        }
        
        th, td {
            padding: 12px;
            text-align: left;
            border: 1px solid #ddd;
        }
        
        tbody tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        
        tfoot {
            background-color: #2c3e50;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Satış Raporu</h2>
    <table>
        <thead>
            <tr>
                <th>Ürün</th>
                <th>Miktar</th>
                <th>Fiyat</th>
                <th>Toplam</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Laptop</td>
                <td>2</td>
                <td>15.000 TL</td>
                <td>30.000 TL</td>
            </tr>
            <tr>
                <td>Telefon</td>
                <td>3</td>
                <td>8.000 TL</td>
                <td>24.000 TL</td>
            </tr>
            <tr>
                <td>Tablet</td>
                <td>1</td>
                <td>5.000 TL</td>
                <td>5.000 TL</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="3">Genel Toplam</td>
                <td>59.000 TL</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### Detaylı Satış Tablosu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Detaylı Satış Tablosu</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        thead {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        th {
            padding: 15px;
            text-align: left;
            font-weight: bold;
            text-transform: uppercase;
            font-size: 0.9em;
        }
        
        tbody td {
            padding: 12px 15px;
            border-bottom: 1px solid #ddd;
        }
        
        tbody tr:hover {
            background-color: #e8f4f8;
        }
        
        tfoot {
            background-color: #2c3e50;
            color: white;
        }
        
        tfoot td {
            padding: 15px;
            font-weight: bold;
            font-size: 1.1em;
        }
        
        .text-right {
            text-align: right;
        }
    </style>
</head>
<body>
    <h1>Aylık Satış Raporu</h1>
    
    <table>
        <thead>
            <tr>
                <th>Tarih</th>
                <th>Ürün</th>
                <th>Müşteri</th>
                <th class="text-right">Miktar</th>
                <th class="text-right">Birim Fiyat</th>
                <th class="text-right">Toplam</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>01.01.2024</td>
                <td>Laptop</td>
                <td>Ahmet Yılmaz</td>
                <td class="text-right">1</td>
                <td class="text-right">25.000 TL</td>
                <td class="text-right">25.000 TL</td>
            </tr>
            <tr>
                <td>05.01.2024</td>
                <td>Telefon</td>
                <td>Ayşe Demir</td>
                <td class="text-right">2</td>
                <td class="text-right">8.000 TL</td>
                <td class="text-right">16.000 TL</td>
            </tr>
            <tr>
                <td>10.01.2024</td>
                <td>Tablet</td>
                <td>Mehmet Kaya</td>
                <td class="text-right">1</td>
                <td class="text-right">12.000 TL</td>
                <td class="text-right">12.000 TL</td>
            </tr>
            <tr>
                <td>15.01.2024</td>
                <td>Laptop</td>
                <td>Fatma Şahin</td>
                <td class="text-right">1</td>
                <td class="text-right">25.000 TL</td>
                <td class="text-right">25.000 TL</td>
            </tr>
            <tr>
                <td>20.01.2024</td>
                <td>Telefon</td>
                <td>Ali Çelik</td>
                <td class="text-right">3</td>
                <td class="text-right">8.000 TL</td>
                <td class="text-right">24.000 TL</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="3">Toplam Satış</td>
                <td class="text-right">8</td>
                <td></td>
                <td class="text-right">102.000 TL</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### Öğrenci Not Tablosu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Öğrenci Not Tablosu</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        thead {
            background-color: #27ae60;
            color: white;
        }
        
        th, td {
            padding: 12px;
            text-align: center;
            border: 1px solid #ddd;
        }
        
        tbody tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        
        tbody tr:hover {
            background-color: #e8f5e9;
        }
        
        tfoot {
            background-color: #34495e;
            color: white;
        }
        
        .pass {
            color: #27ae60;
            font-weight: bold;
        }
        
        .fail {
            color: #e74c3c;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Öğrenci Notları</h2>
    <table>
        <thead>
            <tr>
                <th>Öğrenci No</th>
                <th>Ad Soyad</th>
                <th>Matematik</th>
                <th>Türkçe</th>
                <th>Fen</th>
                <th>Ortalama</th>
                <th>Durum</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>101</td>
                <td>Ahmet Yılmaz</td>
                <td>85</td>
                <td>90</td>
                <td>88</td>
                <td>87.7</td>
                <td class="pass">Geçti</td>
            </tr>
            <tr>
                <td>102</td>
                <td>Ayşe Demir</td>
                <td>92</td>
                <td>88</td>
                <td>95</td>
                <td>91.7</td>
                <td class="pass">Geçti</td>
            </tr>
            <tr>
                <td>103</td>
                <td>Mehmet Kaya</td>
                <td>45</td>
                <td>50</td>
                <td>48</td>
                <td>47.7</td>
                <td class="fail">Kaldı</td>
            </tr>
            <tr>
                <td>104</td>
                <td>Fatma Şahin</td>
                <td>78</td>
                <td>82</td>
                <td>80</td>
                <td>80.0</td>
                <td class="pass">Geçti</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="2">Sınıf Ortalaması</td>
                <td>75.0</td>
                <td>77.5</td>
                <td>77.8</td>
                <td>76.8</td>
                <td>-</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### Stok Takip Tablosu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Stok Takip Tablosu</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        thead {
            background-color: #e74c3c;
            color: white;
        }
        
        th {
            padding: 15px;
            text-align: left;
        }
        
        tbody td {
            padding: 12px 15px;
            border-bottom: 1px solid #ddd;
        }
        
        tbody tr:hover {
            background-color: #ffeaa7;
        }
        
        tfoot {
            background-color: #2c3e50;
            color: white;
        }
        
        .low-stock {
            color: #e74c3c;
            font-weight: bold;
        }
        
        .in-stock {
            color: #27ae60;
        }
    </style>
</head>
<body>
    <h2>Stok Durumu</h2>
    <table>
        <thead>
            <tr>
                <th>Ürün Kodu</th>
                <th>Ürün Adı</th>
                <th>Kategori</th>
                <th>Stok Miktarı</th>
                <th>Minimum Stok</th>
                <th>Durum</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>PRD001</td>
                <td>Laptop</td>
                <td>Elektronik</td>
                <td>15</td>
                <td>10</td>
                <td class="in-stock">Yeterli</td>
            </tr>
            <tr>
                <td>PRD002</td>
                <td>Telefon</td>
                <td>Elektronik</td>
                <td>5</td>
                <td>10</td>
                <td class="low-stock">Düşük</td>
            </tr>
            <tr>
                <td>PRD003</td>
                <td>Tablet</td>
                <td>Elektronik</td>
                <td>20</td>
                <td>10</td>
                <td class="in-stock">Yeterli</td>
            </tr>
            <tr>
                <td>PRD004</td>
                <td>Mouse</td>
                <td>Aksesuar</td>
                <td>3</td>
                <td>15</td>
                <td class="low-stock">Düşük</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="3">Toplam Ürün Sayısı</td>
                <td>43</td>
                <td>-</td>
                <td>-</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Tablo Örneği</title>
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
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        thead {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        thead th {
            padding: 18px;
            text-align: left;
            font-weight: bold;
            text-transform: uppercase;
            font-size: 0.85em;
            letter-spacing: 1px;
        }
        
        tbody {
            background-color: white;
        }
        
        tbody td {
            padding: 15px 18px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        tbody tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        
        tbody tr:hover {
            background-color: #e3f2fd;
            transform: scale(1.01);
            transition: all 0.2s;
        }
        
        tfoot {
            background-color: #2c3e50;
            color: white;
        }
        
        tfoot td {
            padding: 18px;
            font-weight: bold;
            font-size: 1.1em;
        }
        
        .text-right {
            text-align: right;
        }
        
        .badge {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.85em;
            font-weight: bold;
        }
        
        .badge-success {
            background-color: #27ae60;
            color: white;
        }
        
        .badge-warning {
            background-color: #f39c12;
            color: white;
        }
        
        .badge-danger {
            background-color: #e74c3c;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Proje Durum Raporu</h1>
    
    <table>
        <thead>
            <tr>
                <th>Proje ID</th>
                <th>Proje Adı</th>
                <th>Yönetici</th>
                <th class="text-right">Bütçe</th>
                <th class="text-right">Harcanan</th>
                <th>İlerleme</th>
                <th>Durum</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>PRJ001</td>
                <td>Web Sitesi Geliştirme</td>
                <td>Ahmet Yılmaz</td>
                <td class="text-right">100.000 TL</td>
                <td class="text-right">75.000 TL</td>
                <td>75%</td>
                <td><span class="badge badge-success">Devam Ediyor</span></td>
            </tr>
            <tr>
                <td>PRJ002</td>
                <td>Mobil Uygulama</td>
                <td>Ayşe Demir</td>
                <td class="text-right">150.000 TL</td>
                <td class="text-right">120.000 TL</td>
                <td>80%</td>
                <td><span class="badge badge-success">Devam Ediyor</span></td>
            </tr>
            <tr>
                <td>PRJ003</td>
                <td>E-Ticaret Platformu</td>
                <td>Mehmet Kaya</td>
                <td class="text-right">200.000 TL</td>
                <td class="text-right">210.000 TL</td>
                <td>95%</td>
                <td><span class="badge badge-danger">Bütçe Aşıldı</span></td>
            </tr>
            <tr>
                <td>PRJ004</td>
                <td>CRM Sistemi</td>
                <td>Fatma Şahin</td>
                <td class="text-right">80.000 TL</td>
                <td class="text-right">45.000 TL</td>
                <td>50%</td>
                <td><span class="badge badge-warning">Gecikme Var</span></td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="3">Toplam</td>
                <td class="text-right">530.000 TL</td>
                <td class="text-right">450.000 TL</td>
                <td>-</td>
                <td>-</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Sıralama**: `<thead>`, `<tbody>`, `<tfoot>` sırası önemlidir. Tarayıcılar bu sırayı korur.

2. **Anlamsal HTML**: Bu etiketler tabloyu anlamsal olarak bölümlere ayırır, **SEO** ve erişilebilirlik için önemlidir.

3. **Stil**: Her bölüm için farklı stiller uygulanabilir.

4. **Yazdırma**: `<thead>` ve `<tfoot>` yazdırma sırasında her sayfada tekrarlanabilir.

5. **Zorunluluk**: `<tbody>` etiketi kullanılmasa bile tarayıcılar otomatik olarak oluşturur.

## 🎯 İyi Pratikler

- Tabloları `<thead>`, `<tbody>`, `<tfoot>` ile yapılandırın
- Her bölüm için uygun stiller kullanın
- `<tfoot>` ile özet bilgileri gösterin
- Anlamsal HTML kullanarak erişilebilirliği artırın
- Hover efektleri ile kullanıcı deneyimini iyileştirin
- Yazdırma için `<thead>` ve `<tfoot>` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


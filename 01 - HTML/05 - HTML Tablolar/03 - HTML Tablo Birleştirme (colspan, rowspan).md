# 🔗 HTML TABLO BİRLEŞTİRME (colspan, rowspan)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) tablo hücrelerini birleştirmek için `colspan` ve `rowspan` özellikleri kullanılır.

## 📋 Birleştirme Özellikleri

### `colspan` Özelliği

Bir hücrenin kaç sütunu kaplayacağını belirler. Sütun birleştirme için kullanılır.

### `rowspan` Özelliği

Bir hücrenin kaç satırı kaplayacağını belirler. Satır birleştirme için kullanılır.

**Temel kullanım:**
```html
<td colspan="2">İki sütun kaplar</td>
<td rowspan="2">İki satır kaplar</td>
```

## 💡 Kullanım Örnekleri

### colspan ile Sütun Birleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>colspan Örneği</title>
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
            background-color: #3498db;
            color: white;
        }
    </style>
</head>
<body>
    <h2>colspan Örneği</h2>
    <table>
        <tr>
            <th>Ad</th>
            <th>Soyad</th>
            <th colspan="2">İletişim</th>
        </tr>
        <tr>
            <td>Ahmet</td>
            <td>Yılmaz</td>
            <td>Telefon</td>
            <td>E-posta</td>
        </tr>
        <tr>
            <td>Ayşe</td>
            <td>Demir</td>
            <td>Telefon</td>
            <td>E-posta</td>
        </tr>
    </table>
</body>
</html>
```

### rowspan ile Satır Birleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>rowspan Örneği</title>
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
            background-color: #27ae60;
            color: white;
        }
    </style>
</head>
<body>
    <h2>rowspan Örneği</h2>
    <table>
        <tr>
            <th>Kategori</th>
            <th>Ürün</th>
            <th>Fiyat</th>
        </tr>
        <tr>
            <td rowspan="3">Elektronik</td>
            <td>Laptop</td>
            <td>25.000 TL</td>
        </tr>
        <tr>
            <td>Telefon</td>
            <td>8.000 TL</td>
        </tr>
        <tr>
            <td>Tablet</td>
            <td>5.000 TL</td>
        </tr>
        <tr>
            <td rowspan="2">Aksesuar</td>
            <td>Mouse</td>
            <td>500 TL</td>
        </tr>
        <tr>
            <td>Klavye</td>
            <td>1.000 TL</td>
        </tr>
    </table>
</body>
</html>
```

### Kombine Kullanım (colspan + rowspan)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kombine Kullanım</title>
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
        
        .header {
            background-color: #e74c3c;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Kombine Birleştirme</h2>
    <table>
        <tr>
            <th rowspan="2">Bölge</th>
            <th colspan="2">Satışlar</th>
            <th rowspan="2">Toplam</th>
        </tr>
        <tr>
            <th>Q1</th>
            <th>Q2</th>
        </tr>
        <tr>
            <td>İstanbul</td>
            <td>100.000 TL</td>
            <td>120.000 TL</td>
            <td>220.000 TL</td>
        </tr>
        <tr>
            <td>Ankara</td>
            <td>80.000 TL</td>
            <td>90.000 TL</td>
            <td>170.000 TL</td>
        </tr>
        <tr>
            <td>İzmir</td>
            <td>60.000 TL</td>
            <td>70.000 TL</td>
            <td>130.000 TL</td>
        </tr>
        <tr>
            <td class="header">Genel Toplam</td>
            <td class="header">240.000 TL</td>
            <td class="header">280.000 TL</td>
            <td class="header">520.000 TL</td>
        </tr>
    </table>
</body>
</html>
```

### Ders Programı Tablosu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Ders Programı</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 15px;
            text-align: center;
        }
        
        th {
            background-color: #3498db;
            color: white;
        }
        
        .time {
            background-color: #2c3e50;
            color: white;
            font-weight: bold;
        }
        
        .break {
            background-color: #f39c12;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Haftalık Ders Programı</h2>
    <table>
        <tr>
            <th rowspan="2">Saat</th>
            <th>Pazartesi</th>
            <th>Salı</th>
            <th>Çarşamba</th>
            <th>Perşembe</th>
            <th>Cuma</th>
        </tr>
        <tr>
            <th>Ders</th>
            <th>Ders</th>
            <th>Ders</th>
            <th>Ders</th>
            <th>Ders</th>
        </tr>
        <tr>
            <td class="time">09:00</td>
            <td>Matematik</td>
            <td>Türkçe</td>
            <td>Fen</td>
            <td>İngilizce</td>
            <td>Beden</td>
        </tr>
        <tr>
            <td class="time">10:00</td>
            <td>Tarih</td>
            <td>Coğrafya</td>
            <td>Matematik</td>
            <td>Türkçe</td>
            <td>Müzik</td>
        </tr>
        <tr>
            <td class="break" colspan="6">Teneffüs</td>
        </tr>
        <tr>
            <td class="time">11:00</td>
            <td>Fen</td>
            <td>Matematik</td>
            <td>İngilizce</td>
            <td>Beden</td>
            <td>Resim</td>
        </tr>
    </table>
</body>
</html>
```

### Satış Raporu Tablosu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Satış Raporu</title>
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
            background-color: #27ae60;
            color: white;
        }
        
        .quarter {
            background-color: #3498db;
            color: white;
            font-weight: bold;
        }
        
        .total {
            background-color: #2c3e50;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Yıllık Satış Raporu</h2>
    <table>
        <tr>
            <th rowspan="2">Bölge</th>
            <th colspan="4">Çeyrekler</th>
            <th rowspan="2">Yıllık Toplam</th>
        </tr>
        <tr>
            <th class="quarter">Q1</th>
            <th class="quarter">Q2</th>
            <th class="quarter">Q3</th>
            <th class="quarter">Q4</th>
        </tr>
        <tr>
            <td>İstanbul</td>
            <td>100.000</td>
            <td>120.000</td>
            <td>110.000</td>
            <td>130.000</td>
            <td>460.000</td>
        </tr>
        <tr>
            <td>Ankara</td>
            <td>80.000</td>
            <td>90.000</td>
            <td>85.000</td>
            <td>95.000</td>
            <td>350.000</td>
        </tr>
        <tr>
            <td>İzmir</td>
            <td>60.000</td>
            <td>70.000</td>
            <td>65.000</td>
            <td>75.000</td>
            <td>270.000</td>
        </tr>
        <tr>
            <td class="total">Toplam</td>
            <td class="total">240.000</td>
            <td class="total">280.000</td>
            <td class="total">260.000</td>
            <td class="total">300.000</td>
            <td class="total">1.080.000</td>
        </tr>
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
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        
        th {
            background-color: #9b59b6;
            color: white;
        }
        
        .student-name {
            background-color: #ecf0f1;
            font-weight: bold;
            text-align: left;
        }
        
        .average {
            background-color: #3498db;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h2>Öğrenci Notları</h2>
    <table>
        <tr>
            <th rowspan="2">Öğrenci</th>
            <th colspan="3">Sınavlar</th>
            <th rowspan="2">Ortalama</th>
        </tr>
        <tr>
            <th>1. Sınav</th>
            <th>2. Sınav</th>
            <th>Final</th>
        </tr>
        <tr>
            <td class="student-name">Ahmet Yılmaz</td>
            <td>85</td>
            <td>90</td>
            <td>88</td>
            <td class="average">87.7</td>
        </tr>
        <tr>
            <td class="student-name">Ayşe Demir</td>
            <td>92</td>
            <td>88</td>
            <td>95</td>
            <td class="average">91.7</td>
        </tr>
        <tr>
            <td class="student-name">Mehmet Kaya</td>
            <td>45</td>
            <td>50</td>
            <td>48</td>
            <td class="average">47.7</td>
        </tr>
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
    <title>Kapsamlı Birleştirme Örneği</title>
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
        
        th, td {
            border: 1px solid #ddd;
            padding: 15px;
            text-align: center;
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            font-weight: bold;
        }
        
        .main-header {
            background-color: #2c3e50;
            font-size: 1.1em;
        }
        
        .sub-header {
            background-color: #34495e;
        }
        
        .region {
            background-color: #ecf0f1;
            font-weight: bold;
            text-align: left;
        }
        
        .total-row {
            background-color: #27ae60;
            color: white;
            font-weight: bold;
        }
        
        .total-col {
            background-color: #e74c3c;
            color: white;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Bölgesel Satış Raporu</h1>
    
    <table>
        <tr>
            <th rowspan="2" class="main-header">Bölge</th>
            <th colspan="3" class="main-header">2023</th>
            <th colspan="3" class="main-header">2024</th>
            <th rowspan="2" class="main-header">Toplam</th>
        </tr>
        <tr>
            <th class="sub-header">Q1</th>
            <th class="sub-header">Q2</th>
            <th class="sub-header">Q3</th>
            <th class="sub-header">Q1</th>
            <th class="sub-header">Q2</th>
            <th class="sub-header">Q3</th>
        </tr>
        <tr>
            <td class="region">İstanbul</td>
            <td>100.000</td>
            <td>120.000</td>
            <td>110.000</td>
            <td>130.000</td>
            <td>140.000</td>
            <td>135.000</td>
            <td class="total-col">730.000</td>
        </tr>
        <tr>
            <td class="region">Ankara</td>
            <td>80.000</td>
            <td>90.000</td>
            <td>85.000</td>
            <td>95.000</td>
            <td>100.000</td>
            <td>98.000</td>
            <td class="total-col">548.000</td>
        </tr>
        <tr>
            <td class="region">İzmir</td>
            <td>60.000</td>
            <td>70.000</td>
            <td>65.000</td>
            <td>75.000</td>
            <td>80.000</td>
            <td>78.000</td>
            <td class="total-col">428.000</td>
        </tr>
        <tr>
            <td class="total-row">Toplam</td>
            <td class="total-row">240.000</td>
            <td class="total-row">280.000</td>
            <td class="total-row">260.000</td>
            <td class="total-row">300.000</td>
            <td class="total-row">320.000</td>
            <td class="total-row">311.000</td>
            <td class="total-row">1.706.000</td>
        </tr>
    </table>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **colspan**: Bir hücrenin kaç sütunu kaplayacağını belirler. Birleştirilen sütun sayısı kadar `<td>` veya `<th>` etiketi atlanmalıdır.

2. **rowspan**: Bir hücrenin kaç satırı kaplayacağını belirler. Birleştirilen satır sayısı kadar satırda o sütunda hücre olmamalıdır.

3. **Hesaplama**: Toplam sütun ve satır sayısı tutarlı olmalıdır.

4. **Stil**: Birleştirilmiş hücreler için özel stiller uygulanabilir.

5. **Erişilebilirlik**: Birleştirilmiş hücreler ekran okuyucular için karmaşık olabilir, dikkatli kullanılmalıdır.

## 🎯 İyi Pratikler

- Birleştirme işlemlerini dikkatli planlayın
- Sütun ve satır sayılarını kontrol edin
- Birleştirilmiş hücreler için açıklayıcı içerik kullanın
- Stil ile birleştirilmiş hücreleri vurgulayın
- Erişilebilirlik için dikkatli kullanın
- Karmaşık tablolarda test yapın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📊 HTML TEMEL TABLO YAPISI

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) verileri satır ve sütunlar halinde göstermek için tablolar kullanılır. Tablolar `<table>` etiketi ile oluşturulur.

## 📋 Tablo Etiketleri

### `<table>...</table>`

Tablo kapsayıcısı. Tüm tablo içeriği bu etiket içinde yer alır.

### `<tr>...</tr>`

Table row - Tablo satırı. Her satır bir `<tr>` etiketi ile tanımlanır.

### `<td>...</td>`

Table data - Tablo hücresi. Her hücre bir `<td>` etiketi ile tanımlanır.

### `<th>...</th>`

Table header - Tablo başlık hücresi. Genellikle kalın ve ortalanmış görüntülenir.

**Temel kullanım:**
```html
<table>
    <tr>
        <th>Başlık 1</th>
        <th>Başlık 2</th>
    </tr>
    <tr>
        <td>Veri 1</td>
        <td>Veri 2</td>
    </tr>
</table>
```

## 💡 Kullanım Örnekleri

### Basit Tablo

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Basit Tablo</title>
</head>
<body>
    <h2>Öğrenci Listesi</h2>
    <table>
        <tr>
            <th>Ad</th>
            <th>Soyad</th>
            <th>Yaş</th>
        </tr>
        <tr>
            <td>Ahmet</td>
            <td>Yılmaz</td>
            <td>25</td>
        </tr>
        <tr>
            <td>Ayşe</td>
            <td>Demir</td>
            <td>23</td>
        </tr>
        <tr>
            <td>Mehmet</td>
            <td>Kaya</td>
            <td>27</td>
        </tr>
    </table>
</body>
</html>
```

### Stil ile Tablo

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Stil ile Tablo</title>
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
            background-color: #3498db;
            color: white;
            font-weight: bold;
        }
        
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        
        tr:hover {
            background-color: #e8f4f8;
        }
    </style>
</head>
<body>
    <h2>Stil Uygulanmış Tablo</h2>
    <table>
        <tr>
            <th>Ürün</th>
            <th>Fiyat</th>
            <th>Stok</th>
        </tr>
        <tr>
            <td>Laptop</td>
            <td>15.000 TL</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Telefon</td>
            <td>8.000 TL</td>
            <td>25</td>
        </tr>
        <tr>
            <td>Tablet</td>
            <td>5.000 TL</td>
            <td>15</td>
        </tr>
    </table>
</body>
</html>
```

### Başlık ve Veri Hücreleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Başlık ve Veri Hücreleri</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th {
            background-color: #2c3e50;
            color: white;
            padding: 15px;
            text-align: left;
        }
        
        td {
            padding: 12px;
            border-bottom: 1px solid #ddd;
        }
        
        tr:hover {
            background-color: #f5f5f5;
        }
    </style>
</head>
<body>
    <h2>Çalışan Bilgileri</h2>
    <table>
        <tr>
            <th>ID</th>
            <th>Ad Soyad</th>
            <th>Departman</th>
            <th>Maaş</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Ahmet Yılmaz</td>
            <td>Yazılım</td>
            <td>25.000 TL</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Ayşe Demir</td>
            <td>Tasarım</td>
            <td>20.000 TL</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Mehmet Kaya</td>
            <td>Pazarlama</td>
            <td>22.000 TL</td>
        </tr>
    </table>
</body>
</html>
```

### Çok Sütunlu Tablo

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çok Sütunlu Tablo</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: center;
        }
        
        th {
            background-color: #27ae60;
            color: white;
        }
        
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
    </style>
</head>
<body>
    <h2>Haftalık Ders Programı</h2>
    <table>
        <tr>
            <th>Pazartesi</th>
            <th>Salı</th>
            <th>Çarşamba</th>
            <th>Perşembe</th>
            <th>Cuma</th>
        </tr>
        <tr>
            <td>Matematik</td>
            <td>Türkçe</td>
            <td>Fen</td>
            <td>İngilizce</td>
            <td>Beden</td>
        </tr>
        <tr>
            <td>Tarih</td>
            <td>Coğrafya</td>
            <td>Matematik</td>
            <td>Türkçe</td>
            <td>Müzik</td>
        </tr>
        <tr>
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
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: bold;
            text-transform: uppercase;
            font-size: 0.9em;
            letter-spacing: 1px;
        }
        
        td {
            padding: 12px 15px;
            border-bottom: 1px solid #ddd;
        }
        
        tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        
        tr:hover {
            background-color: #e8f4f8;
            transition: background-color 0.3s;
        }
        
        .highlight {
            background-color: #fff3cd !important;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Ürün Kataloğu</h1>
    
    <table>
        <tr>
            <th>Ürün Kodu</th>
            <th>Ürün Adı</th>
            <th>Kategori</th>
            <th>Fiyat</th>
            <th>Stok</th>
            <th>Durum</th>
        </tr>
        <tr>
            <td>PRD001</td>
            <td>Laptop Dell XPS</td>
            <td>Elektronik</td>
            <td>25.000 TL</td>
            <td>15</td>
            <td>Stokta</td>
        </tr>
        <tr>
            <td>PRD002</td>
            <td>iPhone 15 Pro</td>
            <td>Telefon</td>
            <td>45.000 TL</td>
            <td>8</td>
            <td>Stokta</td>
        </tr>
        <tr class="highlight">
            <td>PRD003</td>
            <td>Samsung Galaxy Tab</td>
            <td>Tablet</td>
            <td>12.000 TL</td>
            <td>0</td>
            <td>Tükendi</td>
        </tr>
        <tr>
            <td>PRD004</td>
            <td>Logitech Mouse</td>
            <td>Aksesuar</td>
            <td>500 TL</td>
            <td>50</td>
            <td>Stokta</td>
        </tr>
        <tr>
            <td>PRD005</td>
            <td>Mechanical Keyboard</td>
            <td>Aksesuar</td>
            <td>2.500 TL</td>
            <td>20</td>
            <td>Stokta</td>
        </tr>
    </table>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: Tablolar sadece veri gösterimi için kullanılmalıdır, düzen amaçlı kullanılmamalıdır.

2. **Erişilebilirlik**: Tablolar için `<caption>` ve `scope` özellikleri kullanılmalıdır.

3. **Stil**: Tablo stilleri **CSS** ile özelleştirilebilir.

4. **Responsive**: Büyük tablolar mobil cihazlarda sorun yaratabilir, responsive tasarım gerekebilir.

5. **border-collapse**: Tablo kenarlıkları için `border-collapse: collapse;` kullanılmalıdır.

## 🎯 İyi Pratikler

- Tabloları sadece veri gösterimi için kullanın
- `<th>` etiketlerini başlıklar için kullanın
- Tablo stillerini **CSS** ile özelleştirin
- Erişilebilirlik için `<caption>` ekleyin
- Responsive tasarım için düşünün
- Hover efektleri ile kullanıcı deneyimini artırın
- Zebra striping (çizgili satırlar) ile okunabilirliği artırın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


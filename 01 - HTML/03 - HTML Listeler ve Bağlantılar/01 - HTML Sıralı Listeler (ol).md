# 🔢 HTML SIRALI LİSTELER (ol)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) sıralı listeler, numaralandırılmış öğeleri göstermek için kullanılır. Sıralı listeler `<ol>` (ordered list) etiketi ile oluşturulur ve her liste öğesi `<li>` (list item) etiketi ile tanımlanır.

## 📋 Sıralı Liste Yapısı

### `<ol>...</ol>`

Sıralı liste kapsayıcısı. İçinde `<li>` etiketleri bulunur.

### `<li>...</li>`

Liste öğesi. Her `<li>` etiketi bir liste maddesini temsil eder.

**Temel kullanım:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sıralı Liste Örneği</title>
</head>
<body>
    <ol>
        <li>İlk öğe</li>
        <li>İkinci öğe</li>
        <li>Üçüncü öğe</li>
    </ol>
</body>
</html>
```

## 📋 Sıralı Liste Özellikleri

### `type` Özelliği

Liste numaralandırma tipini belirler.

| Değer | Açıklama | Örnek |
| :---- | :------- | :---- |
| `1` | Sayılar (varsayılan) | 1, 2, 3, 4 |
| `A` | Büyük harfler | A, B, C, D |
| `a` | Küçük harfler | a, b, c, d |
| `I` | Büyük Roma rakamları | I, II, III, IV |
| `i` | Küçük Roma rakamları | i, ii, iii, iv |

### `start` Özelliği

Liste numaralandırmasının başlangıç değerini belirler.

### `reversed` Özelliği

Liste numaralandırmasını tersine çevirir (büyükten küçüğe).

## 💡 Kullanım Örnekleri

### Temel Sıralı Liste

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Sıralı Liste</title>
</head>
<body>
    <h2>Yapılacaklar Listesi</h2>
    <ol>
        <li>HTML öğren</li>
        <li>CSS öğren</li>
        <li>JavaScript öğren</li>
        <li>Proje yap</li>
    </ol>
</body>
</html>
```

### Farklı Numaralandırma Tipleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Farklı Numaralandırma Tipleri</title>
    <style>
        ol {
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h2>Sayılar (varsayılan)</h2>
    <ol type="1">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ol>
    
    <h2>Büyük Harfler</h2>
    <ol type="A">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ol>
    
    <h2>Küçük Harfler</h2>
    <ol type="a">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
    </ol>
    
    <h2>Büyük Roma Rakamları</h2>
    <ol type="I">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
        <li>Dördüncü</li>
    </ol>
    
    <h2>Küçük Roma Rakamları</h2>
    <ol type="i">
        <li>Birinci</li>
        <li>İkinci</li>
        <li>Üçüncü</li>
        <li>Dördüncü</li>
    </ol>
</body>
</html>
```

### start Özelliği ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>start Özelliği</title>
</head>
<body>
    <h2>5'ten Başlayan Liste</h2>
    <ol start="5">
        <li>Beşinci</li>
        <li>Altıncı</li>
        <li>Yedinci</li>
        <li>Sekizinci</li>
    </ol>
    
    <h2>C'den Başlayan Liste</h2>
    <ol type="A" start="3">
        <li>Üçüncü</li>
        <li>Dördüncü</li>
        <li>Beşinci</li>
    </ol>
</body>
</html>
```

### reversed Özelliği ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>reversed Özelliği</title>
</head>
<body>
    <h2>Tersine Sıralı Liste</h2>
    <ol reversed>
        <li>Dördüncü</li>
        <li>Üçüncü</li>
        <li>İkinci</li>
        <li>Birinci</li>
    </ol>
    
    <h2>10'dan Geriye Sayım</h2>
    <ol reversed start="10">
        <li>On</li>
        <li>Dokuz</li>
        <li>Sekiz</li>
        <li>Yedi</li>
    </ol>
</body>
</html>
```

### İç İçe Sıralı Listeler

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>İç İçe Sıralı Listeler</title>
    <style>
        ol {
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <h2>İç İçe Liste Örneği</h2>
    <ol>
        <li>Birinci Bölüm
            <ol>
                <li>Alt başlık 1.1</li>
                <li>Alt başlık 1.2</li>
                <li>Alt başlık 1.3</li>
            </ol>
        </li>
        <li>İkinci Bölüm
            <ol>
                <li>Alt başlık 2.1</li>
                <li>Alt başlık 2.2</li>
            </ol>
        </li>
        <li>Üçüncü Bölüm
            <ol>
                <li>Alt başlık 3.1</li>
                <li>Alt başlık 3.2</li>
                <li>Alt başlık 3.3</li>
                <li>Alt başlık 3.4</li>
            </ol>
        </li>
    </ol>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Sıralı Liste Örneği</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        ol {
            margin: 15px 0;
            padding-left: 30px;
        }
        
        li {
            margin: 5px 0;
        }
        
        .recipe {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h1>Kek Tarifi</h1>
    
    <div class="recipe">
        <h2>Malzemeler</h2>
        <ol>
            <li>3 yumurta</li>
            <li>1 su bardağı şeker</li>
            <li>1 su bardağı süt</li>
            <li>Yarım su bardağı sıvı yağ</li>
            <li>2 su bardağı un</li>
            <li>1 paket kabartma tozu</li>
            <li>1 paket vanilya</li>
        </ol>
    </div>
    
    <div class="recipe">
        <h2>Yapılışı</h2>
        <ol>
            <li>Yumurtaları ve şekeri köpürene kadar çırpın</li>
            <li>Süt ve sıvı yağı ekleyin</li>
            <li>Un, kabartma tozu ve vanilyayı ekleyin
                <ol type="a">
                    <li>Unu elekten geçirin</li>
                    <li>Kabartma tozu ile karıştırın</li>
                    <li>Yavaşça karışıma ekleyin</li>
                </ol>
            </li>
            <li>Karışımı yağlanmış kalıba dökün</li>
            <li>180°C fırında 30-35 dakika pişirin</li>
        </ol>
    </div>
    
    <h2>Önem Sırası</h2>
    <ol type="I">
        <li>Fırın sıcaklığı</li>
        <li>Pişirme süresi</li>
        <li>Malzeme ölçüleri</li>
        <li>Karıştırma tekniği</li>
    </ol>
</body>
</html>
```

### CSS ile Özelleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>CSS ile Özelleştirme</title>
    <style>
        .custom-list {
            list-style-type: none;
            counter-reset: item;
            padding-left: 0;
        }
        
        .custom-list li {
            counter-increment: item;
            margin: 10px 0;
            padding-left: 30px;
            position: relative;
        }
        
        .custom-list li::before {
            content: counter(item);
            position: absolute;
            left: 0;
            background-color: #3498db;
            color: white;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }
        
        .custom-list li:nth-child(odd)::before {
            background-color: #e74c3c;
        }
    </style>
</head>
<body>
    <h2>Özel Stil Sıralı Liste</h2>
    <ol class="custom-list">
        <li>Birinci öğe</li>
        <li>İkinci öğe</li>
        <li>Üçüncü öğe</li>
        <li>Dördüncü öğe</li>
        <li>Beşinci öğe</li>
    </ol>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: Sıralı listeler, sıralama önemli olduğunda kullanılmalıdır.

2. **CSS Stil**: Liste görünümü **CSS** ile tamamen özelleştirilebilir.

3. **Erişilebilirlik**: Ekran okuyucular liste yapısını anlar ve kullanıcıya sunar.

4. **İç İçe Listeler**: Listeler iç içe kullanılabilir, farklı numaralandırma tipleri kullanılabilir.

5. **value Özelliği**: `<li>` etiketinde `value` özelliği ile öğenin numarası değiştirilebilir.

## 🎯 İyi Pratikler

- Sıralama önemli olduğunda sıralı listeler kullanın
- İç içe listeler için farklı numaralandırma tipleri kullanın
- Liste stillerini **CSS** ile özelleştirin
- Anlamsal HTML kullanarak erişilebilirliği artırın
- Gereksiz yere sıralı liste kullanmayın, sırasız liste yeterliyse `<ul>` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


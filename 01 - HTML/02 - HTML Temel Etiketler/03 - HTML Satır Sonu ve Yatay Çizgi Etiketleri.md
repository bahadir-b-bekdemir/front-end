# ➖ HTML SATIR SONU VE YATAY ÇİZGİ ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) satır sonu eklemek ve içeriği ayırmak için kullanılan etiketler bulunmaktadır.

## 📋 Satır Sonu Etiketi

### `<br>` veya `<br/>`

Satır sonu etiketi, metin içinde yeni bir satıra geçmek için kullanılır. Bu etiket kapatılmaz (self-closing tag).

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Satır Sonu Örneği</title>
</head>
<body>
    <p>Bu bir satırdır.<br>Bu yeni bir satırdır.</p>
    
    <p>Adres bilgisi:<br>
    İstanbul Caddesi<br>
    No: 123<br>
    Ankara</p>
</body>
</html>
```

### Şiir veya Adres Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Şiir Örneği</title>
</head>
<body>
    <h2>Şiir Örneği</h2>
    <p>
        Gül bahçesinde gezerken<br>
        Bir kuş gördüm şarkı söylerken<br>
        Rengarenk çiçekler arasında<br>
        Mutluluk dolu bir dünyada
    </p>
    
    <h2>İletişim Bilgileri</h2>
    <p>
        Firma Adı: ABC Şirketi<br>
        Adres: İstanbul Caddesi<br>
        No: 123, Kat: 5<br>
        Şehir: Ankara<br>
        Posta Kodu: 06100
    </p>
</body>
</html>
```

## 📋 Yatay Çizgi Etiketi

### `<hr>` veya `<hr/>`

Yatay çizgi etiketi, içeriği görsel olarak ayırmak için kullanılır. Bu etiket kapatılmaz (self-closing tag).

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Yatay Çizgi Örneği</title>
</head>
<body>
    <h1>Bölüm 1</h1>
    <p>Bu bölümün içeriği burada yer alır.</p>
    
    <hr>
    
    <h1>Bölüm 2</h1>
    <p>Bu bölümün içeriği burada yer alır.</p>
    
    <hr>
    
    <h1>Bölüm 3</h1>
    <p>Bu bölümün içeriği burada yer alır.</p>
</body>
</html>
```

### Stil ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Stil ile Yatay Çizgi</title>
    <style>
        hr {
            border: none;
            border-top: 3px solid #3498db;
            margin: 20px 0;
        }
        
        .dotted {
            border-top: 2px dotted #e74c3c;
        }
        
        .dashed {
            border-top: 2px dashed #2ecc71;
        }
    </style>
</head>
<body>
    <h2>Farklı Yatay Çizgi Stilleri</h2>
    
    <p>Varsayılan yatay çizgi:</p>
    <hr>
    
    <p>Mavi kalın çizgi:</p>
    <hr style="border-top: 3px solid #3498db;">
    
    <p>Noktalı çizgi:</p>
    <hr class="dotted">
    
    <p>Kesikli çizgi:</p>
    <hr class="dashed">
</body>
</html>
```

## 💡 Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Satır Sonu ve Yatay Çizgi Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        hr {
            margin: 30px 0;
            border: none;
            border-top: 2px solid #ddd;
        }
        
        .section {
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h1>Satır Sonu ve Yatay Çizgi Kullanımı</h1>
    
    <div class="section">
        <h2>Satır Sonu Örnekleri</h2>
        
        <h3>Adres Bilgisi</h3>
        <p>
            ABC Şirketi<br>
            İstanbul Caddesi, No: 123<br>
            Çankaya, Ankara<br>
            Posta Kodu: 06100
        </p>
        
        <h3>Şiir Örneği</h3>
        <p>
            Doğa güzeldir,<br>
            Çiçekler açar,<br>
            Kuşlar öter,<br>
            Hayat devam eder.
        </p>
        
        <h3>Liste Benzeri Kullanım</h3>
        <p>
            İsim: Ahmet Yılmaz<br>
            Yaş: 25<br>
            Meslek: Yazılım Geliştirici<br>
            Şehir: İstanbul
        </p>
    </div>
    
    <hr>
    
    <div class="section">
        <h2>Yatay Çizgi Örnekleri</h2>
        
        <h3>Bölüm Ayırıcı</h3>
        <p>Bu bölümün içeriği burada yer alır. Yatay çizgi ile diğer bölümden ayrılır.</p>
        
        <hr>
        
        <h3>İkinci Bölüm</h3>
        <p>Bu ikinci bölümün içeriği burada yer alır.</p>
        
        <hr>
        
        <h3>Üçüncü Bölüm</h3>
        <p>Bu üçüncü bölümün içeriği burada yer alır.</p>
    </div>
    
    <hr>
    
    <div class="section">
        <h2>Kombine Kullanım</h2>
        <p>
            Bu paragraf içinde satır sonu kullanılıyor:<br>
            İlk satır<br>
            İkinci satır<br>
            Üçüncü satır
        </p>
        
        <hr>
        
        <p>
            Yatay çizgiden sonra yeni bir bölüm başlıyor.<br>
            Bu bölümde de satır sonları kullanılabilir.
        </p>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Self-Closing Tags**: Hem `<br>` hem de `<br/>` kullanımı geçerlidir. **XHTML**'de `<br/>` zorunludur, **HTML5**'te her ikisi de kabul edilir.

2. **Paragraf vs Satır Sonu**: Paragraflar arasında boşluk bırakır, satır sonu sadece yeni satıra geçer. Paragraflar anlamsal olarak daha önemlidir.

3. **Yatay Çizgi Stili**: Yatay çizginin görünümü **CSS** ile özelleştirilebilir.

4. **Erişilebilirlik**: Ekran okuyucular `<hr>` etiketini bölüm ayırıcı olarak algılar.

## 🎯 İyi Pratikler

- Satır sonu için `<br>` etiketini sadece gerekli yerlerde kullanın
- Paragraflar arasında boşluk istiyorsanız `<p>` etiketlerini kullanın
- İçeriği görsel olarak ayırmak için `<hr>` etiketini kullanın
- Yatay çizginin stilini **CSS** ile özelleştirin
- Aşırı `<br>` kullanımından kaçının, bunun yerine **CSS** ile boşluk ayarlayın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


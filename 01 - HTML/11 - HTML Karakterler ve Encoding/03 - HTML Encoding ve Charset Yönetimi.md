# 🔤 HTML ENCODING VE CHARSET YÖNETİMİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) karakter encoding, metinlerin doğru şekilde görüntülenmesi için kritik öneme sahiptir.

## 📋 Encoding Türleri

| Encoding | Açıklama | Kullanım |
| :------- | :------- | :------- |
| UTF-8 | Evrensel karakter seti | Önerilen, tüm dilleri destekler |
| ISO-8859-1 | Latin-1 | Eski standart |
| Windows-1252 | Windows Latin | Windows sistemleri |

## 💡 Kullanım Örnekleri

### UTF-8 Encoding (Önerilen)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>UTF-8 Encoding</title>
</head>
<body>
    <h1>Merhaba Dünya</h1>
    <p>Türkçe karakterler: ğ, ü, ş, ı, ö, ç</p>
    <p>Özel karakterler: ©, ®, ™, €, £, ¥</p>
    <p>Emoji: 😀 🎉 🚀</p>
</body>
</html>
```

### HTTP Header ile Encoding

```html
<!-- Server tarafında Content-Type header -->
Content-Type: text/html; charset=UTF-8
```

### XML Declaration ile Encoding

```html
<?xml version="1.0" encoding="UTF-8"?>
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>XML Declaration</title>
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### Farklı Diller için Encoding

```html
<!doctype html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>Arabic Text</title>
</head>
<body>
    <p>النص العربي</p>
</body>
</html>
```

```html
<!doctype html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>Chinese Text</title>
</head>
<body>
    <p>中文文本</p>
</body>
</html>
```

### BOM (Byte Order Mark) ile Encoding

```html
<!-- UTF-8 BOM ile kaydedilmiş dosya -->
<!-- BOM genellikle otomatik eklenir -->
```

### Form Encoding

```html
<form action="submit.php" method="post" accept-charset="UTF-8">
    <input type="text" name="name" placeholder="İsim">
    <button type="submit">Gönder</button>
</form>
```

### Link Encoding

```html
<body>
    <!-- URL encoding -->
    <a href="page.html?name=Ahmet%20Yılmaz">Bağlantı</a>
    
    <!-- JavaScript ile encoding -->
    <script>
        const url = encodeURIComponent('Ahmet Yılmaz');
        console.log(url); // Ahmet%20Y%C4%B1lmaz
    </script>
</body>
```

## 🎯 Önemli Notlar

- `<meta charset="UTF-8">` her zaman `<head>` içinde ilk meta etiketi olmalıdır
- UTF-8 tüm dilleri ve özel karakterleri destekler
- Encoding belirtilmezse tarayıcı varsayılan encoding kullanır
- HTTP header ve meta charset aynı olmalıdır
- Form gönderimlerinde `accept-charset` kullanılabilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


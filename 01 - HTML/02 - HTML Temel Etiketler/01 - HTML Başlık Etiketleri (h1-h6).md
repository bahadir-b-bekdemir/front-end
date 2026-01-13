# 📝 HTML BAŞLIK ETİKETLERİ (h1-h6)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) başlıklar için kullanılan etiketler **`<h1>`** ile **`<h6>`** arasındadır. Bu etiketler sayfa içeriğinin hiyerarşik yapısını oluşturur ve **SEO** (Search Engine Optimization) (arama motoru optimizasyonu) açısından önemlidir.

## 📋 Başlık Etiketleri

| Etiket | Açıklama | Önem Derecesi |
| :----- | :------- | :------------ |
| `<h1>` | En büyük ve en önemli başlık | 1 (En Yüksek) |
| `<h2>` | İkinci seviye başlık | 2 |
| `<h3>` | Üçüncü seviye başlık | 3 |
| `<h4>` | Dördüncü seviye başlık | 4 |
| `<h5>` | Beşinci seviye başlık | 5 |
| `<h6>` | En küçük ve en az önemli başlık | 6 (En Düşük) |

## 💡 Kullanım Örnekleri

### Temel Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Başlık Etiketleri Örneği</title>
</head>
<body>
    <h1>Ana Başlık</h1>
    <h2>Alt Başlık 1</h2>
    <h3>Alt Başlık 1.1</h3>
    <h4>Alt Başlık 1.1.1</h4>
    <h5>Alt Başlık 1.1.1.1</h5>
    <h6>Alt Başlık 1.1.1.1.1</h6>
</body>
</html>
```

### Hiyerarşik Yapı Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Makale Yapısı</title>
</head>
<body>
    <h1>Web Geliştirme Rehberi</h1>
    
    <h2>HTML Nedir?</h2>
    <p>HTML, web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir.</p>
    
    <h2>CSS Nedir?</h2>
    <p>CSS, web sayfalarının görsel tasarımını yapmak için kullanılan bir stil dilidir.</p>
    
    <h3>CSS Seçicileri</h3>
    <p>CSS seçicileri, stillerin hangi elementlere uygulanacağını belirler.</p>
    
    <h3>CSS Özellikleri</h3>
    <p>CSS özellikleri, elementlerin görsel özelliklerini tanımlar.</p>
    
    <h2>JavaScript Nedir?</h2>
    <p>JavaScript, web sayfalarına etkileşim eklemek için kullanılan bir programlama dilidir.</p>
</body>
</html>
```

### Stil ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Stil ile Başlık</title>
    <style>
        h1 {
            color: #2c3e50;
            text-align: center;
            font-family: Arial, sans-serif;
        }
        h2 {
            color: #3498db;
            border-bottom: 2px solid #3498db;
            padding-bottom: 10px;
        }
    </style>
</head>
<body>
    <h1>Stil Uygulanmış Ana Başlık</h1>
    <h2>Stil Uygulanmış Alt Başlık</h2>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Hiyerarşi**: Başlık etiketleri hiyerarşik olarak kullanılmalıdır. Örneğin, `<h3>` etiketinden önce `<h2>` etiketi kullanılmalıdır.

2. **SEO**: Arama motorları başlık etiketlerini içeriğin önemini belirlemek için kullanır. Her sayfada genellikle bir tane `<h1>` etiketi bulunmalıdır.

3. **Erişilebilirlik**: Ekran okuyucular başlık etiketlerini kullanarak sayfa yapısını anlar ve kullanıcıya sunar.

4. **Görsel Boyut**: Başlık etiketleri varsayılan olarak farklı boyutlarda görüntülenir, ancak **CSS** ile bu boyutlar değiştirilebilir.

## 🎯 İyi Pratikler

- Her sayfada sadece bir `<h1>` etiketi kullanın
- Başlık hiyerarşisini atlamayın (örn: h1'den sonra h3 kullanmayın)
- Başlıkları içeriğin yapısını yansıtacak şekilde kullanın
- Başlıkları sadece görsel amaçlı değil, anlamsal amaçlı kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🌐 HTML IFRAME VE EMBED

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) başka web sayfalarını veya içerikleri sayfa içine yerleştirmek için `<iframe>` ve `<embed>` etiketleri kullanılır.

## 📋 iframe Etiketi

### `<iframe>...</iframe>`

Başka bir web sayfasını veya içeriği mevcut sayfa içine yerleştirir.

**Temel kullanım:**
```html
<iframe src="https://www.example.com"></iframe>
```

## 📋 iframe Özellikleri

### `src` Özelliği

Yerleştirilecek sayfanın URL'si. Zorunludur.

### `width` ve `height` Özellikleri

iframe'in genişlik ve yüksekliği.

### `frameborder` Özelliği

Kenarlık gösterilip gösterilmeyeceği (0 veya 1).

### `allowfullscreen` Özelliği

Tam ekran moduna izin verir.

### `sandbox` Özelliği

Güvenlik için iframe'in yeteneklerini kısıtlar.

### `loading` Özelliği

Yükleme davranışını belirler (`lazy`, `eager`).

## 📋 embed Etiketi

### `<embed>`

Harici içerik veya eklentileri yerleştirmek için kullanılır.

## 💡 Kullanım Örnekleri

### Temel iframe Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel iframe</title>
</head>
<body>
    <h2>Yerleştirilmiş Sayfa</h2>
    <iframe src="https://www.example.com" width="800" height="600"></iframe>
</body>
</html>
```

### YouTube Video Yerleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>YouTube Video</title>
    <style>
        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 */
            height: 0;
            overflow: hidden;
            max-width: 100%;
        }
        
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <h2>YouTube Video</h2>
    <div class="video-container">
        <iframe 
            src="https://www.youtube.com/embed/VIDEO_ID" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen>
        </iframe>
    </div>
</body>
</html>
```

### Google Maps Yerleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Google Maps</title>
    <style>
        .map-container {
            width: 100%;
            height: 450px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>
    <h2>Harita</h2>
    <div class="map-container">
        <iframe 
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3000!2d32.8597!3d39.9334!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMznCsDU2JzAwLjQiTiAzMsKwNTEnMzQuOSJF!5e0!3m2!1str!2str!4v1234567890"
            allowfullscreen="" 
            loading="lazy">
        </iframe>
    </div>
</body>
</html>
```

### PDF Yerleştirme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>PDF Yerleştirme</title>
    <style>
        .pdf-container {
            width: 100%;
            height: 600px;
            border: 1px solid #ddd;
        }
        
        .pdf-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>
    <h2>PDF Doküman</h2>
    <div class="pdf-container">
        <iframe src="dokuman.pdf"></iframe>
    </div>
</body>
</html>
```

### Sandbox ile Güvenli iframe

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sandbox iframe</title>
</head>
<body>
    <h2>Güvenli iframe</h2>
    <iframe 
        src="https://www.example.com" 
        width="800" 
        height="600"
        sandbox="allow-scripts allow-same-origin">
    </iframe>
    
    <p>Sandbox özelliği ile iframe'in yetenekleri kısıtlanmıştır.</p>
</body>
</html>
```

### Lazy Loading iframe

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Lazy Loading iframe</title>
</head>
<body>
    <h2>Hemen Yüklenen iframe</h2>
    <iframe src="https://www.example.com" width="800" height="600" loading="eager"></iframe>
    
    <div style="height: 1000px;">
        <p>Scroll yapmak için alan</p>
    </div>
    
    <h2>Gecikmeli Yüklenen iframe</h2>
    <iframe src="https://www.example.com" width="800" height="600" loading="lazy"></iframe>
</body>
</html>
```

### embed Etiketi ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>embed Etiketi</title>
</head>
<body>
    <h2>Flash İçeriği (Eski)</h2>
    <embed src="animasyon.swf" width="800" height="600" type="application/x-shockwave-flash">
    
    <h2>PDF Dosyası</h2>
    <embed src="dokuman.pdf" width="800" height="600" type="application/pdf">
</body>
</html>
```

### Çoklu iframe Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu iframe</title>
    <style>
        .iframe-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        
        .iframe-item {
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .iframe-item h3 {
            padding: 10px;
            background-color: #2c3e50;
            color: white;
            margin: 0;
        }
        
        .iframe-item iframe {
            width: 100%;
            height: 300px;
            border: none;
        }
    </style>
</head>
<body>
    <h1>Yerleştirilmiş İçerikler</h1>
    
    <div class="iframe-grid">
        <div class="iframe-item">
            <h3>YouTube Video</h3>
            <iframe 
                src="https://www.youtube.com/embed/VIDEO_ID" 
                allowfullscreen>
            </iframe>
        </div>
        
        <div class="iframe-item">
            <h3>Google Maps</h3>
            <iframe 
                src="https://www.google.com/maps/embed?pb=..." 
                allowfullscreen>
            </iframe>
        </div>
        
        <div class="iframe-item">
            <h3>Harici Sayfa</h3>
            <iframe src="https://www.example.com"></iframe>
        </div>
    </div>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı iframe Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .iframe-section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .responsive-iframe {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 */
            height: 0;
            overflow: hidden;
            max-width: 100%;
        }
        
        .responsive-iframe iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        
        .info {
            background-color: #e8f4f8;
            padding: 15px;
            border-left: 4px solid #3498db;
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <h1>iframe ve Embed Örnekleri</h1>
    
    <div class="iframe-section">
        <h2>YouTube Video (Responsive)</h2>
        <div class="responsive-iframe">
            <iframe 
                src="https://www.youtube.com/embed/VIDEO_ID" 
                frameborder="0" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                allowfullscreen>
            </iframe>
        </div>
        <div class="info">
            <p>Responsive tasarım ile tüm ekran boyutlarına uyum sağlar.</p>
        </div>
    </div>
    
    <div class="iframe-section">
        <h2>Google Maps</h2>
        <iframe 
            src="https://www.google.com/maps/embed?pb=..." 
            width="100%" 
            height="450" 
            style="border:0;" 
            allowfullscreen="" 
            loading="lazy">
        </iframe>
        <div class="info">
            <p>Google Maps haritası yerleştirilmiştir.</p>
        </div>
    </div>
    
    <div class="iframe-section">
        <h2>PDF Doküman</h2>
        <iframe 
            src="dokuman.pdf" 
            width="100%" 
            height="600" 
            style="border: 1px solid #ddd;">
        </iframe>
        <div class="info">
            <p>PDF dosyası doğrudan sayfa içinde görüntülenir.</p>
        </div>
    </div>
    
    <div class="iframe-section">
        <h2>Güvenli iframe (Sandbox)</h2>
        <iframe 
            src="https://www.example.com" 
            width="100%" 
            height="400"
            sandbox="allow-scripts allow-same-origin"
            style="border: 1px solid #ddd;">
        </iframe>
        <div class="info">
            <p>Sandbox özelliği ile güvenlik artırılmıştır.</p>
        </div>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Güvenlik**: iframe'ler güvenlik riski oluşturabilir. `sandbox` özelliği kullanın.

2. **X-Frame-Options**: Bazı siteler iframe içinde gösterilmeyi engeller (X-Frame-Options header).

3. **Performans**: iframe'ler sayfa yükleme hızını etkileyebilir. `loading="lazy"` kullanın.

4. **Responsive**: iframe'ler için responsive tasarım için padding-bottom tekniği kullanın.

5. **Erişilebilirlik**: iframe'ler için `title` özelliği ekleyin.

6. **embed vs iframe**: Modern web'de `<iframe>` tercih edilir, `<embed>` eski teknolojiler için kullanılır.

## 🎯 İyi Pratikler

- Güvenlik için `sandbox` özelliği kullanın
- Responsive tasarım için padding-bottom tekniğini kullanın
- Performans için `loading="lazy"` kullanın
- Erişilebilirlik için `title` özelliği ekleyin
- YouTube ve Google Maps gibi güvenilir kaynaklar kullanın
- X-Frame-Options engellerini kontrol edin
- iframe içeriğinin mobil uyumluluğunu test edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


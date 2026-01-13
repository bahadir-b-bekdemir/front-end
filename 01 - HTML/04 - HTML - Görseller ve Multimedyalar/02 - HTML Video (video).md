# 🎥 HTML VİDEO (video)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) video oynatmak için `<video>` etiketi kullanılır. HTML5 ile gelen bu etiket, tarayıcıda video oynatmayı sağlar.

## 📋 Video Etiketi Yapısı

### `<video>...</video>`

Video oynatıcı etiketi. İçinde `<source>` etiketleri veya `src` özelliği ile video dosyası belirtilir.

**Temel kullanım:**
```html
<video src="video.mp4" controls></video>
```

## 📋 Video Özellikleri

### `src` Özelliği

Video dosyasının yolu veya URL'si.

### `controls` Özelliği

Video kontrollerini (oynat, duraklat, ses vb.) gösterir.

### `autoplay` Özelliği

Videoyu otomatik olarak oynatır (tarayıcılar genellikle sesli otomatik oynatmayı engeller).

### `loop` Özelliği

Videoyu döngüde oynatır.

### `muted` Özelliği

Videoyu sessiz başlatır.

### `poster` Özelliği

Video yüklenmeden önce gösterilecek resim.

### `width` ve `height` Özellikleri

Video oynatıcının boyutları.

### `preload` Özelliği

Video yükleme davranışını belirler (`none`, `metadata`, `auto`).

## 💡 Kullanım Örnekleri

### Temel Video Oynatma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Video Oynatma</title>
</head>
<body>
    <h2>Video Örneği</h2>
    <video src="video.mp4" controls width="640" height="360">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
</body>
</html>
```

### Çoklu Format Desteği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu Format Desteği</title>
</head>
<body>
    <h2>Çoklu Format Video</h2>
    <video controls width="640" height="360">
        <source src="video.mp4" type="video/mp4">
        <source src="video.webm" type="video/webm">
        <source src="video.ogg" type="video/ogg">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
</body>
</html>
```

### Otomatik Oynatma ve Döngü

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Otomatik Oynatma</title>
</head>
<body>
    <h2>Otomatik Oynatılan Video (Sessiz)</h2>
    <video src="video.mp4" autoplay muted loop width="640" height="360">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
    
    <p>Not: Otomatik oynatma genellikle sessiz modda çalışır.</p>
</body>
</html>
```

### Poster Resmi ile Video

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Poster Resmi</title>
</head>
<body>
    <h2>Poster Resimli Video</h2>
    <video src="video.mp4" controls poster="poster.jpg" width="640" height="360">
        Tarayıcınız video etiketini desteklemiyor.
    </video>
</body>
</html>
```

### Responsive Video

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Responsive Video</title>
    <style>
        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            height: 0;
            overflow: hidden;
            max-width: 100%;
        }
        
        .video-container video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <h2>Responsive Video</h2>
    <div class="video-container">
        <video src="video.mp4" controls>
            Tarayıcınız video etiketini desteklemiyor.
        </video>
    </div>
</body>
</html>
```

### Video Galerisi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Video Galerisi</title>
    <style>
        .video-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        
        .video-item {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 5px;
        }
        
        .video-item video {
            width: 100%;
            height: auto;
            border-radius: 5px;
        }
        
        .video-item h3 {
            margin-top: 10px;
            color: #2c3e50;
        }
    </style>
</head>
<body>
    <h1>Video Galerisi</h1>
    
    <div class="video-gallery">
        <div class="video-item">
            <video src="video1.mp4" controls poster="poster1.jpg">
                Tarayıcınız video etiketini desteklemiyor.
            </video>
            <h3>Video 1</h3>
        </div>
        
        <div class="video-item">
            <video src="video2.mp4" controls poster="poster2.jpg">
                Tarayıcınız video etiketini desteklemiyor.
            </video>
            <h3>Video 2</h3>
        </div>
        
        <div class="video-item">
            <video src="video3.mp4" controls poster="poster3.jpg">
                Tarayıcınız video etiketini desteklemiyor.
            </video>
            <h3>Video 3</h3>
        </div>
    </div>
</body>
</html>
```

### YouTube Video Yerleştirme (iframe)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>YouTube Video</title>
    <style>
        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 */
            height: 0;
            overflow: hidden;
            max-width: 100%;
        }
        
        .video-wrapper iframe {
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
    <div class="video-wrapper">
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

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Video Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .video-section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        video {
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .responsive-video {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            max-width: 100%;
        }
        
        .responsive-video video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <h1>Video Kullanım Örnekleri</h1>
    
    <div class="video-section">
        <h2>Kontrollü Video</h2>
        <video src="video.mp4" controls width="800" height="450">
            Tarayıcınız video etiketini desteklemiyor.
        </video>
    </div>
    
    <div class="video-section">
        <h2>Çoklu Format Desteği</h2>
        <video controls width="800" height="450">
            <source src="video.mp4" type="video/mp4">
            <source src="video.webm" type="video/webm">
            Tarayıcınız video etiketini desteklemiyor.
        </video>
    </div>
    
    <div class="video-section">
        <h2>Poster Resimli Video</h2>
        <video src="video.mp4" controls poster="poster.jpg" width="800" height="450">
            Tarayıcınız video etiketini desteklemiyor.
        </video>
    </div>
    
    <div class="video-section">
        <h2>Responsive Video</h2>
        <div class="responsive-video">
            <video src="video.mp4" controls>
                Tarayıcınız video etiketini desteklemiyor.
            </video>
        </div>
    </div>
    
    <div class="video-section">
        <h2>Otomatik Oynatma (Sessiz, Döngü)</h2>
        <video src="video.mp4" autoplay muted loop width="800" height="450">
            Tarayıcınız video etiketini desteklemiyor.
        </video>
        <p>Bu video otomatik olarak oynatılır, sessizdir ve döngüdedir.</p>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Video Formatları**: Yaygın formatlar: **MP4** (H.264), **WebM**, **OGG**. Tarayıcı uyumluluğu için çoklu format kullanın.

2. **Autoplay Politikası**: Modern tarayıcılar sesli otomatik oynatmayı engeller. `muted` özelliği ile sessiz otomatik oynatma mümkündür.

3. **Poster Resmi**: Video yüklenmeden önce gösterilecek resim için `poster` özelliği kullanılır.

4. **Responsive**: Video için responsive tasarım için padding-bottom tekniği kullanılır.

5. **Preload**: `preload="none"` ile video sadece kullanıcı tıkladığında yüklenir, performans için önemlidir.

6. **Erişilebilirlik**: Video içeriği için altyazı (`<track>`) eklenmelidir.

## 🎯 İyi Pratikler

- Çoklu format desteği sağlayın (MP4, WebM)
- Poster resmi kullanın
- Responsive tasarım için padding-bottom tekniğini kullanın
- Otomatik oynatma için `muted` kullanın
- Performans için `preload="none"` kullanın
- Altyazı ekleyin (`<track>` etiketi)
- Video dosyalarını optimize edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


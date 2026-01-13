# 🖼️ HTML RESİMLER (img)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) resimler `<img>` etiketi ile gösterilir. Bu etiket kapatılmaz (self-closing tag) ve `src` özelliği ile resmin yolu belirtilir.

## 📋 Resim Etiketi Yapısı

### `<img>`

Resim etiketi. Kapatılmaz ve `src` özelliği zorunludur.

**Temel kullanım:**
```html
<img src="resim.jpg" alt="Açıklama">
```

## 📋 Resim Özellikleri

### `src` Özelliği

Resmin dosya yolu veya URL'si. Zorunludur.

### `alt` Özelliği

Resmin alternatif metni. Erişilebilirlik ve **SEO** için önemlidir. Zorunludur.

### `width` ve `height` Özellikleri

Resmin genişlik ve yüksekliği (piksel cinsinden).

### `title` Özelliği

Fare ile üzerine gelindiğinde görüntülenecek başlık.

### `loading` Özelliği

Resmin yükleme davranışını belirler (`lazy`, `eager`).

## 💡 Kullanım Örnekleri

### Temel Resim Gösterimi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Resim Gösterimi</title>
</head>
<body>
    <h2>Doğa Resmi</h2>
    <img src="dogal.jpg" alt="Doğa manzarası">
    
    <h2>Şehir Resmi</h2>
    <img src="sehir.jpg" alt="Şehir manzarası">
</body>
</html>
```

### Boyutlandırma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Resim Boyutlandırma</title>
    <style>
        img {
            border: 2px solid #ddd;
            margin: 10px;
        }
    </style>
</head>
<body>
    <h2>Orijinal Boyut</h2>
    <img src="resim.jpg" alt="Orijinal resim">
    
    <h2>Belirtilen Boyut</h2>
    <img src="resim.jpg" alt="Küçük resim" width="300" height="200">
    
    <h2>CSS ile Boyutlandırma</h2>
    <img src="resim.jpg" alt="CSS ile boyutlandırılmış" style="width: 400px; height: auto;">
</body>
</html>
```

### Responsive Resimler

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Responsive Resimler</title>
    <style>
        .responsive-img {
            max-width: 100%;
            height: auto;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Responsive Resim</h2>
        <img src="resim.jpg" alt="Responsive resim" class="responsive-img">
        
        <p>Bu resim ekran boyutuna göre otomatik olarak ölçeklenir.</p>
    </div>
</body>
</html>
```

### Lazy Loading

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Lazy Loading</title>
</head>
<body>
    <h2>Hemen Yüklenen Resim</h2>
    <img src="resim1.jpg" alt="Hemen yüklenen" loading="eager">
    
    <h2>Gecikmeli Yüklenen Resim</h2>
    <img src="resim2.jpg" alt="Gecikmeli yüklenen" loading="lazy">
    
    <div style="height: 1000px;">
        <p>Bu alan scroll yapmak için eklenmiştir.</p>
    </div>
    
    <h2>Sayfa Sonundaki Resim</h2>
    <img src="resim3.jpg" alt="Sayfa sonu resmi" loading="lazy">
</body>
</html>
```

### Resim Bağlantıları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Resim Bağlantıları</title>
    <style>
        a img {
            border: 2px solid #3498db;
            transition: opacity 0.3s;
        }
        
        a:hover img {
            opacity: 0.8;
        }
    </style>
</head>
<body>
    <h2>Bağlantılı Resimler</h2>
    
    <p>
        <a href="https://www.example.com">
            <img src="logo.jpg" alt="Logo" width="200">
        </a>
    </p>
    
    <p>
        <a href="buyuk-resim.jpg" target="_blank">
            <img src="kucuk-resim.jpg" alt="Büyük resmi görmek için tıklayın" width="300">
        </a>
    </p>
</body>
</html>
```

### Figure ve Figcaption ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Figure ve Figcaption</title>
    <style>
        figure {
            margin: 20px 0;
            text-align: center;
        }
        
        figure img {
            max-width: 100%;
            height: auto;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        figcaption {
            margin-top: 10px;
            font-style: italic;
            color: #666;
        }
    </style>
</head>
<body>
    <article>
        <h1>Doğa Fotoğrafları</h1>
        
        <figure>
            <img src="dag.jpg" alt="Dağ manzarası">
            <figcaption>Yüksek dağlar ve bulutlar</figcaption>
        </figure>
        
        <figure>
            <img src="deniz.jpg" alt="Deniz manzarası">
            <figcaption>Mavi deniz ve gökyüzü</figcaption>
        </figure>
        
        <figure>
            <img src="orman.jpg" alt="Orman manzarası">
            <figcaption>Yeşil orman ve ağaçlar</figcaption>
        </figure>
    </article>
</body>
</html>
```

### Resim Galerisi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Resim Galerisi</title>
    <style>
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            padding: 20px;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .gallery-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.3s;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        .gallery-item figcaption {
            padding: 10px;
            background-color: #2c3e50;
            color: white;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Resim Galerisi</h1>
    
    <div class="gallery">
        <figure class="gallery-item">
            <img src="resim1.jpg" alt="Resim 1" loading="lazy">
            <figcaption>Resim 1</figcaption>
        </figure>
        
        <figure class="gallery-item">
            <img src="resim2.jpg" alt="Resim 2" loading="lazy">
            <figcaption>Resim 2</figcaption>
        </figure>
        
        <figure class="gallery-item">
            <img src="resim3.jpg" alt="Resim 3" loading="lazy">
            <figcaption>Resim 3</figcaption>
        </figure>
        
        <figure class="gallery-item">
            <img src="resim4.jpg" alt="Resim 4" loading="lazy">
            <figcaption>Resim 4</figcaption>
        </figure>
        
        <figure class="gallery-item">
            <img src="resim5.jpg" alt="Resim 5" loading="lazy">
            <figcaption>Resim 5</figcaption>
        </figure>
        
        <figure class="gallery-item">
            <img src="resim6.jpg" alt="Resim 6" loading="lazy">
            <figcaption>Resim 6</figcaption>
        </figure>
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
    <title>Kapsamlı Resim Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .image-section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .responsive-image {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .thumbnail {
            width: 150px;
            height: 150px;
            object-fit: cover;
            border-radius: 50%;
            border: 3px solid #3498db;
        }
        
        .banner {
            width: 100%;
            height: 300px;
            object-fit: cover;
        }
    </style>
</head>
<body>
    <h1>Resim Kullanım Örnekleri</h1>
    
    <div class="image-section">
        <h2>Profil Resmi</h2>
        <img src="profil.jpg" alt="Kullanıcı profil resmi" class="thumbnail">
        <p>Yuvarlak profil resmi örneği</p>
    </div>
    
    <div class="image-section">
        <h2>Banner Resmi</h2>
        <img src="banner.jpg" alt="Web sitesi banner'ı" class="banner">
    </div>
    
    <div class="image-section">
        <h2>Responsive Resim</h2>
        <img src="content.jpg" alt="İçerik resmi" class="responsive-image">
        <p>Bu resim tüm ekran boyutlarına uyum sağlar.</p>
    </div>
    
    <div class="image-section">
        <h2>Resim ile Açıklama</h2>
        <figure>
            <img src="ornek.jpg" alt="Örnek resim" class="responsive-image">
            <figcaption>Bu resim hakkında detaylı açıklama burada yer alır.</figcaption>
        </figure>
    </div>
    
    <div class="image-section">
        <h2>Lazy Loading Örneği</h2>
        <p>Aşağıdaki resimler sayfa kaydırıldığında yüklenecektir:</p>
        <img src="resim1.jpg" alt="Resim 1" loading="lazy" class="responsive-image">
        <img src="resim2.jpg" alt="Resim 2" loading="lazy" class="responsive-image">
        <img src="resim3.jpg" alt="Resim 3" loading="lazy" class="responsive-image">
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **alt Özelliği**: Her resim için mutlaka `alt` özelliği kullanılmalıdır. Erişilebilirlik ve **SEO** için kritiktir.

2. **Dosya Formatları**: Web için uygun formatlar: **JPEG** (fotoğraflar), **PNG** (şeffaflık gereken durumlar), **WebP** (modern tarayıcılar), **SVG** (vektör grafikler).

3. **Boyutlandırma**: `width` ve `height` özellikleri yerine **CSS** kullanılması önerilir.

4. **Lazy Loading**: Sayfa performansı için `loading="lazy"` kullanılmalıdır.

5. **Responsive**: Resimlerin `max-width: 100%` ve `height: auto` ile responsive yapılması önerilir.

6. **Figure/Figcaption**: Resimler için açıklama eklemek için `<figure>` ve `<figcaption>` kullanılmalıdır.

## 🎯 İyi Pratikler

- Her resim için `alt` özelliği kullanın
- Resimleri optimize edin (dosya boyutunu küçültün)
- Responsive tasarım için `max-width: 100%` kullanın
- Lazy loading ile performansı artırın
- Uygun dosya formatlarını seçin
- `figure` ve `figcaption` ile anlamsal HTML kullanın
- Resim boyutlarını **CSS** ile kontrol edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


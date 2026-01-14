# 🖼️ HTML PICTURE VE SOURCE ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) responsive resimler ve farklı ekran boyutları için farklı resimler göstermek için `<picture>` ve `<source>` etiketleri kullanılır.

## 📋 Picture Etiketi Yapısı

### `<picture>...</picture>`

Farklı kaynaklar ve koşullar için resim seçimi yapar. İçinde `<source>` ve `<img>` etiketleri bulunur.

### `<source>`

Farklı kaynakları ve medya sorgularını tanımlar.

**Temel kullanım:**
```html
<picture>
    <source srcset="buyuk-resim.jpg" media="(min-width: 800px)">
    <img src="kucuk-resim.jpg" alt="Resim">
</picture>
```

## 📋 Source Özellikleri

### `srcset` Özelliği

Resim kaynaklarının listesi. Farklı çözünürlükler için birden fazla kaynak belirtilebilir.

### `media` Özelliği

Medya sorgusu. Hangi ekran boyutunda hangi resmin gösterileceğini belirler.

### `type` Özelliği

Resim formatını belirtir (örneğin: `image/webp`, `image/avif`).

### `sizes` Özelliği

Resmin görüntüleneceği boyutları belirtir.

## 💡 Kullanım Örnekleri

### Responsive Resim (Farklı Boyutlar)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Responsive Resim</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h2>Responsive Resim</h2>
    <picture>
        <source srcset="resim-buyuk.jpg" media="(min-width: 1200px)">
        <source srcset="resim-orta.jpg" media="(min-width: 800px)">
        <img src="resim-kucuk.jpg" alt="Responsive resim">
    </picture>
</body>
</html>
```

### Modern Format Desteği (WebP, AVIF)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Modern Format Desteği</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h2>Modern Format Desteği</h2>
    <picture>
        <source srcset="resim.avif" type="image/avif">
        <source srcset="resim.webp" type="image/webp">
        <img src="resim.jpg" alt="Modern format resmi">
    </picture>
    <p>Tarayıcı desteklediği ilk formatı kullanacaktır.</p>
</body>
</html>
```

### Art Direction (Farklı Kırpılmış Resimler)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Art Direction</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h2>Art Direction Örneği</h2>
    <picture>
        <!-- Masaüstü için geniş resim -->
        <source srcset="genis-resim.jpg" media="(min-width: 1024px)">
        <!-- Tablet için orta resim -->
        <source srcset="orta-resim.jpg" media="(min-width: 768px)">
        <!-- Mobil için dar resim -->
        <img src="dar-resim.jpg" alt="Art direction resmi">
    </picture>
</body>
</html>
```

### Çoklu Çözünürlük Desteği (srcset)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu Çözünürlük</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h2>Çoklu Çözünürlük Desteği</h2>
    <picture>
        <source 
            srcset="resim-320w.jpg 320w,
                    resim-640w.jpg 640w,
                    resim-1024w.jpg 1024w,
                    resim-1920w.jpg 1920w"
            sizes="(max-width: 320px) 280px,
                   (max-width: 640px) 600px,
                   (max-width: 1024px) 980px,
                   1920px">
        <img src="resim-640w.jpg" alt="Çoklu çözünürlük resmi">
    </picture>
</body>
</html>
```

### Kombine Kullanım (Format + Boyut)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kombine Kullanım</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h2>Format ve Boyut Kombinasyonu</h2>
    <picture>
        <!-- Büyük ekranlar için WebP -->
        <source 
            srcset="resim-buyuk.webp" 
            type="image/webp" 
            media="(min-width: 1200px)">
        <!-- Orta ekranlar için WebP -->
        <source 
            srcset="resim-orta.webp" 
            type="image/webp" 
            media="(min-width: 800px)">
        <!-- Küçük ekranlar için WebP -->
        <source 
            srcset="resim-kucuk.webp" 
            type="image/webp">
        <!-- Fallback: JPEG -->
        <source 
            srcset="resim-buyuk.jpg" 
            media="(min-width: 1200px)">
        <source 
            srcset="resim-orta.jpg" 
            media="(min-width: 800px)">
        <img src="resim-kucuk.jpg" alt="Kombine resim">
    </picture>
</body>
</html>
```

### Banner Resmi Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Banner Resmi</title>
    <style>
        .banner {
            width: 100%;
            height: 400px;
            object-fit: cover;
        }
    </style>
</head>
<body>
    <h1>Web Sitesi</h1>
    <picture>
        <source 
            srcset="banner-mobil.jpg" 
            media="(max-width: 768px)">
        <source 
            srcset="banner-tablet.jpg" 
            media="(max-width: 1024px)">
        <img src="banner-masaustu.jpg" alt="Banner resmi" class="banner">
    </picture>
</body>
</html>
```

### Galeri Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Responsive Galeri</title>
    <style>
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            padding: 20px;
        }
        
        .gallery-item {
            overflow: hidden;
            border-radius: 5px;
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
    </style>
</head>
<body>
    <h1>Responsive Galeri</h1>
    <div class="gallery">
        <div class="gallery-item">
            <picture>
                <source srcset="resim1-buyuk.webp" type="image/webp" media="(min-width: 800px)">
                <img src="resim1-kucuk.jpg" alt="Resim 1" loading="lazy">
            </picture>
        </div>
        
        <div class="gallery-item">
            <picture>
                <source srcset="resim2-buyuk.webp" type="image/webp" media="(min-width: 800px)">
                <img src="resim2-kucuk.jpg" alt="Resim 2" loading="lazy">
            </picture>
        </div>
        
        <div class="gallery-item">
            <picture>
                <source srcset="resim3-buyuk.webp" type="image/webp" media="(min-width: 800px)">
                <img src="resim3-kucuk.jpg" alt="Resim 3" loading="lazy">
            </picture>
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
    <title>Kapsamlı Picture Örnekleri</title>
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
        
        picture img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
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
    <h1>Picture ve Source Etiketleri</h1>
    
    <div class="image-section">
        <h2>Responsive Resim (Farklı Boyutlar)</h2>
        <picture>
            <source srcset="resim-buyuk.jpg" media="(min-width: 1200px)">
            <source srcset="resim-orta.jpg" media="(min-width: 800px)">
            <img src="resim-kucuk.jpg" alt="Responsive resim">
        </picture>
        <div class="info">
            <p>Ekran boyutuna göre farklı boyutlarda resim gösterilir.</p>
        </div>
    </div>
    
    <div class="image-section">
        <h2>Modern Format Desteği</h2>
        <picture>
            <source srcset="resim.avif" type="image/avif">
            <source srcset="resim.webp" type="image/webp">
            <img src="resim.jpg" alt="Modern format resmi">
        </picture>
        <div class="info">
            <p>Tarayıcı desteklediği en modern formatı kullanır (AVIF > WebP > JPEG).</p>
        </div>
    </div>
    
    <div class="image-section">
        <h2>Kombine Kullanım</h2>
        <picture>
            <source 
                srcset="resim-buyuk.webp" 
                type="image/webp" 
                media="(min-width: 1200px)">
            <source 
                srcset="resim-orta.webp" 
                type="image/webp" 
                media="(min-width: 800px)">
            <source srcset="resim-buyuk.jpg" media="(min-width: 1200px)">
            <img src="resim-orta.jpg" alt="Kombine resim">
        </picture>
        <div class="info">
            <p>Hem format hem de boyut optimizasyonu birlikte kullanılmıştır.</p>
        </div>
    </div>
    
    <div class="image-section">
        <h2>Çoklu Çözünürlük (srcset)</h2>
        <picture>
            <source 
                srcset="resim-320w.webp 320w,
                        resim-640w.webp 640w,
                        resim-1024w.webp 1024w"
                sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 33vw"
                type="image/webp">
            <source 
                srcset="resim-320w.jpg 320w,
                        resim-640w.jpg 640w,
                        resim-1024w.jpg 1024w"
                sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 33vw">
            <img src="resim-640w.jpg" alt="Çoklu çözünürlük resmi">
        </picture>
        <div class="info">
            <p>Tarayıcı ekran boyutuna ve çözünürlüğe göre en uygun resmi seçer.</p>
        </div>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Fallback**: `<picture>` içinde mutlaka `<img>` etiketi bulunmalıdır (fallback için).

2. **Tarayıcı Desteği**: Modern tarayıcılar `<picture>` etiketini destekler.

3. **Performans**: Farklı ekran boyutları için farklı resimler kullanarak performans artırılır.

4. **Modern Formatlar**: WebP ve AVIF gibi modern formatlar daha küçük dosya boyutları sağlar.

5. **Art Direction**: Farklı ekran boyutları için farklı kırpılmış resimler kullanılabilir.

6. **srcset ve sizes**: Çoklu çözünürlük desteği için `srcset` ve `sizes` özellikleri kullanılır.

## 🎯 İyi Pratikler

- Modern formatları (WebP, AVIF) destekleyin
- Farklı ekran boyutları için farklı resimler kullanın
- Fallback için mutlaka `<img>` etiketi ekleyin
- `srcset` ve `sizes` ile çoklu çözünürlük desteği sağlayın
- Art direction için farklı kırpılmış resimler kullanın
- Performans için uygun resim boyutlarını seçin
- Lazy loading ile birlikte kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# ⚡ HTML PERFORMANS OPTİMİZASYONU

**HTML** performans optimizasyonu, web sayfalarının daha hızlı yüklenmesi ve daha iyi kullanıcı deneyimi sağlaması için yapılan optimizasyonlardır.

## 📋 Performans Optimizasyon Teknikleri

### Resim Optimizasyonu

- Lazy loading
- Responsive resimler
- Modern formatlar (WebP, AVIF)
- Uygun boyutlandırma

### CSS ve JavaScript

- Minification
- Async/Defer
- Critical CSS
- Code splitting

### Caching

- Browser caching
- CDN kullanımı
- Service Workers

### Diğer Teknikler

- Preconnect/Prefetch
- Resource hints
- Compression

## 💡 Kullanım Örnekleri

### Lazy Loading

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Lazy Loading</title>
</head>
<body>
    <h1>Lazy Loading Örneği</h1>
    
    <!-- Resim lazy loading -->
    <img src="resim1.jpg" alt="Resim 1" loading="lazy">
    
    <!-- iframe lazy loading -->
    <iframe 
        src="https://www.example.com" 
        loading="lazy"
        width="800" 
        height="600">
    </iframe>
    
    <!-- Video lazy loading -->
    <video src="video.mp4" controls loading="lazy"></video>
    
    <!-- Sayfa sonundaki resimler -->
    <div style="height: 2000px;">
        <p>Scroll yapmak için alan</p>
    </div>
    
    <img src="resim2.jpg" alt="Resim 2" loading="lazy">
    <img src="resim3.jpg" alt="Resim 3" loading="lazy">
</body>
</html>
```

### Responsive Resimler

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Resimler</title>
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h1>Responsive Resimler</h1>
    
    <!-- Picture element ile responsive -->
    <picture>
        <source srcset="resim-buyuk.webp" type="image/webp" media="(min-width: 1200px)">
        <source srcset="resim-orta.webp" type="image/webp" media="(min-width: 800px)">
        <source srcset="resim-buyuk.jpg" media="(min-width: 1200px)">
        <img src="resim-kucuk.jpg" alt="Responsive resim" loading="lazy">
    </picture>
    
    <!-- srcset ile çoklu çözünürlük -->
    <img 
        srcset="resim-320w.jpg 320w,
                resim-640w.jpg 640w,
                resim-1024w.jpg 1024w,
                resim-1920w.jpg 1920w"
        sizes="(max-width: 640px) 100vw,
               (max-width: 1024px) 50vw,
               33vw"
        src="resim-640w.jpg"
        alt="Çoklu çözünürlük resmi"
        loading="lazy">
</body>
</html>
```

### Async ve Defer

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Async ve Defer</title>
    
    <!-- Normal script (bloklar) -->
    <!-- <script src="script.js"></script> -->
    
    <!-- Async - İndirirken sayfa yüklenmeye devam eder, indirilince çalışır -->
    <script src="analytics.js" async></script>
    
    <!-- Defer - Sayfa yüklendikten sonra çalışır, sırayla -->
    <script src="main.js" defer></script>
    <script src="app.js" defer></script>
    
    <!-- Critical CSS inline -->
    <style>
        body { margin: 0; padding: 0; }
        header { background: #2c3e50; }
    </style>
    
    <!-- Non-critical CSS async -->
    <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
<body>
    <h1>Async ve Defer Örnekleri</h1>
</body>
</html>
```

### Resource Hints

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Resource Hints</title>
    
    <!-- DNS Prefetch - DNS çözümlemesini önceden yap -->
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="https://www.google-analytics.com">
    
    <!-- Preconnect - Bağlantıyı önceden kur -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    
    <!-- Prefetch - Gelecekte kullanılacak kaynağı önceden indir -->
    <link rel="prefetch" href="/next-page.html">
    <link rel="prefetch" href="/images/next-image.jpg" as="image">
    
    <!-- Preload - Kritik kaynağı önceden indir -->
    <link rel="preload" href="/fonts/custom-font.woff2" as="font" type="font/woff2" crossorigin>
    <link rel="preload" href="/critical.css" as="style">
    <link rel="preload" href="/hero-image.jpg" as="image">
    
    <!-- Prerender - Sayfayı arka planda render et -->
    <!-- <link rel="prerender" href="/next-page.html"> -->
</head>
<body>
    <h1>Resource Hints Örnekleri</h1>
</body>
</html>
```

### Critical CSS ve Font Loading

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Critical CSS</title>
    
    <!-- Critical CSS inline -->
    <style>
        /* Above-the-fold CSS */
        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }
        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
        }
        .hero {
            height: 400px;
            background-color: #3498db;
        }
    </style>
    
    <!-- Non-critical CSS -->
    <link rel="preload" href="non-critical.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="non-critical.css"></noscript>
    
    <!-- Font preload -->
    <link rel="preload" href="/fonts/custom-font.woff2" as="font" type="font/woff2" crossorigin>
    
    <!-- Font display -->
    <style>
        @font-face {
            font-family: 'CustomFont';
            src: url('/fonts/custom-font.woff2') format('woff2');
            font-display: swap; /* swap, block, fallback, optional */
        }
    </style>
</head>
<body>
    <header>
        <h1>Web Sitesi</h1>
    </header>
    <div class="hero">
        <h2>Hero Bölümü</h2>
    </div>
    <main>
        <p>İçerik burada yer alır...</p>
    </main>
</body>
</html>
```

### Kapsamlı Performans Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Performans Optimizasyonu</title>
    
    <!-- DNS Prefetch -->
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="https://www.google-analytics.com">
    
    <!-- Preconnect -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    
    <!-- Critical CSS inline -->
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: Arial, sans-serif; }
        header { background: #2c3e50; color: white; padding: 20px; }
    </style>
    
    <!-- Non-critical CSS -->
    <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="styles.css"></noscript>
    
    <!-- Font preload -->
    <link rel="preload" href="/fonts/font.woff2" as="font" type="font/woff2" crossorigin>
</head>
<body>
    <header>
        <h1>Performans Optimizasyonu</h1>
    </header>
    
    <main>
        <h2>İçerik</h2>
        
        <!-- Lazy loading resim -->
        <img 
            src="hero.jpg" 
            alt="Hero resmi" 
            loading="lazy"
            width="1200"
            height="600">
        
        <!-- Responsive resim -->
        <picture>
            <source srcset="resim.webp" type="image/webp">
            <img src="resim.jpg" alt="Resim" loading="lazy">
        </picture>
        
        <!-- Lazy loading iframe -->
        <iframe 
            src="https://www.example.com" 
            loading="lazy"
            width="800" 
            height="600">
        </iframe>
    </main>
    
    <!-- Scripts -->
    <script src="analytics.js" async></script>
    <script src="main.js" defer></script>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Lazy Loading**: Sayfa yükleme hızını artırır, ancak görünür alandaki resimler için kullanmayın.

2. **Async vs Defer**: `async` sırasız çalışır, `defer` sırayla çalışır.

3. **Preload**: Kritik kaynaklar için kullanın.

4. **Preconnect**: Dış kaynaklar için bağlantıyı önceden kurun.

5. **Critical CSS**: Above-the-fold CSS'i inline yapın.

6. **Font Display**: `swap` ile metin görünürlüğünü koruyun.

## 🎯 İyi Pratikler

- Lazy loading kullanın
- Responsive resimler kullanın
- Modern formatlar (WebP, AVIF) kullanın
- Critical CSS'i inline yapın
- Async/defer kullanın
- Resource hints ekleyin
- Font preload yapın
- Minification yapın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


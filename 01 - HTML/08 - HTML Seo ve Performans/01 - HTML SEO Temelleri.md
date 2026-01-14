# 🔍 HTML SEO TEMELLERİ

**SEO** (Search Engine Optimization) (arama motoru optimizasyonu), web sitelerinin arama motorlarında daha iyi sıralanması için yapılan optimizasyonlardır. HTML yapısı **SEO** için kritik öneme sahiptir.

## 📋 SEO İçin Önemli HTML Öğeleri

### Meta Etiketleri

- `<title>` - Sayfa başlığı
- `<meta name="description">` - Sayfa açıklaması
- `<meta name="keywords">` - Anahtar kelimeler
- `<meta name="author">` - Yazar bilgisi
- `<meta name="robots">` - Arama motoru yönlendirmesi

### Semantic HTML

- `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`
- Başlık hiyerarşisi (`<h1>` - `<h6>`)
- Anlamsal etiketler

### Alt Text ve Bağlantılar

- Resimler için `alt` özelliği
- Açıklayıcı bağlantı metinleri
- `title` özelliği

## 💡 Kullanım Örnekleri

### Temel SEO Yapısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Meta Etiketleri -->
    <title>Web Geliştirme Rehberi - HTML, CSS, JavaScript Dersleri</title>
    <meta name="description" content="Web geliştirme için kapsamlı rehber. HTML, CSS ve JavaScript dersleri, örnekler ve ipuçları.">
    <meta name="keywords" content="web geliştirme, HTML, CSS, JavaScript, ders, öğretici">
    <meta name="author" content="Bahadır B. Bekdemir">
    <meta name="robots" content="index, follow">
    
    <!-- Open Graph (Sosyal Medya) -->
    <meta property="og:title" content="Web Geliştirme Rehberi">
    <meta property="og:description" content="Web geliştirme için kapsamlı rehber.">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://www.example.com">
    <meta property="og:image" content="https://www.example.com/image.jpg">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Web Geliştirme Rehberi">
    <meta name="twitter:description" content="Web geliştirme için kapsamlı rehber.">
    <meta name="twitter:image" content="https://www.example.com/image.jpg">
</head>
<body>
    <header>
        <h1>Web Geliştirme Rehberi</h1>
        <nav>
            <ul>
                <li><a href="#html">HTML</a></li>
                <li><a href="#css">CSS</a></li>
                <li><a href="#javascript">JavaScript</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <h2>HTML Nedir?</h2>
            <p>HTML, web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir.</p>
            
            <h3>HTML Temelleri</h3>
            <p>HTML etiketleri ile içerik yapılandırılır.</p>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2024 Web Geliştirme Rehberi</p>
    </footer>
</body>
</html>
```

### Başlık Hiyerarşisi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Başlık Hiyerarşisi - SEO</title>
</head>
<body>
    <!-- Doğru Hiyerarşi -->
    <article>
        <h1>Ana Başlık (Sayfada Sadece Bir Tane)</h1>
        
        <section>
            <h2>Bölüm 1 Başlığı</h2>
            <p>Bölüm 1 içeriği...</p>
            
            <h3>Alt Bölüm 1.1</h3>
            <p>Alt bölüm içeriği...</p>
            
            <h3>Alt Bölüm 1.2</h3>
            <p>Alt bölüm içeriği...</p>
        </section>
        
        <section>
            <h2>Bölüm 2 Başlığı</h2>
            <p>Bölüm 2 içeriği...</p>
            
            <h3>Alt Bölüm 2.1</h3>
            <p>Alt bölüm içeriği...</p>
        </section>
    </article>
    
    <!-- YANLIŞ: Hiyerarşi atlanmış -->
    <!--
    <h1>Başlık 1</h1>
    <h3>Başlık 3 (h2 atlanmış - YANLIŞ)</h3>
    -->
</body>
</html>
```

### Alt Text ve Erişilebilirlik

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Alt Text ve Erişilebilirlik</title>
</head>
<body>
    <article>
        <h1>Doğa Fotoğrafları</h1>
        
        <!-- İyi: Açıklayıcı alt text -->
        <img src="dag.jpg" alt="Yüksek dağlar ve bulutların görüntüsü, güneşli bir günde çekilmiş manzara fotoğrafı">
        
        <!-- Kötü: Boş veya yetersiz alt text -->
        <!-- <img src="dag.jpg" alt=""> -->
        <!-- <img src="dag.jpg" alt="resim"> -->
        
        <!-- Dekoratif resimler için boş alt -->
        <img src="dekoratif-cizgi.jpg" alt="" role="presentation">
        
        <!-- Bağlantılı resimler -->
        <a href="buyuk-resim.jpg">
            <img src="kucuk-resim.jpg" alt="Büyük resmi görmek için tıklayın - Dağ manzarası">
        </a>
    </article>
</body>
</html>
```

### Semantic HTML Yapısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Semantic HTML - SEO</title>
    <meta name="description" content="Semantic HTML kullanımı ve SEO faydaları">
</head>
<body>
    <!-- Semantic yapı -->
    <header>
        <h1>Web Sitesi Başlığı</h1>
        <nav>
            <ul>
                <li><a href="#anasayfa">Ana Sayfa</a></li>
                <li><a href="#hakkimizda">Hakkımızda</a></li>
                <li><a href="#iletisim">İletişim</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article>
            <header>
                <h2>Makale Başlığı</h2>
                <time datetime="2024-01-15">15 Ocak 2024</time>
            </header>
            
            <section>
                <h3>Bölüm 1</h3>
                <p>İçerik...</p>
            </section>
            
            <section>
                <h3>Bölüm 2</h3>
                <p>İçerik...</p>
            </section>
            
            <footer>
                <p>Yazar: Ahmet Yılmaz</p>
            </footer>
        </article>
        
        <aside>
            <h3>İlgili Makaleler</h3>
            <ul>
                <li><a href="#">Makale 1</a></li>
                <li><a href="#">Makale 2</a></li>
            </ul>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 Tüm hakları saklıdır.</p>
    </footer>
</body>
</html>
```

### Kapsamlı SEO Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Temel SEO -->
    <title>Web Geliştirme Rehberi | HTML, CSS, JavaScript Öğrenin</title>
    <meta name="description" content="Web geliştirme için kapsamlı rehber. HTML, CSS ve JavaScript dersleri, örnekler ve ipuçları. Sıfırdan ileri seviyeye kadar öğrenin.">
    <meta name="keywords" content="web geliştirme, HTML, CSS, JavaScript, frontend, backend, programlama, ders, öğretici, tutorial">
    <meta name="author" content="Bahadır B. Bekdemir">
    <meta name="robots" content="index, follow, max-snippet:-1, max-image-preview:large, max-video-preview:-1">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://www.example.com/web-gelistirme-rehberi">
    
    <!-- Open Graph -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Web Geliştirme Rehberi">
    <meta property="og:description" content="Web geliştirme için kapsamlı rehber.">
    <meta property="og:url" content="https://www.example.com/web-gelistirme-rehberi">
    <meta property="og:image" content="https://www.example.com/images/og-image.jpg">
    <meta property="og:locale" content="tr_TR">
    <meta property="og:site_name" content="Web Geliştirme Rehberi">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Web Geliştirme Rehberi">
    <meta name="twitter:description" content="Web geliştirme için kapsamlı rehber.">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-image.jpg">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    
    <!-- Structured Data (JSON-LD) -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Article",
        "headline": "Web Geliştirme Rehberi",
        "description": "Web geliştirme için kapsamlı rehber.",
        "author": {
            "@type": "Person",
            "name": "Bahadır B. Bekdemir"
        },
        "datePublished": "2024-01-15",
        "dateModified": "2024-01-20"
    }
    </script>
</head>
<body>
    <header>
        <h1>Web Geliştirme Rehberi</h1>
        <nav aria-label="Ana navigasyon">
            <ul>
                <li><a href="#html" title="HTML dersleri">HTML</a></li>
                <li><a href="#css" title="CSS dersleri">CSS</a></li>
                <li><a href="#javascript" title="JavaScript dersleri">JavaScript</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article itemscope itemtype="https://schema.org/Article">
            <header>
                <h2 itemprop="headline">HTML Nedir?</h2>
                <time datetime="2024-01-15" itemprop="datePublished">15 Ocak 2024</time>
            </header>
            
            <section>
                <h3>HTML Temelleri</h3>
                <p itemprop="description">
                    HTML (Hyper Text Markup Language), web sayfalarının yapısını 
                    oluşturmak için kullanılan bir işaretleme dilidir.
                </p>
                
                <figure>
                    <img 
                        src="html-logo.jpg" 
                        alt="HTML5 logosu, modern web geliştirme için standart işaretleme dili"
                        width="300"
                        height="300"
                        loading="lazy">
                    <figcaption>HTML5 Logo</figcaption>
                </figure>
            </section>
            
            <section>
                <h3>HTML Özellikleri</h3>
                <ul>
                    <li>Yapısal işaretleme</li>
                    <li>Semantic etiketler</li>
                    <li>Erişilebilirlik</li>
                </ul>
            </section>
        </article>
    </main>
    
    <footer>
        <p>&copy; 2024 Web Geliştirme Rehberi. Tüm hakları saklıdır.</p>
    </footer>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Title**: Her sayfada benzersiz ve açıklayıcı bir `<title>` kullanın (50-60 karakter).

2. **Description**: Meta description açıklayıcı olmalı (150-160 karakter).

3. **H1**: Her sayfada sadece bir `<h1>` etiketi kullanın.

4. **Alt Text**: Tüm resimler için açıklayıcı `alt` text kullanın.

5. **Semantic HTML**: Anlamsal HTML kullanarak arama motorlarının içeriği anlamasını kolaylaştırın.

6. **Structured Data**: JSON-LD ile yapılandırılmış veri ekleyin.

## 🎯 İyi Pratikler

- Her sayfa için benzersiz title ve description
- Doğru başlık hiyerarşisi (h1-h6)
- Tüm resimler için alt text
- Semantic HTML kullanın
- Canonical URL kullanın
- Open Graph ve Twitter Card ekleyin
- Structured Data (JSON-LD) kullanın
- Mobil uyumlu tasarım

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


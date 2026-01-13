# 🚀 HTML BAŞLANGIÇ KODLARI (SADE VE GELİŞMİŞ)

**HTML** (Hyper Text Markup Language) (zengin metin işaretleme dili) sayfaları oluştururken, en sade yapıdan en gelişmiş yapıya kadar farklı seviyelerde başlangıç kodları kullanılabilir.

## 📋 HTML Başlangıç Seviyeleri

### En Sade HTML Yapısı

Minimum gerekli etiketlerle oluşturulan temel yapı.

### Gelişmiş HTML Yapısı

SEO, performans, erişilebilirlik ve modern web standartlarına uygun tam özellikli yapı.

## 💡 Kullanım Örnekleri

### En Sade HTML Başlangıç Kodu

```html
<!doctype html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Sayfa Başlığı</title>
</head>
<body>
    <h1>Merhaba Dünya</h1>
    <p>Bu en sade HTML yapısıdır.</p>
</body>
</html>
```

**Özellikler:**
- Minimum gerekli etiketler
- Temel charset tanımı
- Basit başlık
- Hızlı başlangıç için ideal

### Orta Seviye HTML Başlangıç Kodu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
    <meta name="description" content="Sayfa açıklaması">
</head>
<body>
    <header>
        <h1>Sayfa Başlığı</h1>
    </header>
    
    <main>
        <p>İçerik burada yer alır.</p>
    </main>
    
    <footer>
        <p>&copy; 2024</p>
    </footer>
</body>
</html>
```

**Özellikler:**
- Dil tanımı (`lang="tr"`)
- Viewport meta etiketi (mobil uyumluluk)
- SEO için description
- Semantic HTML yapısı

### Gelişmiş HTML Başlangıç Kodu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Meta Etiketleri -->
    <title>Sayfa Başlığı | Site Adı</title>
    <meta name="description" content="Sayfa açıklaması - 150-160 karakter arası">
    <meta name="keywords" content="anahtar, kelimeler, burada">
    <meta name="author" content="Yazar Adı">
    <meta name="robots" content="index, follow">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://www.example.com/sayfa">
    
    <!-- Open Graph (Sosyal Medya) -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Sayfa Başlığı">
    <meta property="og:description" content="Sayfa açıklaması">
    <meta property="og:url" content="https://www.example.com/sayfa">
    <meta property="og:image" content="https://www.example.com/images/og-image.jpg">
    <meta property="og:site_name" content="Site Adı">
    <meta property="og:locale" content="tr_TR">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Sayfa Başlığı">
    <meta name="twitter:description" content="Sayfa açıklaması">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-image.jpg">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#3498db">
    
    <!-- DNS Prefetch ve Preconnect -->
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    
    <!-- Critical CSS (Inline) -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #333;
        }
    </style>
    
    <!-- Non-critical CSS -->
    <link rel="preload" href="/styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="/styles.css"></noscript>
    
    <!-- Structured Data (JSON-LD) -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "WebPage",
        "name": "Sayfa Başlığı",
        "description": "Sayfa açıklaması",
        "url": "https://www.example.com/sayfa",
        "inLanguage": "tr-TR"
    }
    </script>
</head>
<body>
    <!-- Skip Link (Erişilebilirlik) -->
    <a href="#main-content" class="skip-link" style="position: absolute; top: -40px; left: 0; background: #2c3e50; color: white; padding: 8px; text-decoration: none; z-index: 1000;">
        Ana içeriğe geç
    </a>
    
    <header role="banner">
        <nav role="navigation" aria-label="Ana navigasyon">
            <ul>
                <li><a href="/">Ana Sayfa</a></li>
                <li><a href="/hakkimizda">Hakkımızda</a></li>
                <li><a href="/iletisim">İletişim</a></li>
            </ul>
        </nav>
    </header>
    
    <main id="main-content" role="main">
        <article itemscope itemtype="https://schema.org/Article">
            <header>
                <h1 itemprop="headline">Sayfa Başlığı</h1>
                <time datetime="2024-01-15" itemprop="datePublished">15 Ocak 2024</time>
            </header>
            
            <section>
                <p itemprop="description">İçerik burada yer alır.</p>
            </section>
        </article>
    </main>
    
    <aside role="complementary" aria-label="Yan içerik">
        <h2>İlgili İçerik</h2>
        <ul>
            <li><a href="#">Bağlantı 1</a></li>
            <li><a href="#">Bağlantı 2</a></li>
        </ul>
    </aside>
    
    <footer role="contentinfo">
        <p>&copy; 2024 Site Adı. Tüm hakları saklıdır.</p>
        <address>
            <a href="mailto:info@example.com">info@example.com</a>
        </address>
    </footer>
    
    <!-- JavaScript (Defer ile) -->
    <script src="/main.js" defer></script>
    
    <!-- Analytics (Async ile) -->
    <script src="/analytics.js" async></script>
</body>
</html>
```

### En Gelişmiş HTML Başlangıç Kodu (Production Ready)

```html
<!doctype html>
<html lang="tr" dir="ltr">
<head>
    <!-- Character Encoding -->
    <meta charset="UTF-8">
    
    <!-- Viewport (Responsive) -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    
    <!-- Primary Meta Tags -->
    <title>Sayfa Başlığı | Site Adı - Açıklayıcı Alt Başlık</title>
    <meta name="title" content="Sayfa Başlığı | Site Adı">
    <meta name="description" content="Sayfa açıklaması - 150-160 karakter arası, açıklayıcı ve çekici olmalı.">
    <meta name="keywords" content="anahtar, kelimeler, burada, virgülle, ayrılmış">
    <meta name="author" content="Yazar Adı">
    <meta name="robots" content="index, follow, max-snippet:-1, max-image-preview:large, max-video-preview:-1">
    <meta name="language" content="Turkish">
    <meta name="revisit-after" content="7 days">
    <meta name="rating" content="general">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://www.example.com/sayfa">
    
    <!-- Alternate Languages -->
    <link rel="alternate" hreflang="tr" href="https://www.example.com/tr/sayfa">
    <link rel="alternate" hreflang="en" href="https://www.example.com/en/page">
    <link rel="alternate" hreflang="x-default" href="https://www.example.com/sayfa">
    
    <!-- Open Graph / Facebook -->
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://www.example.com/sayfa">
    <meta property="og:title" content="Sayfa Başlığı">
    <meta property="og:description" content="Sayfa açıklaması">
    <meta property="og:image" content="https://www.example.com/images/og-image.jpg">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:image:alt" content="Görsel açıklaması">
    <meta property="og:site_name" content="Site Adı">
    <meta property="og:locale" content="tr_TR">
    <meta property="og:locale:alternate" content="en_US">
    
    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:url" content="https://www.example.com/sayfa">
    <meta name="twitter:title" content="Sayfa Başlığı">
    <meta name="twitter:description" content="Sayfa açıklaması">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-image.jpg">
    <meta name="twitter:image:alt" content="Görsel açıklaması">
    <meta name="twitter:site" content="@kullaniciadi">
    <meta name="twitter:creator" content="@yazaradi">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    <link rel="manifest" href="/site.webmanifest">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#3498db">
    <meta name="msapplication-TileColor" content="#3498db">
    <meta name="msapplication-config" content="/browserconfig.xml">
    
    <!-- Mobile Web App -->
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Site Adı">
    
    <!-- DNS Prefetch -->
    <link rel="dns-prefetch" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="https://www.google-analytics.com">
    <link rel="dns-prefetch" href="https://cdn.example.com">
    
    <!-- Preconnect -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    
    <!-- Preload Critical Resources -->
    <link rel="preload" href="/fonts/main-font.woff2" as="font" type="font/woff2" crossorigin>
    <link rel="preload" href="/images/hero-image.webp" as="image">
    <link rel="preload" href="/critical.css" as="style">
    
    <!-- Critical CSS (Inline) -->
    <style>
        /* Reset */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* Base Styles */
        html {
            font-size: 16px;
            scroll-behavior: smooth;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #fff;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        
        /* Skip Link */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: #2c3e50;
            color: white;
            padding: 8px 16px;
            text-decoration: none;
            z-index: 1000;
        }
        
        .skip-link:focus {
            top: 0;
        }
        
        /* Focus Styles */
        a:focus,
        button:focus,
        input:focus,
        textarea:focus,
        select:focus {
            outline: 3px solid #3498db;
            outline-offset: 2px;
        }
    </style>
    
    <!-- Non-critical CSS -->
    <link rel="preload" href="/styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="/styles.css"></noscript>
    
    <!-- Structured Data (JSON-LD) -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "WebPage",
        "name": "Sayfa Başlığı",
        "description": "Sayfa açıklaması",
        "url": "https://www.example.com/sayfa",
        "inLanguage": "tr-TR",
        "isPartOf": {
            "@type": "WebSite",
            "name": "Site Adı",
            "url": "https://www.example.com"
        },
        "about": {
            "@type": "Thing",
            "name": "Konu"
        },
        "primaryImageOfPage": {
            "@type": "ImageObject",
            "url": "https://www.example.com/images/og-image.jpg"
        },
        "datePublished": "2024-01-15T10:00:00+03:00",
        "dateModified": "2024-01-20T15:30:00+03:00",
        "author": {
            "@type": "Person",
            "name": "Yazar Adı"
        },
        "publisher": {
            "@type": "Organization",
            "name": "Site Adı",
            "logo": {
                "@type": "ImageObject",
                "url": "https://www.example.com/logo.jpg"
            }
        }
    }
    </script>
    
    <!-- Organization Schema -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Organization",
        "name": "Site Adı",
        "url": "https://www.example.com",
        "logo": "https://www.example.com/logo.jpg",
        "contactPoint": {
            "@type": "ContactPoint",
            "telephone": "+90-312-123-45-67",
            "contactType": "Müşteri Hizmetleri"
        },
        "sameAs": [
            "https://www.facebook.com/example",
            "https://www.twitter.com/example",
            "https://www.linkedin.com/company/example"
        ]
    }
    </script>
</head>
<body>
    <!-- Skip Link (Erişilebilirlik) -->
    <a href="#main-content" class="skip-link">Ana içeriğe geç</a>
    
    <!-- Header -->
    <header role="banner">
        <nav role="navigation" aria-label="Ana navigasyon">
            <ul>
                <li><a href="/" aria-current="page">Ana Sayfa</a></li>
                <li><a href="/hakkimizda">Hakkımızda</a></li>
                <li><a href="/hizmetler">Hizmetler</a></li>
                <li><a href="/iletisim">İletişim</a></li>
            </ul>
        </nav>
    </header>
    
    <!-- Main Content -->
    <main id="main-content" role="main">
        <article itemscope itemtype="https://schema.org/Article">
            <header>
                <h1 itemprop="headline">Sayfa Başlığı</h1>
                <div class="meta">
                    <time datetime="2024-01-15T10:00:00+03:00" itemprop="datePublished">
                        15 Ocak 2024
                    </time>
                    <span itemprop="author" itemscope itemtype="https://schema.org/Person">
                        <span itemprop="name">Yazar Adı</span>
                    </span>
                </div>
            </header>
            
            <div itemprop="articleBody">
                <section>
                    <h2>Bölüm Başlığı</h2>
                    <p itemprop="description">İçerik burada yer alır.</p>
                    
                    <figure>
                        <img 
                            src="/images/content-image.jpg" 
                            alt="Açıklayıcı resim açıklaması"
                            width="800"
                            height="600"
                            loading="lazy">
                        <figcaption>Resim açıklaması</figcaption>
                    </figure>
                </section>
            </div>
            
            <footer>
                <p>
                    Son Güncelleme: 
                    <time datetime="2024-01-20T15:30:00+03:00" itemprop="dateModified">
                        20 Ocak 2024
                    </time>
                </p>
            </footer>
        </article>
    </main>
    
    <!-- Sidebar -->
    <aside role="complementary" aria-label="Yan içerik">
        <section>
            <h2>İlgili İçerik</h2>
            <nav aria-label="İlgili içerik navigasyonu">
                <ul>
                    <li><a href="#">Bağlantı 1</a></li>
                    <li><a href="#">Bağlantı 2</a></li>
                    <li><a href="#">Bağlantı 3</a></li>
                </ul>
            </nav>
        </section>
    </aside>
    
    <!-- Footer -->
    <footer role="contentinfo">
        <div>
            <p>&copy; <time datetime="2024">2024</time> Site Adı. Tüm hakları saklıdır.</p>
            <address>
                <p>
                    <strong>Adres:</strong><br>
                    İstanbul Caddesi No:123<br>
                    Çankaya, Ankara<br>
                    Posta Kodu: 06100
                </p>
                <p>
                    <strong>İletişim:</strong><br>
                    <a href="tel:+903121234567">+90 312 123 45 67</a><br>
                    <a href="mailto:info@example.com">info@example.com</a>
                </p>
            </address>
        </div>
        
        <nav aria-label="Alt navigasyon">
            <ul>
                <li><a href="/gizlilik">Gizlilik Politikası</a></li>
                <li><a href="/kullanim">Kullanım Şartları</a></li>
                <li><a href="/cerezler">Çerez Politikası</a></li>
            </ul>
        </nav>
    </footer>
    
    <!-- JavaScript -->
    <script src="/main.js" defer></script>
    
    <!-- Analytics (Async) -->
    <script src="/analytics.js" async></script>
    
    <!-- Service Worker (PWA) -->
    <script>
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', function() {
                navigator.serviceWorker.register('/sw.js');
            });
        }
    </script>
</body>
</html>
```

## 📊 Karşılaştırma Tablosu

| Özellik | En Sade | Orta Seviye | Gelişmiş | En Gelişmiş |
| :------ | :------ | :---------- | :------- | :---------- |
| Doctype | ✅ | ✅ | ✅ | ✅ |
| Charset | ✅ | ✅ | ✅ | ✅ |
| Lang | ❌ | ✅ | ✅ | ✅ |
| Viewport | ❌ | ✅ | ✅ | ✅ |
| Title | ✅ | ✅ | ✅ | ✅ |
| Description | ❌ | ✅ | ✅ | ✅ |
| Semantic HTML | ❌ | ✅ | ✅ | ✅ |
| Open Graph | ❌ | ❌ | ✅ | ✅ |
| Twitter Card | ❌ | ❌ | ✅ | ✅ |
| Favicon | ❌ | ❌ | ✅ | ✅ |
| Structured Data | ❌ | ❌ | ✅ | ✅ |
| Resource Hints | ❌ | ❌ | ✅ | ✅ |
| Critical CSS | ❌ | ❌ | ✅ | ✅ |
| Erişilebilirlik | ❌ | ❌ | ✅ | ✅ |
| PWA | ❌ | ❌ | ❌ | ✅ |

## ⚠️ Önemli Notlar

1. **En Sade**: Hızlı prototipleme ve öğrenme için idealdir.

2. **Orta Seviye**: Küçük projeler ve kişisel siteler için yeterlidir.

3. **Gelişmiş**: Profesyonel web siteleri için önerilir.

4. **En Gelişmiş**: Enterprise seviye projeler ve production ortamları için idealdir.

5. **Seçim**: Projenin ihtiyacına göre uygun seviyeyi seçin.

## 🎯 Hangi Seviyeyi Seçmeliyim?

- **Öğrenme/Test**: En Sade
- **Kişisel Blog**: Orta Seviye
- **Kurumsal Site**: Gelişmiş
- **E-Ticaret/Büyük Projeler**: En Gelişmiş

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


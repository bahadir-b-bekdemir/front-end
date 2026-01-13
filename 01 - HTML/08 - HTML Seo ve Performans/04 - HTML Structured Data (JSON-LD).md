# 📊 HTML STRUCTURED DATA (JSON-LD)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) **Structured Data** (Yapılandırılmış Veri), arama motorlarının içeriği daha iyi anlaması için kullanılan işaretleme formatıdır. **JSON-LD** (JavaScript Object Notation for Linked Data) en yaygın kullanılan formattır.

## 📋 Structured Data Türleri

### Schema.org Türleri

- `Article` - Makale
- `Organization` - Organizasyon
- `Person` - Kişi
- `Product` - Ürün
- `Review` - Değerlendirme
- `BreadcrumbList` - Ekmek kırıntısı
- `FAQPage` - SSS sayfası
- `LocalBusiness` - Yerel işletme

## 💡 Kullanım Örnekleri

### Article (Makale)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Makale Başlığı</title>
    
    <!-- JSON-LD Structured Data -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Article",
        "headline": "Web Geliştirme Rehberi",
        "description": "Web geliştirme için kapsamlı rehber.",
        "image": "https://www.example.com/images/article.jpg",
        "author": {
            "@type": "Person",
            "name": "Bahadır B. Bekdemir",
            "url": "https://www.example.com/author"
        },
        "publisher": {
            "@type": "Organization",
            "name": "Web Geliştirme Rehberi",
            "logo": {
                "@type": "ImageObject",
                "url": "https://www.example.com/logo.jpg"
            }
        },
        "datePublished": "2024-01-15T10:00:00+03:00",
        "dateModified": "2024-01-20T15:30:00+03:00",
        "mainEntityOfPage": {
            "@type": "WebPage",
            "@id": "https://www.example.com/article"
        }
    }
    </script>
</head>
<body>
    <article>
        <h1>Web Geliştirme Rehberi</h1>
        <p>Makale içeriği...</p>
    </article>
</body>
</html>
```

### Organization (Organizasyon)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Hakkımızda</title>
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Organization",
        "name": "ABC Teknoloji A.Ş.",
        "url": "https://www.abc.com",
        "logo": "https://www.abc.com/logo.jpg",
        "contactPoint": {
            "@type": "ContactPoint",
            "telephone": "+90-312-123-45-67",
            "contactType": "Müşteri Hizmetleri",
            "areaServed": "TR",
            "availableLanguage": ["Turkish", "English"]
        },
        "sameAs": [
            "https://www.facebook.com/abc",
            "https://www.twitter.com/abc",
            "https://www.linkedin.com/company/abc"
        ],
        "address": {
            "@type": "PostalAddress",
            "streetAddress": "İstanbul Caddesi No:123",
            "addressLocality": "Ankara",
            "addressRegion": "Çankaya",
            "postalCode": "06100",
            "addressCountry": "TR"
        }
    }
    </script>
</head>
<body>
    <h1>Hakkımızda</h1>
    <p>ABC Teknoloji A.Ş. hakkında bilgiler...</p>
</body>
</html>
```

### Product (Ürün)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Ürün Sayfası</title>
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Product",
        "name": "Laptop Dell XPS 15",
        "image": [
            "https://www.example.com/images/laptop-1.jpg",
            "https://www.example.com/images/laptop-2.jpg"
        ],
        "description": "Yüksek performanslı laptop, Intel i7 işlemci, 16GB RAM.",
        "brand": {
            "@type": "Brand",
            "name": "Dell"
        },
        "offers": {
            "@type": "Offer",
            "url": "https://www.example.com/urun/laptop",
            "priceCurrency": "TRY",
            "price": "25000",
            "priceValidUntil": "2024-12-31",
            "availability": "https://schema.org/InStock",
            "seller": {
                "@type": "Organization",
                "name": "ABC Teknoloji"
            }
        },
        "aggregateRating": {
            "@type": "AggregateRating",
            "ratingValue": "4.5",
            "reviewCount": "120"
        }
    }
    </script>
</head>
<body>
    <h1>Laptop Dell XPS 15</h1>
    <p>Ürün açıklaması...</p>
    <p>Fiyat: 25.000 TL</p>
</body>
</html>
```

### BreadcrumbList (Ekmek Kırıntısı)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Ürün Detay</title>
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "BreadcrumbList",
        "itemListElement": [
            {
                "@type": "ListItem",
                "position": 1,
                "name": "Ana Sayfa",
                "item": "https://www.example.com"
            },
            {
                "@type": "ListItem",
                "position": 2,
                "name": "Elektronik",
                "item": "https://www.example.com/elektronik"
            },
            {
                "@type": "ListItem",
                "position": 3,
                "name": "Laptop",
                "item": "https://www.example.com/elektronik/laptop"
            },
            {
                "@type": "ListItem",
                "position": 4,
                "name": "Dell XPS 15",
                "item": "https://www.example.com/elektronik/laptop/dell-xps-15"
            }
        ]
    }
    </script>
</head>
<body>
    <nav aria-label="Breadcrumb">
        <ol>
            <li><a href="/">Ana Sayfa</a></li>
            <li><a href="/elektronik">Elektronik</a></li>
            <li><a href="/elektronik/laptop">Laptop</a></li>
            <li>Dell XPS 15</li>
        </ol>
    </nav>
    
    <h1>Dell XPS 15</h1>
</body>
</html>
```

### FAQPage (SSS Sayfası)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sık Sorulan Sorular</title>
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "FAQPage",
        "mainEntity": [
            {
                "@type": "Question",
                "name": "HTML nedir?",
                "acceptedAnswer": {
                    "@type": "Answer",
                    "text": "HTML (Hyper Text Markup Language), web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir."
                }
            },
            {
                "@type": "Question",
                "name": "CSS nedir?",
                "acceptedAnswer": {
                    "@type": "Answer",
                    "text": "CSS (Cascading Style Sheets), web sayfalarının görsel tasarımını yapmak için kullanılan bir stil dilidir."
                }
            },
            {
                "@type": "Question",
                "name": "JavaScript nedir?",
                "acceptedAnswer": {
                    "@type": "Answer",
                    "text": "JavaScript, web sayfalarına etkileşim eklemek için kullanılan bir programlama dilidir."
                }
            }
        ]
    }
    </script>
</head>
<body>
    <h1>Sık Sorulan Sorular</h1>
    
    <dl>
        <dt>HTML nedir?</dt>
        <dd>HTML (Hyper Text Markup Language), web sayfalarının yapısını oluşturmak için kullanılan bir işaretleme dilidir.</dd>
        
        <dt>CSS nedir?</dt>
        <dd>CSS (Cascading Style Sheets), web sayfalarının görsel tasarımını yapmak için kullanılan bir stil dilidir.</dd>
        
        <dt>JavaScript nedir?</dt>
        <dd>JavaScript, web sayfalarına etkileşim eklemek için kullanılan bir programlama dilidir.</dd>
    </dl>
</body>
</html>
```

### LocalBusiness (Yerel İşletme)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>İşletme Bilgileri</title>
    
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "LocalBusiness",
        "name": "ABC Restoran",
        "image": "https://www.example.com/images/restoran.jpg",
        "@id": "https://www.example.com",
        "url": "https://www.example.com",
        "telephone": "+90-312-123-45-67",
        "priceRange": "$$",
        "address": {
            "@type": "PostalAddress",
            "streetAddress": "İstanbul Caddesi No:123",
            "addressLocality": "Ankara",
            "addressRegion": "Çankaya",
            "postalCode": "06100",
            "addressCountry": "TR"
        },
        "geo": {
            "@type": "GeoCoordinates",
            "latitude": 39.9334,
            "longitude": 32.8597
        },
        "openingHoursSpecification": [
            {
                "@type": "OpeningHoursSpecification",
                "dayOfWeek": [
                    "Monday",
                    "Tuesday",
                    "Wednesday",
                    "Thursday",
                    "Friday"
                ],
                "opens": "09:00",
                "closes": "22:00"
            },
            {
                "@type": "OpeningHoursSpecification",
                "dayOfWeek": "Saturday",
                "opens": "10:00",
                "closes": "23:00"
            }
        ],
        "servesCuisine": "Türk Mutfağı"
    }
    </script>
</head>
<body>
    <h1>ABC Restoran</h1>
    <p>İşletme bilgileri...</p>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Structured Data</title>
    
    <!-- Organization -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Organization",
        "name": "Web Geliştirme Rehberi",
        "url": "https://www.example.com",
        "logo": "https://www.example.com/logo.jpg"
    }
    </script>
    
    <!-- Article -->
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
    
    <!-- BreadcrumbList -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "BreadcrumbList",
        "itemListElement": [
            {
                "@type": "ListItem",
                "position": 1,
                "name": "Ana Sayfa",
                "item": "https://www.example.com"
            },
            {
                "@type": "ListItem",
                "position": 2,
                "name": "Makaleler",
                "item": "https://www.example.com/makaleler"
            }
        ]
    }
    </script>
</head>
<body>
    <h1>Kapsamlı Structured Data Örneği</h1>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **JSON-LD**: En yaygın ve önerilen format.

2. **Schema.org**: Standart vocabulary kullanın.

3. **Doğrulama**: Google Rich Results Test ile test edin.

4. **Çoklu Schema**: Birden fazla schema kullanılabilir.

5. **Güncellik**: Verileri güncel tutun.

## 🎯 İyi Pratikler

- JSON-LD formatını kullanın
- Schema.org vocabulary kullanın
- Google Rich Results Test ile test edin
- Verileri güncel tutun
- Doğru schema tipini seçin
- Gerekli alanları doldurun

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📋 HTML META ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) meta etiketleri sayfa hakkında bilgi sağlar ve **SEO** (Search Engine Optimization) ile tarayıcı davranışlarını kontrol eder.

## 📋 Meta Etiket Türleri

### SEO Meta Etiketleri

- `description` - Sayfa açıklaması
- `keywords` - Anahtar kelimeler
- `author` - Yazar bilgisi
- `robots` - Arama motoru yönlendirmesi

### Viewport ve Responsive

- `viewport` - Mobil uyumluluk

### Open Graph (Sosyal Medya)

- `og:title`, `og:description`, `og:image` vb.

### Twitter Card

- `twitter:card`, `twitter:title` vb.

## 💡 Kullanım Örnekleri

### Temel Meta Etiketleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Meta Etiketleri -->
    <title>Web Geliştirme Rehberi</title>
    <meta name="description" content="Web geliştirme için kapsamlı rehber. HTML, CSS ve JavaScript dersleri.">
    <meta name="keywords" content="web geliştirme, HTML, CSS, JavaScript">
    <meta name="author" content="Bahadır B. Bekdemir">
    <meta name="robots" content="index, follow">
    
    <!-- Dil ve Bölge -->
    <meta http-equiv="content-language" content="tr">
    <meta name="language" content="Turkish">
</head>
<body>
    <h1>Web Geliştirme Rehberi</h1>
</body>
</html>
```

### Viewport Meta Etiketi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    
    <!-- Responsive için viewport -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    
    <!-- Alternatif viewport ayarları -->
    <!--
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="viewport" content="width=1024">
    <meta name="viewport" content="initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    -->
    
    <title>Responsive Sayfa</title>
</head>
<body>
    <h1>Mobil Uyumlu Sayfa</h1>
</body>
</html>
```

### Robots Meta Etiketi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Robots Meta Etiketi</title>
    
    <!-- Arama motoru yönlendirmesi -->
    <meta name="robots" content="index, follow">
    
    <!-- Alternatifler -->
    <!--
    <meta name="robots" content="noindex, nofollow">  <!-- Sayfayı indeksleme, linkleri takip etme -->
    <meta name="robots" content="index, nofollow">      <!-- Sayfayı indeksle, linkleri takip etme -->
    <meta name="robots" content="noindex, follow">     <!-- Sayfayı indeksleme, linkleri takip et -->
    <meta name="robots" content="noarchive">            <!-- Önbelleğe alma -->
    <meta name="robots" content="nosnippet">            <!-- Snippet gösterme -->
    -->
    
    <!-- Google özel -->
    <meta name="googlebot" content="index, follow">
    <meta name="google" content="nositelinkssearchbox">
</head>
<body>
    <h1>Robots Meta Etiketi Örneği</h1>
</body>
</html>
```

### Open Graph (Sosyal Medya)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Makale Başlığı</title>
    <meta name="description" content="Makale açıklaması">
    
    <!-- Open Graph Meta Etiketleri -->
    <meta property="og:type" content="article">
    <meta property="og:title" content="Makale Başlığı">
    <meta property="og:description" content="Makale açıklaması">
    <meta property="og:url" content="https://www.example.com/makale">
    <meta property="og:image" content="https://www.example.com/images/makale-resim.jpg">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:image:alt" content="Makale görseli">
    <meta property="og:site_name" content="Web Sitesi Adı">
    <meta property="og:locale" content="tr_TR">
    
    <!-- Article özel -->
    <meta property="article:author" content="Ahmet Yılmaz">
    <meta property="article:published_time" content="2024-01-15T10:00:00+03:00">
    <meta property="article:modified_time" content="2024-01-20T15:30:00+03:00">
    <meta property="article:section" content="Teknoloji">
    <meta property="article:tag" content="HTML">
    <meta property="article:tag" content="CSS">
</head>
<body>
    <article>
        <h1>Makale Başlığı</h1>
        <p>Makale içeriği...</p>
    </article>
</body>
</html>
```

### Twitter Card

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Makale Başlığı</title>
    <meta name="description" content="Makale açıklaması">
    
    <!-- Twitter Card Meta Etiketleri -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:site" content="@kullaniciadi">
    <meta name="twitter:creator" content="@yazaradi">
    <meta name="twitter:title" content="Makale Başlığı">
    <meta name="twitter:description" content="Makale açıklaması">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-resim.jpg">
    <meta name="twitter:image:alt" content="Görsel açıklaması">
    
    <!-- Twitter Card Tipleri -->
    <!--
    summary - Küçük resimli kart
    summary_large_image - Büyük resimli kart
    app - Uygulama kartı
    player - Video/audio oynatıcı kartı
    -->
</head>
<body>
    <article>
        <h1>Makale Başlığı</h1>
        <p>Makale içeriği...</p>
    </article>
</body>
</html>
```

### HTTP-Equiv Meta Etiketleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    
    <!-- HTTP-Equiv Meta Etiketleri -->
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <meta http-equiv="content-language" content="tr">
    <meta http-equiv="refresh" content="30"> <!-- 30 saniyede bir yenile -->
    <!-- <meta http-equiv="refresh" content="5;url=https://www.example.com"> --> <!-- 5 saniye sonra yönlendir -->
    
    <!-- Cache Kontrolü -->
    <meta http-equiv="cache-control" content="no-cache, no-store, must-revalidate">
    <meta http-equiv="pragma" content="no-cache">
    <meta http-equiv="expires" content="0">
    
    <!-- Alternatif: Cache'e izin ver -->
    <!--
    <meta http-equiv="cache-control" content="public, max-age=3600">
    <meta http-equiv="expires" content="Wed, 21 Oct 2024 07:28:00 GMT">
    -->
    
    <title>HTTP-Equiv Örnekleri</title>
</head>
<body>
    <h1>HTTP-Equiv Meta Etiketleri</h1>
</body>
</html>
```

### Kapsamlı Meta Etiket Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Temel SEO -->
    <title>Web Geliştirme Rehberi | HTML, CSS, JavaScript</title>
    <meta name="description" content="Web geliştirme için kapsamlı rehber. HTML, CSS ve JavaScript dersleri, örnekler ve ipuçları.">
    <meta name="keywords" content="web geliştirme, HTML, CSS, JavaScript, frontend, programlama">
    <meta name="author" content="Bahadır B. Bekdemir">
    <meta name="robots" content="index, follow">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://www.example.com/web-gelistirme-rehberi">
    
    <!-- Open Graph -->
    <meta property="og:type" content="website">
    <meta property="og:title" content="Web Geliştirme Rehberi">
    <meta property="og:description" content="Web geliştirme için kapsamlı rehber.">
    <meta property="og:url" content="https://www.example.com/web-gelistirme-rehberi">
    <meta property="og:image" content="https://www.example.com/images/og-image.jpg">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:site_name" content="Web Geliştirme Rehberi">
    <meta property="og:locale" content="tr_TR">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Web Geliştirme Rehberi">
    <meta name="twitter:description" content="Web geliştirme için kapsamlı rehber.">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-image.jpg">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#3498db">
    
    <!-- Mobile Web App -->
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Web Rehberi">
</head>
<body>
    <h1>Web Geliştirme Rehberi</h1>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Description**: 150-160 karakter arası olmalı, açıklayıcı ve çekici olmalı.

2. **Keywords**: Artık çok önemli değil, ancak yine de eklenebilir.

3. **Robots**: Sayfa indeksleme kontrolü için kullanılır.

4. **Open Graph**: Sosyal medyada paylaşım için önemlidir.

5. **Viewport**: Mobil uyumluluk için zorunludur.

6. **Canonical**: Duplicate content sorunlarını önler.

## 🎯 İyi Pratikler

- Her sayfa için benzersiz title ve description
- Open Graph ve Twitter Card ekleyin
- Viewport meta etiketi ekleyin
- Canonical URL kullanın
- Favicon ekleyin
- Theme color belirleyin
- Mobil web app meta etiketleri ekleyin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


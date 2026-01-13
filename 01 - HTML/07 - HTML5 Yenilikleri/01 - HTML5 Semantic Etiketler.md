# 🏗️ HTML5 SEMANTIC ETİKETLER

**HTML5** ile birlikte anlamsal (semantic) etiketler eklendi. Bu etiketler sayfa yapısını daha anlamlı hale getirir ve **SEO** (Search Engine Optimization) ile erişilebilirlik açısından önemlidir.

## 📋 Semantic Etiketler

| Etiket | Açıklama | Kullanım |
| :----- | :------- | :------- |
| `<header>` | Sayfa veya bölüm başlığı | Üst bilgi |
| `<nav>` | Navigasyon menüsü | Menü |
| `<main>` | Ana içerik | Ana bölüm |
| `<section>` | Bölüm | İçerik bölümü |
| `<article>` | Makale/Bağımsız içerik | Blog yazısı |
| `<aside>` | Yan içerik | Kenar çubuğu |
| `<footer>` | Alt bilgi | Sayfa altı |
| `<figure>` | Resim/Grafik | Görsel içerik |
| `<figcaption>` | Görsel açıklaması | Görsel alt yazı |
| `<time>` | Tarih/Saat | Zaman bilgisi |
| `<mark>` | Vurgulanmış metin | Önemli metin |
| `<progress>` | İlerleme çubuğu | İlerleme göstergesi |
| `<meter>` | Ölçüm göstergesi | Değer göstergesi |

## 💡 Kullanım Örnekleri

### Temel Semantic Yapı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Semantic Yapı</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
        }
        
        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        nav {
            background-color: #34495e;
            padding: 10px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            padding: 10px;
        }
        
        main {
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        section {
            margin: 20px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        article {
            margin: 20px 0;
            padding: 20px;
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        aside {
            background-color: #ecf0f1;
            padding: 20px;
            border-radius: 5px;
        }
        
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Web Sitesi Başlığı</h1>
        <p>Alt başlık veya açıklama</p>
    </header>
    
    <nav>
        <a href="#anasayfa">Ana Sayfa</a>
        <a href="#hakkimizda">Hakkımızda</a>
        <a href="#hizmetler">Hizmetler</a>
        <a href="#iletisim">İletişim</a>
    </nav>
    
    <main>
        <section>
            <h2>Ana Bölüm</h2>
            <article>
                <h3>Makale Başlığı 1</h3>
                <p>Makale içeriği burada yer alır.</p>
                <time datetime="2024-01-15">15 Ocak 2024</time>
            </article>
            
            <article>
                <h3>Makale Başlığı 2</h3>
                <p>Makale içeriği burada yer alır.</p>
                <time datetime="2024-01-20">20 Ocak 2024</time>
            </article>
        </section>
        
        <aside>
            <h3>Yan İçerik</h3>
            <p>Reklamlar, bağlantılar veya ek bilgiler burada yer alır.</p>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 Tüm hakları saklıdır.</p>
    </footer>
</body>
</html>
```

### Figure ve Figcaption

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
    </article>
</body>
</html>
```

### Time Etiketi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Time Etiketi</title>
</head>
<body>
    <article>
        <h1>Makale Başlığı</h1>
        <p>
            Yayın Tarihi: 
            <time datetime="2024-01-15T10:30:00">15 Ocak 2024, 10:30</time>
        </p>
        
        <p>
            Son Güncelleme: 
            <time datetime="2024-01-20">20 Ocak 2024</time>
        </p>
        
        <p>
            Etkinlik Tarihi: 
            <time datetime="2024-02-01T14:00:00">1 Şubat 2024, 14:00</time>
        </p>
    </article>
</body>
</html>
```

### Mark, Progress ve Meter

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Mark, Progress ve Meter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        mark {
            background-color: #fff3cd;
            padding: 2px 5px;
        }
        
        progress {
            width: 100%;
            height: 25px;
        }
        
        meter {
            width: 100%;
            height: 25px;
        }
    </style>
</head>
<body>
    <h1>HTML5 Yeni Etiketler</h1>
    
    <section>
        <h2>Mark - Vurgulanmış Metin</h2>
        <p>
            Bu metin içinde <mark>önemli bir kısım</mark> vurgulanmıştır.
        </p>
    </section>
    
    <section>
        <h2>Progress - İlerleme Çubuğu</h2>
        <p>Yükleme İlerlemesi:</p>
        <progress value="75" max="100">75%</progress>
        
        <p>İndirme İlerlemesi:</p>
        <progress value="45" max="100">45%</progress>
    </section>
    
    <section>
        <h2>Meter - Ölçüm Göstergesi</h2>
        <p>Disk Kullanımı:</p>
        <meter value="65" min="0" max="100" optimum="50" low="30" high="80">
            65%
        </meter>
        
        <p>Bateri Seviyesi:</p>
        <meter value="85" min="0" max="100" optimum="80" low="20" high="90">
            85%
        </meter>
    </section>
</body>
</html>
```

### Kapsamlı Semantic Yapı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Semantic Yapı</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }
        
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }
        
        nav {
            background-color: #2c3e50;
            padding: 15px;
        }
        
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        nav li {
            margin: 0 15px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
            border-radius: 3px;
            transition: background-color 0.3s;
        }
        
        nav a:hover {
            background-color: #3498db;
        }
        
        main {
            flex: 1;
            display: flex;
            max-width: 1200px;
            margin: 20px auto;
            gap: 20px;
            padding: 0 20px;
        }
        
        section {
            flex: 2;
        }
        
        article {
            background-color: white;
            padding: 25px;
            margin-bottom: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        article h2 {
            color: #2c3e50;
            margin-bottom: 15px;
        }
        
        article time {
            color: #7f8c8d;
            font-size: 0.9em;
        }
        
        aside {
            flex: 1;
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            height: fit-content;
        }
        
        aside h3 {
            color: #2c3e50;
            margin-bottom: 15px;
        }
        
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: auto;
        }
        
        figure {
            margin: 20px 0;
        }
        
        figure img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
        }
        
        figcaption {
            margin-top: 10px;
            font-style: italic;
            color: #666;
            text-align: center;
        }
    </style>
</head>
<body>
    <header>
        <h1>Web Geliştirme Blogu</h1>
        <p>HTML, CSS ve JavaScript hakkında güncel içerikler</p>
    </header>
    
    <nav>
        <ul>
            <li><a href="#anasayfa">Ana Sayfa</a></li>
            <li><a href="#makaleler">Makaleler</a></li>
            <li><a href="#hakkimizda">Hakkımızda</a></li>
            <li><a href="#iletisim">İletişim</a></li>
        </ul>
    </nav>
    
    <main>
        <section>
            <article>
                <h2>HTML5 Semantic Etiketler</h2>
                <time datetime="2024-01-15">15 Ocak 2024</time>
                <p>
                    HTML5 ile birlikte anlamsal etiketler eklendi. 
                    Bu etiketler sayfa yapısını daha anlamlı hale getirir.
                </p>
                <figure>
                    <img src="html5.jpg" alt="HTML5 Logo">
                    <figcaption>HTML5 Logo</figcaption>
                </figure>
                <p>
                    <mark>Semantic etiketler</mark> SEO ve erişilebilirlik 
                    açısından önemlidir.
                </p>
            </article>
            
            <article>
                <h2>CSS3 Yeni Özellikler</h2>
                <time datetime="2024-01-20">20 Ocak 2024</time>
                <p>
                    CSS3 ile birlikte flexbox, grid, animasyonlar gibi 
                    yeni özellikler eklendi.
                </p>
            </article>
        </section>
        
        <aside>
            <h3>Popüler Makaleler</h3>
            <ul>
                <li><a href="#">HTML5 Nedir?</a></li>
                <li><a href="#">CSS Flexbox</a></li>
                <li><a href="#">JavaScript ES6</a></li>
            </ul>
            
            <h3>Kategoriler</h3>
            <ul>
                <li><a href="#">HTML</a></li>
                <li><a href="#">CSS</a></li>
                <li><a href="#">JavaScript</a></li>
            </ul>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 Web Geliştirme Blogu. Tüm hakları saklıdır.</p>
        <p>
            Son Güncelleme: 
            <time datetime="2024-01-25">25 Ocak 2024</time>
        </p>
    </footer>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **SEO**: Semantic etiketler arama motorları için önemlidir.

2. **Erişilebilirlik**: Ekran okuyucular semantic yapıyı daha iyi anlar.

3. **Yapı**: Semantic etiketler sayfa yapısını daha anlamlı hale getirir.

4. **Tarayıcı Desteği**: Modern tarayıcılar semantic etiketleri destekler.

5. **CSS**: Semantic etiketler **CSS** ile stillendirilebilir.

## 🎯 İyi Pratikler

- Semantic etiketleri doğru yerlerde kullanın
- Her sayfada bir `<main>` etiketi kullanın
- `<header>` ve `<footer>` sayfa yapısı için kullanın
- `<article>` bağımsız içerikler için kullanın
- `<section>` içerik bölümleri için kullanın
- `<nav>` navigasyon için kullanın
- Anlamsal HTML kullanarak **SEO**'yu iyileştirin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


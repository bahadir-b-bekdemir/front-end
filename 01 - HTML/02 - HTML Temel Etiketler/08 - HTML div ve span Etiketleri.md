# 📦 HTML DIV VE SPAN ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) içeriği gruplamak ve düzenlemek için `<div>` ve `<span>` etiketleri kullanılır. Bu etiketler anlamsal değildir, sadece yapısal amaçlıdır.

## 📋 div ve span Etiketleri

### `<div>...</div>`

Block-level (blok seviyesi) bir kapsayıcı etikettir. Yeni satırda başlar ve tam genişlik kaplar.

### `<span>...</span>`

Inline-level (satır içi) bir kapsayıcı etikettir. Aynı satırda kalır ve sadece içeriği kadar yer kaplar.

**Temel fark:**
- `<div>` = Block-level (blok seviyesi)
- `<span>` = Inline-level (satır içi)

## 💡 Kullanım Örnekleri

### Temel div Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel div Kullanımı</title>
    <style>
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .box {
            background-color: #3498db;
            color: white;
            padding: 15px;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <h1>div Örnekleri</h1>
    
    <div class="container">
        <h2>Container 1</h2>
        <p>Bu bir div container'dır.</p>
    </div>
    
    <div class="container">
        <h2>Container 2</h2>
        <p>Bu başka bir div container'dır.</p>
    </div>
    
    <div class="box">Kutu 1</div>
    <div class="box">Kutu 2</div>
    <div class="box">Kutu 3</div>
</body>
</html>
```

### Temel span Kullanımı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel span Kullanımı</title>
    <style>
        .highlight {
            background-color: #fff3cd;
            padding: 2px 5px;
            border-radius: 3px;
        }
        
        .important {
            color: #e74c3c;
            font-weight: bold;
        }
        
        .code {
            font-family: 'Courier New', monospace;
            background-color: #f4f4f4;
            padding: 2px 5px;
        }
    </style>
</head>
<body>
    <h1>span Örnekleri</h1>
    
    <p>
        Bu metin içinde <span class="highlight">vurgulanmış</span> bir kısım var.
    </p>
    
    <p>
        Bu metin içinde <span class="important">önemli</span> bir kelime var.
    </p>
    
    <p>
        HTML etiketi: <span class="code">&lt;div&gt;</span>
    </p>
    
    <p>
        Fiyat: <span style="color: #27ae60; font-weight: bold;">100 TL</span>
    </p>
</body>
</html>
```

### div ile Sayfa Düzeni

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>div ile Sayfa Düzeni</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
        }
        
        .header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        .nav {
            background-color: #34495e;
            padding: 15px;
        }
        
        .nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            padding: 10px;
        }
        
        .content {
            display: flex;
            max-width: 1200px;
            margin: 20px auto;
            gap: 20px;
        }
        
        .main {
            flex: 2;
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
        }
        
        .sidebar {
            flex: 1;
            background-color: #ecf0f1;
            padding: 20px;
            border-radius: 5px;
        }
        
        .footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>Web Sitesi Başlığı</h1>
    </div>
    
    <div class="nav">
        <a href="#anasayfa">Ana Sayfa</a>
        <a href="#hakkimizda">Hakkımızda</a>
        <a href="#iletisim">İletişim</a>
    </div>
    
    <div class="content">
        <div class="main">
            <h2>Ana İçerik</h2>
            <p>Ana içerik burada yer alır.</p>
        </div>
        
        <div class="sidebar">
            <h3>Yan İçerik</h3>
            <p>Yan içerik burada yer alır.</p>
        </div>
    </div>
    
    <div class="footer">
        <p>&copy; 2024 Tüm hakları saklıdır.</p>
    </div>
</body>
</html>
```

### span ile Metin Stilleme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>span ile Metin Stilleme</title>
    <style>
        .highlight {
            background-color: #fff3cd;
            padding: 2px 5px;
            border-radius: 3px;
        }
        
        .error {
            color: #e74c3c;
            font-weight: bold;
        }
        
        .success {
            color: #27ae60;
            font-weight: bold;
        }
        
        .warning {
            color: #f39c12;
            font-weight: bold;
        }
        
        .info {
            color: #3498db;
            font-weight: bold;
        }
        
        .badge {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 15px;
            font-size: 0.85em;
            font-weight: bold;
        }
        
        .badge-primary {
            background-color: #3498db;
            color: white;
        }
        
        .badge-success {
            background-color: #27ae60;
            color: white;
        }
    </style>
</head>
<body>
    <h1>span ile Metin Stilleme</h1>
    
    <p>
        Bu metin içinde <span class="highlight">vurgulanmış</span> bir kısım var.
    </p>
    
    <p>
        Durum: <span class="error">Hata</span> | 
        <span class="success">Başarılı</span> | 
        <span class="warning">Uyarı</span> | 
        <span class="info">Bilgi</span>
    </p>
    
    <p>
        Etiketler: 
        <span class="badge badge-primary">HTML</span>
        <span class="badge badge-success">CSS</span>
        <span class="badge badge-primary">JavaScript</span>
    </p>
    
    <p>
        Fiyat: <span style="text-decoration: line-through; color: #999;">150 TL</span> 
        <span style="color: #27ae60; font-weight: bold; font-size: 1.2em;">100 TL</span>
    </p>
</body>
</html>
```

### div ve span Birlikte Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>div ve span Birlikte</title>
    <style>
        .card {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 20px;
            margin: 20px 0;
            background-color: white;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .card-header {
            border-bottom: 2px solid #3498db;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }
        
        .card-title {
            color: #2c3e50;
            font-size: 1.5em;
            margin: 0;
        }
        
        .card-meta {
            color: #7f8c8d;
            font-size: 0.9em;
        }
        
        .tag {
            display: inline-block;
            background-color: #ecf0f1;
            padding: 3px 8px;
            border-radius: 3px;
            font-size: 0.85em;
            margin: 2px;
        }
        
        .price {
            color: #27ae60;
            font-weight: bold;
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <h1>div ve span Birlikte Kullanım</h1>
    
    <div class="card">
        <div class="card-header">
            <h2 class="card-title">Ürün Adı</h2>
            <span class="card-meta">Yayın Tarihi: 15 Ocak 2024</span>
        </div>
        
        <p>Ürün açıklaması burada yer alır.</p>
        
        <div>
            <span class="tag">Elektronik</span>
            <span class="tag">Laptop</span>
            <span class="tag">Dell</span>
        </div>
        
        <div style="margin-top: 15px;">
            <span class="price">25.000 TL</span>
        </div>
    </div>
    
    <div class="card">
        <div class="card-header">
            <h2 class="card-title">Başka Bir Ürün</h2>
            <span class="card-meta">Yayın Tarihi: 20 Ocak 2024</span>
        </div>
        
        <p>Ürün açıklaması burada yer alır.</p>
        
        <div>
            <span class="tag">Telefon</span>
            <span class="tag">Samsung</span>
        </div>
        
        <div style="margin-top: 15px;">
            <span class="price">8.000 TL</span>
        </div>
    </div>
</body>
</html>
```

### Grid ve Flexbox ile div

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Grid ve Flexbox ile div</title>
    <style>
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        
        .grid-item {
            background-color: #3498db;
            color: white;
            padding: 30px;
            text-align: center;
            border-radius: 5px;
        }
        
        .flex-container {
            display: flex;
            gap: 15px;
            padding: 20px;
            background-color: #f8f9fa;
        }
        
        .flex-item {
            flex: 1;
            background-color: #27ae60;
            color: white;
            padding: 20px;
            text-align: center;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>Grid ve Flexbox ile div</h1>
    
    <h2>Grid Layout</h2>
    <div class="grid-container">
        <div class="grid-item">Öğe 1</div>
        <div class="grid-item">Öğe 2</div>
        <div class="grid-item">Öğe 3</div>
        <div class="grid-item">Öğe 4</div>
        <div class="grid-item">Öğe 5</div>
        <div class="grid-item">Öğe 6</div>
    </div>
    
    <h2>Flexbox Layout</h2>
    <div class="flex-container">
        <div class="flex-item">Öğe 1</div>
        <div class="flex-item">Öğe 2</div>
        <div class="flex-item">Öğe 3</div>
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
    <title>Kapsamlı div ve span Örneği</title>
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
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        
        .content-wrapper {
            display: flex;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .main-content {
            flex: 2;
        }
        
        .sidebar {
            flex: 1;
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
        }
        
        .card {
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid #3498db;
        }
        
        .card-title {
            color: #2c3e50;
            font-size: 1.3em;
        }
        
        .badge {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.85em;
            font-weight: bold;
        }
        
        .badge-new {
            background-color: #27ae60;
            color: white;
        }
        
        .badge-popular {
            background-color: #e74c3c;
            color: white;
        }
        
        .meta-info {
            color: #7f8c8d;
            font-size: 0.9em;
        }
        
        .meta-info span {
            margin-right: 15px;
        }
        
        .price {
            color: #27ae60;
            font-weight: bold;
            font-size: 1.5em;
        }
        
        .old-price {
            color: #999;
            text-decoration: line-through;
            font-size: 1em;
            margin-right: 10px;
        }
        
        .tags {
            margin-top: 15px;
        }
        
        .tag {
            display: inline-block;
            background-color: #ecf0f1;
            padding: 5px 10px;
            border-radius: 3px;
            font-size: 0.85em;
            margin: 3px;
        }
        
        .highlight {
            background-color: #fff3cd;
            padding: 2px 5px;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Web Geliştirme Ürünleri</h1>
            <p>En iyi kaynaklar ve araçlar</p>
        </div>
        
        <div class="content-wrapper">
            <div class="main-content">
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">HTML5 Kursu</h2>
                        <span class="badge badge-new">Yeni</span>
                    </div>
                    
                    <p>
                        Modern web geliştirme için <span class="highlight">HTML5</span> 
                        öğrenin. Semantic etiketler, formlar ve daha fazlası.
                    </p>
                    
                    <div class="meta-info">
                        <span>📅 15 Ocak 2024</span>
                        <span>👤 Ahmet Yılmaz</span>
                        <span>⭐ 4.8</span>
                    </div>
                    
                    <div class="tags">
                        <span class="tag">HTML</span>
                        <span class="tag">Web Geliştirme</span>
                        <span class="tag">Başlangıç</span>
                    </div>
                    
                    <div style="margin-top: 15px;">
                        <span class="old-price">200 TL</span>
                        <span class="price">150 TL</span>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">CSS3 Masterclass</h2>
                        <span class="badge badge-popular">Popüler</span>
                    </div>
                    
                    <p>
                        <span class="highlight">CSS3</span> ile modern web tasarımı. 
                        Flexbox, Grid, Animasyonlar ve daha fazlası.
                    </p>
                    
                    <div class="meta-info">
                        <span>📅 20 Ocak 2024</span>
                        <span>👤 Ayşe Demir</span>
                        <span>⭐ 4.9</span>
                    </div>
                    
                    <div class="tags">
                        <span class="tag">CSS</span>
                        <span class="tag">Tasarım</span>
                        <span class="tag">İleri Seviye</span>
                    </div>
                    
                    <div style="margin-top: 15px;">
                        <span class="price">180 TL</span>
                    </div>
                </div>
            </div>
            
            <div class="sidebar">
                <h3>Kategoriler</h3>
                <div>
                    <span class="tag">HTML</span>
                    <span class="tag">CSS</span>
                    <span class="tag">JavaScript</span>
                    <span class="tag">React</span>
                    <span class="tag">Vue.js</span>
                </div>
                
                <h3 style="margin-top: 20px;">Popüler Etiketler</h3>
                <div>
                    <span class="tag">Web Geliştirme</span>
                    <span class="tag">Frontend</span>
                    <span class="tag">Backend</span>
                    <span class="tag">Full Stack</span>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal HTML**: `<div>` ve `<span>` anlamsal değildir. Mümkün olduğunca semantic etiketler (`<header>`, `<nav>`, `<article>` vb.) kullanın.

2. **div vs span**: `<div>` block-level, `<span>` inline-level'dır.

3. **CSS**: `<div>` ve `<span>` genellikle **CSS** ile stillendirmek için kullanılır.

4. **Erişilebilirlik**: Anlamsal etiketler erişilebilirlik için daha iyidir.

5. **Kullanım**: `<div>` düzen için, `<span>` metin içi stilleme için kullanılır.

## 🎯 İyi Pratikler

- Semantic HTML'i tercih edin (`<div>` yerine `<section>`, `<article>` vb.)
- `<div>` düzen ve gruplama için kullanın
- `<span>` metin içi stilleme için kullanın
- Gereksiz `<div>` kullanımından kaçının
- CSS ile stillendirme yapın
- Erişilebilirlik için semantic etiketleri tercih edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


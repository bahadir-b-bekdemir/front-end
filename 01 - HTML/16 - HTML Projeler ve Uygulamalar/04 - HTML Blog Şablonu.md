# 📝 HTML BLOG ŞABLONU

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) blog şablonu içerik yönetimi için kullanılır.

## 📋 Blog Bölümleri

| Bölüm | Açıklama |
| :---- | :------- |
| Header | Logo ve navigasyon |
| Main | Blog yazıları |
| Sidebar | Kategoriler, arşiv |
| Footer | Footer bilgileri |

## 💡 Kullanım Örnekleri

### Blog Şablonu

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        header {
            background: #333;
            color: white;
            padding: 20px;
        }
        nav a {
            color: white;
            margin-right: 20px;
            text-decoration: none;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
        }
        main {
            flex: 2;
            padding: 20px;
        }
        aside {
            flex: 1;
            padding: 20px;
            background: #f4f4f4;
        }
        article {
            margin-bottom: 40px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Blog Başlığı</h1>
        <nav>
            <a href="/">Ana Sayfa</a>
            <a href="/about">Hakkında</a>
        </nav>
    </header>
    
    <div class="container">
        <main>
            <article>
                <h2>Blog Yazısı Başlığı</h2>
                <time>2024-01-15</time>
                <p>Blog yazısı içeriği...</p>
            </article>
        </main>
        
        <aside>
            <h3>Kategoriler</h3>
            <ul>
                <li><a href="/category/html">HTML</a></li>
                <li><a href="/category/css">CSS</a></li>
            </ul>
        </aside>
    </div>
    
    <footer style="background: #333; color: white; padding: 20px; text-align: center;">
        <p>&copy; 2024 Blog</p>
    </footer>
</body>
</html>
```

## 🎯 Önemli Notlar

- Semantic HTML kullanın
- Responsive tasarım uygulayın
- SEO optimizasyonu yapın
- Kategoriler ve etiketler ekleyin

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 💬 HTML YORUMLAR

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) kod içine açıklama eklemek ve kodları geçici olarak devre dışı bırakmak için yorumlar kullanılır. Yorumlar tarayıcıda görüntülenmez.

## 📋 Yorum Yapısı

HTML yorumları `<!--` ile başlar ve `-->` ile biter.

**Temel kullanım:**
```html
<!-- Bu bir HTML yorumudur -->
```

## 💡 Kullanım Örnekleri

### Basit Yorum

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Yorum Örneği</title>
</head>
<body>
    <!-- Bu sayfa ana sayfadır -->
    <h1>Hoş Geldiniz</h1>
    <p>Bu sayfaya hoş geldiniz.</p>
</body>
</html>
```

### Çok Satırlı Yorum

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çok Satırlı Yorum</title>
    <!--
        Bu bir çok satırlı yorumdur.
        Burada kod hakkında detaylı açıklamalar yapılabilir.
        Yorumlar tarayıcıda görüntülenmez.
    -->
</head>
<body>
    <h1>Başlık</h1>
    <p>İçerik</p>
</body>
</html>
```

### Kod Açıklamaları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kod Açıklamaları</title>
</head>
<body>
    <!-- Ana başlık bölümü -->
    <header>
        <h1>Web Sitesi Başlığı</h1>
    </header>
    
    <!-- Navigasyon menüsü -->
    <nav>
        <ul>
            <li><a href="#anasayfa">Ana Sayfa</a></li>
            <li><a href="#hakkimizda">Hakkımızda</a></li>
            <li><a href="#iletisim">İletişim</a></li>
        </ul>
    </nav>
    
    <!-- Ana içerik bölümü -->
    <main>
        <article>
            <h2>Makale Başlığı</h2>
            <p>Makale içeriği burada yer alır.</p>
        </article>
    </main>
    
    <!-- Alt bilgi bölümü -->
    <footer>
        <p>Telif Hakkı © 2024</p>
    </footer>
</body>
</html>
```

### Geçici Kod Devre Dışı Bırakma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kod Devre Dışı Bırakma</title>
</head>
<body>
    <h1>Aktif Başlık</h1>
    
    <!--
    <h2>Bu başlık geçici olarak devre dışı bırakıldı</h2>
    <p>Bu paragraf da görüntülenmeyecek</p>
    -->
    
    <h3>Başka bir başlık</h3>
    <p>Bu içerik görüntülenecek</p>
</body>
</html>
```

### Bölüm Açıklamaları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Bölüm Açıklamaları</title>
    <style>
        /* CSS yorumları farklıdır: /* ... */ */
        body {
            font-family: Arial, sans-serif;
        }
    </style>
</head>
<body>
    <!-- ============================================
         SAYFA BAŞLIĞI BÖLÜMÜ
         ============================================ -->
    <header>
        <h1>Web Sitesi</h1>
    </header>
    
    <!-- ============================================
         İÇERİK BÖLÜMÜ
         ============================================ -->
    <main>
        <section>
            <!-- Bu bölüm hakkında bilgi -->
            <h2>Bölüm 1</h2>
            <p>İçerik 1</p>
        </section>
        
        <section>
            <!-- Bu bölüm hakkında bilgi -->
            <h2>Bölüm 2</h2>
            <p>İçerik 2</p>
        </section>
    </main>
    
    <!-- ============================================
         ALT BİLGİ BÖLÜMÜ
         ============================================ -->
    <footer>
        <p>Telif Hakkı</p>
    </footer>
</body>
</html>
```

### Geliştirici Notları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Geliştirici Notları</title>
</head>
<body>
    <!-- 
        TODO: Bu bölümü daha sonra güncelle
        Tarih: 2024-01-15
        Geliştirici: Ahmet Yılmaz
    -->
    <section>
        <h2>Güncellenecek Bölüm</h2>
        <p>Bu bölüm yakında güncellenecek.</p>
    </section>
    
    <!-- 
        NOT: Bu form henüz test edilmedi
        Test tarihi: 2024-01-20
    -->
    <form>
        <input type="text" placeholder="İsim">
        <button type="submit">Gönder</button>
    </form>
    
    <!-- 
        HATA: Bu bölümde bir sorun var
        Çözüm: CSS ile düzeltilecek
    -->
    <div>
        <p>Bu bölüm düzeltilecek.</p>
    </div>
</body>
</html>
```

### İç İçe Yorumlar (Hatalı Kullanım)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>İç İçe Yorumlar</title>
</head>
<body>
    <!-- 
        Dış yorum
        <!-- İç yorum - BU ÇALIŞMAZ! -->
        Yorum devam ediyor
    -->
    <p>Bu kod çalışmayabilir çünkü HTML yorumları iç içe kullanılamaz.</p>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **İç İçe Yorumlar**: HTML yorumları iç içe kullanılamaz. İç yorum dış yorumu sonlandırır.

2. **Görünürlük**: Yorumlar tarayıcıda görüntülenmez, ancak kaynak kodunda görülebilir.

3. **Performans**: Yorumlar sayfa yükleme hızını çok az etkiler, ancak çok fazla yorum kullanmaktan kaçının.

4. **Güvenlik**: Yorumlarda hassas bilgiler (şifreler, API anahtarları vb.) saklamayın.

5. **CSS ve JavaScript Yorumları**: HTML yorumları (`<!-- -->`) sadece HTML için geçerlidir. **CSS** için `/* */` ve **JavaScript** için `//` veya `/* */` kullanılır.

## 🎯 İyi Pratikler

- Kodunuzu açıklamak için yorumları kullanın
- Karmaşık bölümler için açıklayıcı yorumlar ekleyin
- Geçici olarak kodları devre dışı bırakmak için yorumları kullanın
- Yorumları güncel tutun, eski yorumları silin
- Hassas bilgileri yorumlarda saklamayın
- Çok fazla yorum kullanmaktan kaçının, kod kendini açıklayıcı olmalıdır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


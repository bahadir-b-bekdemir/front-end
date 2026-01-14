# 🎨 HTML STYLE ETİKETİ VE INLINE CSS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) CSS stilleri `<style>` etiketi ile veya inline `style` özelliği ile uygulanabilir.

## 📋 CSS Ekleme Yöntemleri

| Yöntem | Etiket/Özellik | Kullanım |
| :----- | :------------- | :------- |
| Internal CSS | `<style>` | Head içinde |
| Inline CSS | `style` özelliği | Element içinde |
| External CSS | `<link>` | Dış dosya |

## 💡 Kullanım Örnekleri

### Style Etiketi (Internal CSS)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Internal CSS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
        }
        
        h1 {
            color: #333;
            text-align: center;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Başlık</h1>
        <p>İçerik</p>
    </div>
</body>
</html>
```

### Inline CSS

```html
<body>
    <h1 style="color: blue; font-size: 32px;">Başlık</h1>
    <p style="color: #666; line-height: 1.6;">Paragraf metni</p>
    <div style="background-color: yellow; padding: 20px;">
        İçerik
    </div>
</body>
```

### Media Queries ile Style

```html
<head>
    <style>
        body {
            font-size: 16px;
        }
        
        @media (max-width: 768px) {
            body {
                font-size: 14px;
            }
        }
        
        @media print {
            body {
                color: black;
                background: white;
            }
        }
    </style>
</head>
```

## 📱 HTML Style Etiketi İçerisinde Media (Medya) Kullanımı

**HTML**'in (Hyper Text Markup Language) (zengin metin işaretleme diline) style tag'ı (etiketi) içerisinde media (medya) özelliği kullanılarak, CSS (Cascading Style Sheets) (basamaklı stil şablonları veya basamaklı biçim sayfaları) kurallarının hangi medya türlerinde veya hangi koşullarda uygulanacağı belirlenebilmektedir.

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) style tag'ı (etiketi) içerisinde kullanılmakta olan media (medya) özelliği, o `<style>` bloğundaki tüm CSS kurallarının hangi medya türlerinde geçerli olacağını belirtir. Bu özellik, `<link>` etiketindeki `media` özelliğine benzer şekilde çalışır ve internal CSS (head içindeki `<style>` etiketi) için kullanılır.

### Media Özelliğinin Amacı

`<style>` etiketindeki `media` özelliği, tarayıcıya o stil bloğundaki CSS kurallarının hangi durumlarda uygulanması gerektiğini söyler. Bu sayede:
- Farklı medya türleri için farklı stil blokları oluşturulabilir
- Yazdırma için özel stiller tanımlanabilir
- Ekran boyutuna göre farklı stiller uygulanabilir
- Performans optimizasyonu sağlanabilir

### Media Özelliği İçin Kullanılan Değerler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) style tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan değerler:

| Value (Değer) | Description (Tanım) |
| :------------ | :------------------ |
| `all` | Tüm aygıtlar. Default (Varsayılan) değer. |
| `print` | Baskı ve yazdırma cihazları. |
| `screen` | Bilgisayar, tablet, akıllı telefon vb. |
| `speech` | Ses sentezleme veya ekran okuyucu cihazları. |

### Media Özelliği İçin Kullanılan Operatörler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) style tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan operatörler:

| Operator Name (Operatör Adı) | Description (Tanım) |
| :--------------------------- | :------------------ |
| `only` | Sadece operatörü. |
| `and` | Ve operatörü. |
| `not` | Değil operatörü. |
| `,` | Veya operatörü. |

### Media Özelliği İçin Kullanılan Ek Değerler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) style tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan ek değerler:

| Value (Değer) | Description (Tanım) |
| :------------ | :------------------ |
| `aspect-ratio` | Hedeflenen görüntü alanının genişlik ve yüksekliği. Minimum ve maksimum değerlerini de kullanılabilir. (`min-aspect-ratio`, `max-aspect-ratio`)<br>Örnek : `(min-aspect-ratio:16/9)` |
| `width` | Hedeflenen görüntü alanının genişliği. Minimum ve maksimum değerlerini de kullanılabilir. (`min-width`, `max-width`)<br>Örnek : `screen and (max-width:1200px)` |
| `height` | Hedeflenen görüntü alanının yüksekliği. Minimum ve maksimum değerlerini de kullanılabilir. (`min-height`, `max-height`)<br>Örnek : `screen and (max-height:800px)` |
| `resolution` | Hedeflenen ekranın veya kağıdın dpi veya dpcm türünde renk çözünürlüğü / yoğunluğu. Minimum ve maksimum değerlerini de kullanılabilir. (`min-resolution`, `max-resolution`)<br>Örnek : `print and (min-resolution:300dpi)` |
| `light-level` | Hedeflenen ekranın ışık seviyesi. Dim (Sönük), normal veya washed (parlak) değerlerini kullanılabilir.<br>Örnek : `(light-level:dim)` |
| `display-mode` | Hedeflenen uygulamanın görüntülenme modu. Fullscreen (Tam ekran), standalone (bağımsız), minimal-ui (minimum kullanıcı arayüzü) veya browser (tarayıcı) değerlerini kullanılabilir.<br>Örnek : `all and (display-mode:fullscreen)` |
| `color` | Hedeflenen ekranın renk başına bit sayısı. Minimum ve maksimum değerlerini de kullanılabilir. (`min-color`, `max-color`)<br>Örnek : `screen and (min-color:3)` |
| `color-index` | Hedeflenen ekranın işleyebileceği renk sayısı. Minimum ve maksimum değerlerini de kullanılabilir. (`min-color-index`, `max-color-index`)<br>Örnek : `screen and (min-color-index:256)` |
| `color-gamut` | Hedeflenen ekranın desteklediği renk gamı / yelpazesi. srgb, p3 veya rec2020 değerlerini kullanılabilir.<br>Örnek : `(color-gamut:srgb)` |
| `inverted-colors` | Hedeflenen cihazın OS (operating system) (işletim sistemi) renklerini tersine çevirebilmesi durumu. None (Yok) veya inverted (ters) değerlerini kullanılabilir.<br>Örnek : `(inverted-colors:inverted)` |
| `orientation` | Hedeflenen ekranın veya kağıdın yönü. Portrait (portre) veya landscape (manzara) değerlerini kullanılabilir.<br>Örnek : `all and (orientation:landscape)` |
| `monochrome` | Hedeflenen tek renkli ekranın (greyscale) (gri tonlama), piksel başına düşen bit sayısı. Minimum ve maksimum değerlerini de kullanılabilir. (`min-monochrome`, `max-monochrome`)<br>Örnek : `(monochrome)` (tek renkli cihaz) - `(monochrome:0)` (tek renkli olmayan cihaz) |
| `grid` | Hedeflenen cihazın kullandığı ekran (ızgara veya bitmap) tabanı. 0 veya 1 değerlerini kullanılabilir.<br>Örnek : `(grid:0)` |
| `scan` | Hedeflenen cihazın ekran tarama türü. Interlace (Karıştırarak) veya progressive (ilerleyerek) değerlerini kullanılabilir.<br>Örnek : `(scan:progressive)` |
| `update` | Hedeflenen cihazın görüntü yenileme sıklığı. Non (Olmayan), slow (yavaş) veya fast (hızlı) değerlerini kullanılabilir.<br>Örnek : `(update:fast)` |
| `scripting` | Hedeflenen cihazın komut dosyası kullanabilme durumu. None (Yok), initial-only (sadece başlangıçta) veya enabled (etkin) değerlerini kullanılabilir.<br>Örnek : `(scripting:enabled)` |
| `pointer` | Hedeflenen cihazın birincil giriş mekanizması işaretleme aygıtı ise. None (Yok), coarse (kalitesiz) veya fine (iyi) değerlerini kullanılabilir.<br>Örnek : `(pointer:fine)` |
| `any-pointer` | Hedeflenen cihazın kullanılabilir bir giriş mekanizması işaretleme aygıtı ise. None (Yok), coarse (kalitesiz) veya fine (iyi) değerlerini kullanılabilir.<br>Örnek : `(any-pointer:fine)` |
| `hover` | Hedeflenen cihazın birincil giriş mekanizması elementin üzerine gelebilme durumu. None (Yok) veya hover (üzerinde) değerlerini kullanılabilir.<br>Örnek : `(hover:hover)` |
| `any-hover` | Hedeflenen cihazın kullanılabilir bir giriş mekanizması elementin üzerine gelebilme durumu. None (Yok) veya hover (üzerinde) değerlerini kullanılabilir.<br>Örnek : `(any-hover:hover)` |
| `overflow-block` | Hedeflenen cihazın görüntüleme alanı blok eksenin boyunca taşan içerik durumu. None (Yok), scroll (kaydırma), optional-paged (isteğe bağlı sayfalı) veya paged (sayfalı) değerlerini kullanılabilir.<br>Örnek : `(overflow-block:scroll)` |
| `overflow-inline` | Hedeflenen cihazın görüntüleme alanı satır içi eksenin boyunca taşan içerik durumu. None (Yok) veya scroll (kaydırma) değerlerini kullanılabilir.<br>Örnek : `(overflow-inline:scroll)` |

### 💡 Kullanım Örnekleri

#### Temel Medya Türleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Style Media Özelliği</title>
    
    <!-- Tüm cihazlar için (varsayılan) -->
    <style media="all">
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
    </style>
    
    <!-- Sadece ekranlar için -->
    <style media="screen">
        body {
            background-color: #f5f5f5;
            color: #333;
        }
        
        h1 {
            color: #007bff;
        }
    </style>
    
    <!-- Yazdırma için -->
    <style media="print">
        body {
            background-color: white;
            color: black;
        }
        
        .no-print {
            display: none;
        }
    </style>
</head>
<body>
    <h1>Başlık</h1>
    <p>İçerik</p>
    <div class="no-print">Yazdırılmayacak içerik</div>
</body>
</html>
```

#### Ekran Genişliği Sorguları

```html
<head>
    <!-- Mobil cihazlar için (768px ve altı) -->
    <style media="screen and (max-width: 768px)">
        body {
            font-size: 14px;
            padding: 10px;
        }
        
        .sidebar {
            display: none;
        }
    </style>
    
    <!-- Masaüstü için (1025px ve üzeri) -->
    <style media="screen and (min-width: 1025px)">
        body {
            font-size: 16px;
            padding: 40px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
    </style>
</head>
```

#### Yönlendirme Sorguları

```html
<head>
    <!-- Dikey (portrait) yönlendirme -->
    <style media="screen and (orientation: portrait)">
        body {
            padding: 20px 10px;
        }
    </style>
    
    <!-- Yatay (landscape) yönlendirme -->
    <style media="screen and (orientation: landscape)">
        body {
            padding: 10px 20px;
        }
    </style>
</head>
```

#### Çözünürlük Sorguları

```html
<head>
    <!-- Yüksek çözünürlüklü ekranlar (Retina, 2x) -->
    <style media="screen and (min-resolution: 2dppx)">
        .logo {
            background-image: url('logo@2x.png');
        }
    </style>
    
    <!-- Yazdırma için yüksek çözünürlük -->
    <style media="print and (min-resolution: 300dpi)">
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
```

#### Karanlık Mod ve Tercihler

```html
<head>
    <!-- Varsayılan (açık) tema -->
    <style media="screen and (prefers-color-scheme: light)">
        body {
            background-color: white;
            color: black;
        }
    </style>
    
    <!-- Karanlık tema -->
    <style media="screen and (prefers-color-scheme: dark)">
        body {
            background-color: #1a1a1a;
            color: white;
        }
    </style>
    
    <!-- Animasyonsuz stil (erişilebilirlik) -->
    <style media="screen and (prefers-reduced-motion: reduce)">
        * {
            animation: none !important;
            transition: none !important;
        }
    </style>
</head>
```

#### Karmaşık Media Sorguları

```html
<head>
    <!-- Büyük ekranlı tabletler ve küçük masaüstü (landscape) -->
    <style media="screen and (min-width: 768px) and (max-width: 1024px) and (orientation: landscape)">
        .container {
            display: grid;
            grid-template-columns: 1fr 2fr;
        }
    </style>
    
    <!-- Yüksek çözünürlüklü mobil cihazlar -->
    <style media="screen and (max-width: 768px) and (min-resolution: 2dppx)">
        .icon {
            width: 48px;
            height: 48px;
        }
    </style>
</head>
```

#### Operatör Kullanımları

```html
<head>
    <!-- Ve (and) operatörü -->
    <style media="screen and (min-width: 768px) and (max-width: 1024px)">
        .tablet-layout {
            display: flex;
        }
    </style>
    
    <!-- Veya (,) operatörü -->
    <style media="screen, print">
        body {
            font-family: Arial, sans-serif;
        }
    </style>
    
    <!-- Değil (not) operatörü -->
    <style media="not print">
        .screen-only {
            display: block;
        }
    </style>
</head>
```

### 📍 Style Etiketi Media Özelliği Nereye Yerleştirilir?

Media özelliği `<style>` etiketi içerisinde, genellikle `<head>` bölümüne yerleştirilmelidir.

### ✅ Doğru Yerleşim

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
    
    <!-- Media özelliği ile style -->
    <style media="screen">
        body {
            background-color: #f5f5f5;
        }
    </style>
    
    <style media="print">
        body {
            background-color: white;
        }
    </style>
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### ⚠️ Önemli Notlar

1. **Media özelliği olmadan kullanım**: `media` özelliği belirtilmezse, stil bloğu varsayılan olarak `all` medya türü için geçerlidir, yani tüm durumlarda uygulanır.

2. **`@media` ile fark**: `<style media="...">` ile CSS içindeki `@media` kuralı farklıdır. `<style media="...">` tüm stil bloğunu etkiler, `@media` ise sadece belirli kuralları etkiler.

3. **Yazdırma stilleri**: `media="print"` kullanıldığında, sayfa yazdırıldığında veya yazdırma önizlemesi açıldığında stil uygulanır.

4. **Performans**: Media sorgusu eşleşmeyen stil blokları yine de yüklenir, ancak uygulanmaz.

5. **Tarayıcı desteği**: Modern tarayıcıların tümü `<style>` etiketindeki `media` özelliğini destekler.

### 🎯 İyi Pratikler

- ✅ Yazdırma için özel stiller oluştururken `media="print"` kullanın
- ✅ Responsive tasarım için ekran boyutuna göre farklı stil blokları kullanın
- ✅ Karanlık mod desteği için `prefers-color-scheme` kullanın
- ✅ Erişilebilirlik için `prefers-reduced-motion` kullanın
- ✅ Karmaşık media sorgularında operatörleri doğru kullanın
- ❌ Tüm cihazlar için geçerli stiller için `media` özelliğini kullanmayın (gereksiz)
- ❌ Çok fazla farklı stil bloğu oluşturmaktan kaçının (bakım zorluğu)

### CSS Variables (Custom Properties)

```html
<head>
    <style>
        :root {
            --primary-color: #007bff;
            --secondary-color: #6c757d;
            --font-size: 16px;
        }
        
        h1 {
            color: var(--primary-color);
            font-size: var(--font-size);
        }
    </style>
</head>
```

### Scoped Style (Deprecated - Artık Desteklenmiyor)

⚠️ **Önemli Not**: `scoped` özelliği HTML5 spesifikasyonundan kaldırılmıştır ve modern tarayıcılar tarafından desteklenmemektedir. Bu özellik artık kullanılmamalıdır.

**Eski kullanım (artık çalışmaz):**
```html
<body>
    <article>
        <style scoped>
            h2 {
                color: red;
            }
        </style>
        <h2>Bu başlık kırmızı</h2>
    </article>
    
    <section>
        <h2>Bu başlık normal</h2>
    </section>
</body>
```

**Alternatif çözüm (CSS Modules veya class-based):**
```html
<head>
    <style>
        .article-scoped h2 {
            color: red;
        }
    </style>
</head>
<body>
    <article class="article-scoped">
        <h2>Bu başlık kırmızı</h2>
    </article>
    
    <section>
        <h2>Bu başlık normal</h2>
    </section>
</body>
```

### Conditional CSS

```html
<head>
    <style>
        /* Varsayılan stil */
        .box {
            width: 100px;
            height: 100px;
            background: blue;
        }
        
        /* JavaScript ile değiştirilebilir */
        .box.active {
            background: red;
        }
    </style>
</head>
<body>
    <div class="box" id="box"></div>
    <script>
        document.getElementById('box').classList.add('active');
    </script>
</body>
```

## 🎯 Best Practices

- Büyük projelerde external CSS kullanın
- Küçük, sayfa-spesifik stiller için `<style>` kullanın
- Inline CSS'i mümkün olduğunca az kullanın
- CSS variables kullanarak tema yönetimi yapın
- Media queries ile responsive tasarım uygulayın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


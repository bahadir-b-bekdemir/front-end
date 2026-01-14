# 📱 HTML'İN LINK TAG'I (ETİKETİ) İÇERİSİNDE MEDIA (MEDYA) KULLANIMI

**HTML**'in (Hyper Text Markup Language) (zengin metin işaretleme diline) link tag'ı (etiketi) içerisinde media (medya) özelliği kullanılarak atanacak olan tip, değer yada değerlere göre CSS (Cascading Style Sheets) (basamaklı stil şablonları veya basamaklı biçim sayfaları) dosyalarının çalışma durumları belirlenebilmekte ve aynı zamanda duyarlı web yazılımları yapılabilmektedir.

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) link tag'ı (etiketi) içerisinde kullanılmakta olan media (medya) özelliği, bir kaynağın hangi medya türlerinde veya hangi koşullarda yükleneceğini ve kullanılacağını belirtmek için kullanılır. Bu özellik özellikle CSS dosyaları için performans optimizasyonu ve farklı cihazlar için özelleştirilmiş stiller sağlamak amacıyla kullanılır.

## 📋 Media Özelliği İçin Kullanılan Değerler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) link tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan değerler:

| Value (Değer) | Description (Tanım) |
| :------------ | :------------------ |
| `all` | Tüm aygıtlar. Default (Varsayılan) değer. |
| `print` | Baskı ve yazdırma cihazları. |
| `screen` | Bilgisayar, tablet, akıllı telefon vb. |
| `speech` | Ses sentezleme veya ekran okuyucu cihazları. |

## 🔧 Media Özelliği İçin Kullanılan Operatörler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) link tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan operatörler:

| Operator Name (Operatör Adı) | Description (Tanım) |
| :--------------------------- | :------------------ |
| `only` | Sadece operatörü. |
| `and` | Ve operatörü. |
| `not` | Değil operatörü. |
| `,` | Veya operatörü. |

## 📐 Media Özelliği İçin Kullanılan Ek Değerler

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) link tag'ı (etiketi) içerisinde media (medya) özelliği için kullanılan ek değerler:

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

## 💡 Kullanım Örnekleri

### Temel Medya Türleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Özelliği Örnekleri</title>
    
    <!-- Tüm cihazlar için (varsayılan) -->
    <link rel="stylesheet" href="style.css" media="all">
    
    <!-- Sadece ekranlar için -->
    <link rel="stylesheet" href="screen.css" media="screen">
    
    <!-- Yazdırma için -->
    <link rel="stylesheet" href="print.css" media="print">
    
    <!-- Ekran okuyucular için -->
    <link rel="stylesheet" href="speech.css" media="speech">
</head>
<body>
    <h1>Media Özelliği Örnekleri</h1>
</body>
</html>
```

### Ekran Genişliği Sorguları

```html
<head>
    <!-- Mobil cihazlar için (768px ve altı) -->
    <link rel="stylesheet" href="mobile.css" media="screen and (max-width: 768px)">
    
    <!-- Tablet cihazlar için (769px - 1024px) -->
    <link rel="stylesheet" href="tablet.css" media="screen and (min-width: 769px) and (max-width: 1024px)">
    
    <!-- Masaüstü için (1025px ve üzeri) -->
    <link rel="stylesheet" href="desktop.css" media="screen and (min-width: 1025px)">
    
    <!-- Küçük ekranlar için (480px ve altı) -->
    <link rel="stylesheet" href="small.css" media="screen and (max-width: 480px)">
</head>
```

### Yönlendirme Sorguları

```html
<head>
    <!-- Dikey (portrait) yönlendirme -->
    <link rel="stylesheet" href="portrait.css" media="screen and (orientation: portrait)">
    
    <!-- Yatay (landscape) yönlendirme -->
    <link rel="stylesheet" href="landscape.css" media="screen and (orientation: landscape)">
</head>
```

### Çözünürlük Sorguları

```html
<head>
    <!-- Yüksek çözünürlüklü ekranlar (Retina, 2x) -->
    <link rel="stylesheet" href="retina.css" media="screen and (min-resolution: 2dppx)">
    
    <!-- Yazdırma için yüksek çözünürlük -->
    <link rel="stylesheet" href="high-res-print.css" media="print and (min-resolution: 300dpi)">
</head>
```

### Renk ve Görüntü Özellikleri

```html
<head>
    <!-- Renkli ekranlar -->
    <link rel="stylesheet" href="color.css" media="screen and (color)">
    
    <!-- Siyah-beyaz ekranlar -->
    <link rel="stylesheet" href="monochrome.css" media="screen and (monochrome)">
    
    <!-- Yüksek renk derinliği -->
    <link rel="stylesheet" href="high-color.css" media="screen and (min-color: 8)">
</head>
```

### Karanlık Mod ve Tercihler

```html
<head>
    <!-- Varsayılan (açık) tema -->
    <link rel="stylesheet" href="light.css" media="screen and (prefers-color-scheme: light)">
    
    <!-- Karanlık tema -->
    <link rel="stylesheet" href="dark.css" media="screen and (prefers-color-scheme: dark)">
    
    <!-- Animasyonlu stil (varsayılan) -->
    <link rel="stylesheet" href="animated.css" media="screen and (prefers-reduced-motion: no-preference)">
    
    <!-- Animasyonsuz stil (erişilebilirlik) -->
    <link rel="stylesheet" href="static.css" media="screen and (prefers-reduced-motion: reduce)">
</head>
```

### Giriş Mekanizması Sorguları

```html
<head>
    <!-- Dokunmatik ekranlar (kalem veya parmak) -->
    <link rel="stylesheet" href="touch.css" media="screen and (pointer: coarse)">
    
    <!-- Fare veya trackpad -->
    <link rel="stylesheet" href="mouse.css" media="screen and (pointer: fine)">
    
    <!-- Hover desteği olan cihazlar -->
    <link rel="stylesheet" href="hover.css" media="screen and (hover: hover)">
</head>
```

### Karmaşık Media Sorguları

```html
<head>
    <!-- Büyük ekranlı tabletler ve küçük masaüstü (landscape) -->
    <link rel="stylesheet" href="tablet-landscape.css" 
          media="screen and (min-width: 768px) and (max-width: 1024px) and (orientation: landscape)">
    
    <!-- Yüksek çözünürlüklü mobil cihazlar -->
    <link rel="stylesheet" href="retina-mobile.css" 
          media="screen and (max-width: 768px) and (min-resolution: 2dppx)">
    
    <!-- Büyük ekranlar ve yatay yönlendirme -->
    <link rel="stylesheet" href="large-landscape.css" 
          media="screen and (min-width: 1200px) and (orientation: landscape)">
    
    <!-- Yazdırma ve yüksek çözünürlük -->
    <link rel="stylesheet" href="print-high-res.css" 
          media="print and (min-resolution: 300dpi)">
</head>
```

### Operatör Kullanımları

```html
<head>
    <!-- Ve (and) operatörü -->
    <link rel="stylesheet" href="tablet.css" 
          media="screen and (min-width: 768px) and (max-width: 1024px)">
    
    <!-- Veya (,) operatörü -->
    <link rel="stylesheet" href="screen-print.css" 
          media="screen, print">
    
    <!-- Değil (not) operatörü -->
    <link rel="stylesheet" href="no-print.css" 
          media="not print">
    
    <!-- Sadece (only) operatörü -->
    <link rel="stylesheet" href="only-screen.css" 
          media="only screen">
</head>
```

## 📍 Media Özelliği Nereye Yerleştirilir?

Media özelliği `<link>` etiketi içerisinde, `<head>` bölümüne yerleştirilmelidir.

### ✅ Doğru Yerleşim

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
    
    <!-- Media özelliği ile CSS -->
    <link rel="stylesheet" href="style.css" media="screen">
    <link rel="stylesheet" href="print.css" media="print">
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### ❌ Yanlış Yerleşim

```html
<!-- YANLIŞ: Media özelliği body içinde -->
<body>
    <link rel="stylesheet" href="style.css" media="screen">
</body>

<!-- YANLIŞ: Link etiketi head dışında -->
<html>
    <link rel="stylesheet" href="style.css" media="screen">
</html>
```

## ⚠️ Önemli Notlar

1. **Media özelliği olmadan kullanım**: `media` özelliği belirtilmezse, kaynak varsayılan olarak `all` medya türü için yüklenir, yani tüm durumlarda geçerlidir.

2. **Performans avantajı**: Media sorgusu eşleşmeyen kaynaklar yine de indirilir, ancak uygulanmaz. Bu nedenle kritik olmayan stiller için `media` kullanmak faydalıdır.

3. **Yazdırma stilleri**: `media="print"` kullanıldığında, sayfa yazdırıldığında veya yazdırma önizlemesi açıldığında stil uygulanır.

4. **CSS Media Queries ile fark**: `<link>` etiketindeki `media` özelliği ile CSS içindeki `@media` kuralı farklıdır. `<link>` etiketi kaynağın yüklenip yüklenmeyeceğini kontrol eder, CSS'teki `@media` ise yüklenmiş stillerin uygulanıp uygulanmayacağını kontrol eder.

5. **Tarayıcı desteği**: Modern tarayıcıların tümü `media` özelliğini ve Media Queries'i destekler.

## 🎯 İyi Pratikler

- ✅ Yazdırma için özel stiller oluştururken `media="print"` kullanın
- ✅ Responsive tasarım için ekran boyutuna göre farklı CSS dosyaları kullanın
- ✅ Karanlık mod desteği için `prefers-color-scheme` kullanın
- ✅ Erişilebilirlik için `prefers-reduced-motion` kullanın
- ✅ Mobil cihazlar için gereksiz kaynakları yüklemekten kaçının
- ✅ Karmaşık media sorgularında operatörleri doğru kullanın
- ❌ Tüm cihazlar için geçerli stiller için `media` özelliğini kullanmayın (gereksiz)
- ❌ Çok fazla farklı CSS dosyası oluşturmaktan kaçının (bakım zorluğu)

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

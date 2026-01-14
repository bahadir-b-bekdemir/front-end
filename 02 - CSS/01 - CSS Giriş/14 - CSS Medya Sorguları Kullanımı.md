# 📱 CSS'DE MEDIA (MEDYA) SORGULARI KULLANIMI

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) media (medya) sorgularını ve özellikleri ile birlikte değerlerini kullanarak, atanacak olan tip, değer veya değerlere göre CSS kodlarının çalışma durumları belirlenebilmekte ve aynı zamanda **duyarlı (responsive) web yazılımları** yapılabilmektedir.

## 🎯 Media Query Nedir?

Media query'ler, farklı cihazlar ve ekran boyutları için farklı CSS stilleri uygulamanıza olanak tanır. Bu sayede web siteniz mobil, tablet ve masaüstü cihazlarda optimal görünüm sağlar.

---

## 📋 Media Type (Medya Türleri)

CSS'de media sorguları için kullanılan medya türleri:

| Değer | Açıklama |
|-------|----------|
| `all` | Tüm aygıtlar. Default (Varsayılan) değer. |
| `print` | Baskı ve yazdırma cihazları. |
| `screen` | Bilgisayar, tablet, akıllı telefon vb. ekran cihazları. |
| `speech` | Ses sentezleme veya ekran okuyucu cihazları. |

### 💡 Örnekler

```css
/* Tüm cihazlar için */
@media all {
    body { font-size: 16px; }
}

/* Sadece ekran cihazları için */
@media screen {
    .container { max-width: 1200px; }
}

/* Yazdırma için */
@media print {
    .no-print { display: none; }
    body { color: black; background: white; }
}

/* Ekran okuyucular için */
@media speech {
    .skip-link { display: block; }
}
```

---

## 🔧 Media Query Operatörleri

CSS'de media sorguları için kullanılan operatörler:

| Operatör | Açıklama | Örnek |
|----------|----------|-------|
| `and` | Ve operatörü - Tüm koşulların sağlanması gerekir | `screen and (max-width: 768px)` |
| `,` (virgül) | Veya operatörü - Koşullardan birinin sağlanması yeterlidir | `screen, print` |
| `not` | Değil operatörü - Koşulun tersini kontrol eder | `not screen` |
| `only` | Sadece operatörü - Eski tarayıcılarda sorguyu gizler | `only screen` |

### 💡 Örnekler

```css
/* AND operatörü - Her iki koşul da sağlanmalı */
@media screen and (max-width: 768px) {
    .menu { display: none; }
}

/* OR operatörü - Koşullardan biri sağlanmalı */
@media screen, print {
    body { font-family: Arial; }
}

/* NOT operatörü - Koşulun tersi */
@media not screen {
    .video { display: none; }
}

/* ONLY operatörü - Eski tarayıcı desteği */
@media only screen and (min-width: 768px) {
    .desktop-only { display: block; }
}
```

---

## 📐 Media Features (Medya Özellikleri)

### 🖥️ Boyut ve Görünüm Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `width` | Hedeflenen görüntü alanının genişliği | `(width: 768px)` |
| `min-width` | Minimum genişlik | `(min-width: 768px)` |
| `max-width` | Maksimum genişlik | `(max-width: 1200px)` |
| `height` | Hedeflenen görüntü alanının yüksekliği | `(height: 600px)` |
| `min-height` | Minimum yükseklik | `(min-height: 400px)` |
| `max-height` | Maksimum yükseklik | `(max-height: 800px)` |
| `aspect-ratio` | Genişlik/yükseklik oranı | `(aspect-ratio: 16/9)` |
| `min-aspect-ratio` | Minimum en-boy oranı | `(min-aspect-ratio: 16/9)` |
| `max-aspect-ratio` | Maksimum en-boy oranı | `(max-aspect-ratio: 4/3)` |
| `orientation` | Ekran yönü (portrait/landscape) | `(orientation: landscape)` |

### 💡 Boyut Örnekleri

```css
/* Mobil cihazlar (768px ve altı) */
@media screen and (max-width: 768px) {
    .container { padding: 10px; }
    .menu { flex-direction: column; }
}

/* Tablet cihazlar (768px - 1024px) */
@media screen and (min-width: 768px) and (max-width: 1024px) {
    .container { padding: 20px; }
}

/* Masaüstü cihazlar (1024px ve üzeri) */
@media screen and (min-width: 1024px) {
    .container { max-width: 1200px; margin: 0 auto; }
}

/* Yükseklik kontrolü */
@media screen and (max-height: 600px) {
    .header { height: 50px; }
}

/* Yön kontrolü */
@media screen and (orientation: portrait) {
    .sidebar { display: none; }
}

@media screen and (orientation: landscape) {
    .sidebar { display: block; }
}
```

### 🎨 Renk ve Görüntü Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `color` | Renk başına bit sayısı | `(min-color: 8)` |
| `min-color` | Minimum renk derinliği | `(min-color: 8)` |
| `max-color` | Maksimum renk derinliği | `(max-color: 24)` |
| `color-index` | İşlenebilecek renk sayısı | `(min-color-index: 256)` |
| `min-color-index` | Minimum renk sayısı | `(min-color-index: 256)` |
| `max-color-index` | Maksimum renk sayısı | `(max-color-index: 65536)` |
| `color-gamut` | Desteklenen renk gamı | `(color-gamut: p3)` |
| `monochrome` | Tek renkli ekran bit sayısı | `(monochrome: 0)` |
| `min-monochrome` | Minimum monochrome bit | `(min-monochrome: 0)` |
| `max-monochrome` | Maksimum monochrome bit | `(max-monochrome: 8)` |

### 💡 Renk Örnekleri

```css
/* Yüksek renk derinliği olan ekranlar */
@media screen and (min-color: 8) {
    .gradient { background: linear-gradient(...); }
}

/* Geniş renk gamı desteği */
@media (color-gamut: p3) {
    .vibrant { color: color(display-p3 1 0 0); }
}
```

### 🔍 Çözünürlük ve Kalite Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `resolution` | DPI veya DPCM cinsinden çözünürlük | `(min-resolution: 300dpi)` |
| `min-resolution` | Minimum çözünürlük | `(min-resolution: 300dpi)` |
| `max-resolution` | Maksimum çözünürlük | `(max-resolution: 600dpi)` |

### 💡 Çözünürlük Örnekleri

```css
/* Yüksek çözünürlüklü ekranlar (Retina) */
@media screen and (min-resolution: 192dpi) {
    .logo { background-image: url('logo@2x.png'); }
}

/* Yazdırma için yüksek çözünürlük */
@media print and (min-resolution: 300dpi) {
    .print-image { width: 100%; }
}
```

### 🌟 Görüntüleme ve Etkileşim Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `display-mode` | Uygulama görüntülenme modu | `(display-mode: fullscreen)` |
| `pointer` | Birincil işaretleme aygıtı | `(pointer: fine)` |
| `any-pointer` | Herhangi bir işaretleme aygıtı | `(any-pointer: coarse)` |
| `hover` | Hover desteği | `(hover: hover)` |
| `any-hover` | Herhangi bir hover desteği | `(any-hover: hover)` |
| `light-level` | Ekran ışık seviyesi | `(light-level: dim)` |
| `inverted-colors` | Renk tersine çevirme | `(inverted-colors: inverted)` |

### 💡 Etkileşim Örnekleri

```css
/* Dokunmatik cihazlar (kalın işaretçi) */
@media (pointer: coarse) {
    .button { min-height: 44px; min-width: 44px; }
}

/* Mouse kullanılan cihazlar (ince işaretçi) */
@media (pointer: fine) {
    .tooltip { display: block; }
}

/* Hover desteği olan cihazlar */
@media (hover: hover) {
    .link:hover { text-decoration: underline; }
}

/* Hover desteği olmayan cihazlar */
@media (hover: none) {
    .link { text-decoration: underline; }
}

/* Tam ekran modu */
@media (display-mode: fullscreen) {
    .fullscreen-content { display: block; }
}
```

### 📄 Diğer Özellikler

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `grid` | Izgara veya bitmap ekran | `(grid: 0)` |
| `scan` | Tarama türü (interlace/progressive) | `(scan: progressive)` |
| `update` | Görüntü yenileme sıklığı | `(update: fast)` |
| `scripting` | Komut dosyası desteği | `(scripting: enabled)` |
| `overflow-block` | Blok eksen taşma durumu | `(overflow-block: scroll)` |
| `overflow-inline` | Satır içi eksen taşma durumu | `(overflow-inline: scroll)` |

---

## 📱 Responsive Breakpoints (Duyarlı Kırılma Noktaları)

Responsive tasarım için yaygın kullanılan breakpoint'ler:

### 💡 Standart Breakpoint'ler

```css
/* Küçük mobil cihazlar (320px - 480px) */
@media screen and (max-width: 480px) {
    .container { padding: 10px; }
}

/* Mobil cihazlar (481px - 768px) */
@media screen and (min-width: 481px) and (max-width: 768px) {
    .container { padding: 15px; }
}

/* Tablet cihazlar (769px - 1024px) */
@media screen and (min-width: 769px) and (max-width: 1024px) {
    .container { padding: 20px; }
}

/* Küçük masaüstü (1025px - 1200px) */
@media screen and (min-width: 1025px) and (max-width: 1200px) {
    .container { max-width: 1140px; }
}

/* Büyük masaüstü (1201px ve üzeri) */
@media screen and (min-width: 1201px) {
    .container { max-width: 1320px; }
}
```

### 💡 Mobile-First Yaklaşımı (Önerilen)

```css
/* Mobil önce (varsayılan) */
.container {
    width: 100%;
    padding: 10px;
}

/* Tablet ve üzeri */
@media screen and (min-width: 768px) {
    .container {
        max-width: 750px;
        padding: 20px;
    }
}

/* Masaüstü ve üzeri */
@media screen and (min-width: 1024px) {
    .container {
        max-width: 1200px;
        padding: 30px;
    }
}

/* Büyük ekranlar */
@media screen and (min-width: 1440px) {
    .container {
        max-width: 1320px;
    }
}
```

---

## 💡 Pratik Örnekler

### Örnek 1: Responsive Navigation (Duyarlı Menü)

```css
/* Mobil - Hamburger menü */
.nav-menu {
    display: none;
}

.menu-toggle {
    display: block;
}

/* Tablet ve üzeri - Yatay menü */
@media screen and (min-width: 768px) {
    .nav-menu {
        display: flex;
    }
    
    .menu-toggle {
        display: none;
    }
}
```

### Örnek 2: Responsive Grid (Duyarlı Izgara)

```css
/* Mobil - Tek sütun */
.grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}

/* Tablet - İki sütun */
@media screen and (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Masaüstü - Üç sütun */
@media screen and (min-width: 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

### Örnek 3: Yazdırma Stilleri

```css
/* Yazdırma için özel stiller */
@media print {
    /* Gereksiz elementleri gizle */
    .no-print,
    .header,
    .footer,
    .sidebar {
        display: none;
    }
    
    /* Sayfa düzeni */
    body {
        color: black;
        background: white;
    }
    
    /* Sayfa sonlarını kontrol et */
    .page-break {
        page-break-after: always;
    }
    
    /* Linkleri göster */
    a::after {
        content: " (" attr(href) ")";
    }
}
```

### Örnek 4: Dark Mode (Karanlık Mod)

```css
/* Varsayılan (açık mod) */
body {
    background-color: white;
    color: black;
}

/* Karanlık mod desteği */
@media (prefers-color-scheme: dark) {
    body {
        background-color: #1a1a1a;
        color: white;
    }
}
```

### Örnek 5: Reduced Motion (Azaltılmış Hareket)

```css
/* Varsayılan animasyonlar */
.element {
    transition: transform 0.3s ease;
}

/* Hareket tercihini azaltan kullanıcılar için */
@media (prefers-reduced-motion: reduce) {
    .element {
        transition: none;
    }
    
    * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
    }
}
```

---

## 🎯 Best Practices (En İyi Uygulamalar)

### 1. **Mobile-First Yaklaşımı**

```css
/* ✅ İyi - Mobil önce */
.container {
    width: 100%;
}

@media (min-width: 768px) {
    .container {
        max-width: 750px;
    }
}

/* ❌ Kötü - Desktop önce */
.container {
    max-width: 1200px;
}

@media (max-width: 767px) {
    .container {
        width: 100%;
    }
}
```

### 2. **Breakpoint'leri Değişkenlerde Tutun**

```css
:root {
    --breakpoint-mobile: 480px;
    --breakpoint-tablet: 768px;
    --breakpoint-desktop: 1024px;
}

@media (min-width: var(--breakpoint-tablet)) {
    /* Tablet stilleri */
}
```

### 3. **Container Queries Kullanın (Modern CSS)**

```css
/* Container query - Element boyutuna göre */
@container (min-width: 500px) {
    .card {
        display: grid;
        grid-template-columns: 1fr 2fr;
    }
}
```

### 4. **Yazdırma Stillerini Unutmayın**

```css
@media print {
    * {
        background: white !important;
        color: black !important;
    }
}
```

---

## ⚠️ Önemli Notlar

1. **Viewport Meta Tag:** Media query'lerin düzgün çalışması için HTML'de viewport meta tag'i olmalıdır:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

2. **Min-Width vs Max-Width:** 
   - `min-width`: "Bu genişlik ve üzeri için"
   - `max-width`: "Bu genişlik ve altı için"

3. **Modern Özellikler:** Bazı media feature'lar (örneğin `prefers-color-scheme`, `prefers-reduced-motion`) modern tarayıcılarda desteklenir.

4. **Container Queries:** CSS Container Queries, element boyutuna göre stiller uygulamanıza olanak tanır (daha esnek).

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

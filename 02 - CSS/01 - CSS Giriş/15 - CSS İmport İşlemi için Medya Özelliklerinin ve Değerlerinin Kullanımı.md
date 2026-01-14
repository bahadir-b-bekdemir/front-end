# 📥 CSS'DE IMPORT İŞLEMİ İÇİN MEDIA (MEDYA) ÖZELLİKLERİNİN VE DEĞERLERİNİN KULLANIMI

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) `@import` işlemi için media (medya) özelliklerini ve değerlerini kullanarak, atanacak olan tip, değer veya değerlere göre CSS dosyalarının çalışma durumları belirlenebilmekte ve aynı zamanda **duyarlı (responsive) web yazılımları** yapılabilmektedir.

## 🎯 @import Nedir?

`@import` kuralı, bir CSS dosyasından başka bir CSS dosyasını içe aktarmanıza olanak tanır. Media query'ler ile birlikte kullanıldığında, belirli koşullarda hangi CSS dosyalarının yükleneceğini kontrol edebilirsiniz.

## 📋 @import Sözdizimi

```css
@import url("dosya.css") media-query;
@import "dosya.css" media-query;
```

### 💡 Temel Kullanım

```css
/* Tüm cihazlar için */
@import url("styles.css");

/* Sadece ekran cihazları için */
@import url("screen.css") screen;

/* Yazdırma için */
@import url("print.css") print;
```

---

## 📱 Media Type (Medya Türleri) ile @import

CSS'de `@import` işleminde media özelliği için kullanılan medya türleri:

| Değer | Açıklama | Örnek |
|-------|----------|-------|
| `all` | Tüm aygıtlar. Default (Varsayılan) değer. | `@import "styles.css" all;` |
| `print` | Baskı ve yazdırma cihazları. | `@import "print.css" print;` |
| `screen` | Bilgisayar, tablet, akıllı telefon vb. ekran cihazları. | `@import "screen.css" screen;` |
| `speech` | Ses sentezleme veya ekran okuyucu cihazları. | `@import "speech.css" speech;` |

### 💡 Örnekler

```css
/* Tüm cihazlar için (varsayılan) */
@import url("base.css") all;

/* Sadece ekran cihazları için */
@import url("screen-styles.css") screen;

/* Yazdırma için */
@import url("print-styles.css") print;

/* Ekran okuyucular için */
@import url("a11y.css") speech;
```

---

## 🔧 Operatörler ile @import

CSS'de `@import` işleminde media özelliği için kullanılan operatörler:

| Operatör | Açıklama | Örnek |
|----------|----------|-------|
| `and` | Ve operatörü - Tüm koşulların sağlanması gerekir | `@import "mobile.css" screen and (max-width: 768px);` |
| `,` (virgül) | Veya operatörü - Koşullardan birinin sağlanması yeterlidir | `@import "styles.css" screen, print;` |
| `not` | Değil operatörü - Koşulun tersini kontrol eder | `@import "styles.css" not print;` |
| `only` | Sadece operatörü - Eski tarayıcılarda sorguyu gizler | `@import "styles.css" only screen;` |

### 💡 Örnekler

```css
/* AND operatörü */
@import url("mobile.css") screen and (max-width: 768px);
@import url("tablet.css") screen and (min-width: 769px) and (max-width: 1024px);

/* OR operatörü */
@import url("styles.css") screen, print;

/* NOT operatörü */
@import url("styles.css") not print;

/* ONLY operatörü */
@import url("styles.css") only screen and (min-width: 768px);
```

---

## 📐 Media Features (Medya Özellikleri) ile @import

### 🖥️ Boyut ve Görünüm Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `width` | Hedeflenen görüntü alanının genişliği | `@import "styles.css" screen and (width: 768px);` |
| `min-width` | Minimum genişlik | `@import "desktop.css" screen and (min-width: 1024px);` |
| `max-width` | Maksimum genişlik | `@import "mobile.css" screen and (max-width: 768px);` |
| `height` | Hedeflenen görüntü alanının yüksekliği | `@import "styles.css" screen and (height: 600px);` |
| `min-height` | Minimum yükseklik | `@import "styles.css" screen and (min-height: 400px);` |
| `max-height` | Maksimum yükseklik | `@import "styles.css" screen and (max-height: 800px);` |
| `aspect-ratio` | Genişlik/yükseklik oranı | `@import "styles.css" screen and (aspect-ratio: 16/9);` |
| `min-aspect-ratio` | Minimum en-boy oranı | `@import "styles.css" screen and (min-aspect-ratio: 16/9);` |
| `max-aspect-ratio` | Maksimum en-boy oranı | `@import "styles.css" screen and (max-aspect-ratio: 4/3);` |
| `orientation` | Ekran yönü (portrait/landscape) | `@import "landscape.css" screen and (orientation: landscape);` |

### 💡 Boyut Örnekleri

```css
/* Mobil cihazlar için */
@import url("mobile.css") screen and (max-width: 768px);

/* Tablet cihazlar için */
@import url("tablet.css") screen and (min-width: 769px) and (max-width: 1024px);

/* Masaüstü cihazlar için */
@import url("desktop.css") screen and (min-width: 1024px);

/* Yükseklik kontrolü */
@import url("compact.css") screen and (max-height: 600px);

/* Yön kontrolü */
@import url("portrait.css") screen and (orientation: portrait);
@import url("landscape.css") screen and (orientation: landscape);
```

### 🎨 Renk ve Görüntü Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `color` | Renk başına bit sayısı | `@import "styles.css" screen and (min-color: 8);` |
| `min-color` | Minimum renk derinliği | `@import "styles.css" screen and (min-color: 8);` |
| `max-color` | Maksimum renk derinliği | `@import "styles.css" screen and (max-color: 24);` |
| `color-index` | İşlenebilecek renk sayısı | `@import "styles.css" screen and (min-color-index: 256);` |
| `min-color-index` | Minimum renk sayısı | `@import "styles.css" screen and (min-color-index: 256);` |
| `max-color-index` | Maksimum renk sayısı | `@import "styles.css" screen and (max-color-index: 65536);` |
| `color-gamut` | Desteklenen renk gamı | `@import "styles.css" (color-gamut: p3);` |
| `monochrome` | Tek renkli ekran bit sayısı | `@import "styles.css" (monochrome: 0);` |

### 💡 Renk Örnekleri

```css
/* Yüksek renk derinliği olan ekranlar için */
@import url("high-color.css") screen and (min-color: 8);

/* Geniş renk gamı desteği */
@import url("wide-gamut.css") (color-gamut: p3);
```

### 🔍 Çözünürlük Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `resolution` | DPI veya DPCM cinsinden çözünürlük | `@import "retina.css" screen and (min-resolution: 192dpi);` |
| `min-resolution` | Minimum çözünürlük | `@import "print.css" print and (min-resolution: 300dpi);` |
| `max-resolution` | Maksimum çözünürlük | `@import "styles.css" screen and (max-resolution: 600dpi);` |

### 💡 Çözünürlük Örnekleri

```css
/* Retina / Yüksek çözünürlüklü ekranlar için */
@import url("retina.css") screen and (min-resolution: 192dpi);

/* Yazdırma için yüksek çözünürlük */
@import url("print-hq.css") print and (min-resolution: 300dpi);
```

### 🌟 Görüntüleme ve Etkileşim Özellikleri

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `display-mode` | Uygulama görüntülenme modu | `@import "styles.css" all and (display-mode: fullscreen);` |
| `pointer` | Birincil işaretleme aygıtı | `@import "touch.css" (pointer: coarse);` |
| `any-pointer` | Herhangi bir işaretleme aygıtı | `@import "styles.css" (any-pointer: fine);` |
| `hover` | Hover desteği | `@import "styles.css" (hover: hover);` |
| `any-hover` | Herhangi bir hover desteği | `@import "styles.css" (any-hover: hover);` |
| `light-level` | Ekran ışık seviyesi | `@import "dark.css" (light-level: dim);` |
| `inverted-colors` | Renk tersine çevirme | `@import "styles.css" (inverted-colors: inverted);` |

### 💡 Etkileşim Örnekleri

```css
/* Dokunmatik cihazlar için */
@import url("touch.css") (pointer: coarse);

/* Mouse kullanılan cihazlar için */
@import url("desktop.css") (pointer: fine);

/* Hover desteği olan cihazlar için */
@import url("interactive.css") (hover: hover);

/* Tam ekran modu */
@import url("fullscreen.css") all and (display-mode: fullscreen);
```

### 📄 Diğer Özellikler

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `grid` | Izgara veya bitmap ekran | `@import "styles.css" (grid: 0);` |
| `scan` | Tarama türü | `@import "styles.css" (scan: progressive);` |
| `update` | Görüntü yenileme sıklığı | `@import "styles.css" (update: fast);` |
| `scripting` | Komut dosyası desteği | `@import "styles.css" (scripting: enabled);` |
| `overflow-block` | Blok eksen taşma durumu | `@import "styles.css" (overflow-block: scroll);` |
| `overflow-inline` | Satır içi eksen taşma durumu | `@import "styles.css" (overflow-inline: scroll);` |

---

## 💡 Pratik Örnekler

### Örnek 1: Responsive CSS Dosyaları

```css
/* Ana stil dosyası */
@import url("base.css");

/* Mobil cihazlar için */
@import url("mobile.css") screen and (max-width: 768px);

/* Tablet cihazlar için */
@import url("tablet.css") screen and (min-width: 769px) and (max-width: 1024px);

/* Masaüstü cihazlar için */
@import url("desktop.css") screen and (min-width: 1024px);
```

### Örnek 2: Yazdırma Stilleri

```css
/* Ekran için */
@import url("screen.css") screen;

/* Yazdırma için */
@import url("print.css") print;
```

### Örnek 3: Yüksek Çözünürlüklü Ekranlar

```css
/* Normal çözünürlük */
@import url("styles.css") screen;

/* Retina / Yüksek çözünürlük */
@import url("retina.css") screen and (min-resolution: 192dpi);
```

### Örnek 4: Yön Bazlı Stiller

```css
/* Dikey yön */
@import url("portrait.css") screen and (orientation: portrait);

/* Yatay yön */
@import url("landscape.css") screen and (orientation: landscape);
```

### Örnek 5: Dokunmatik vs Mouse

```css
/* Dokunmatik cihazlar */
@import url("touch.css") (pointer: coarse);

/* Mouse kullanılan cihazlar */
@import url("desktop.css") (pointer: fine);
```

---

## 🎯 @import vs <link> Karşılaştırması

### @import Kullanımı

```css
/* CSS dosyası içinde */
@import url("mobile.css") screen and (max-width: 768px);
```

**Avantajları:**
- CSS dosyası içinde kontrol
- Media query ile koşullu yükleme
- CSS preprocessor'lar ile uyumlu

**Dezavantajları:**
- Performans: Dosyalar sırayla yüklenir (paralel değil)
- HTTP istek sayısı artar
- Eski tarayıcılarda sorun olabilir

### <link> Kullanımı

```html
<!-- HTML dosyası içinde -->
<link rel="stylesheet" href="mobile.css" media="screen and (max-width: 768px)">
```

**Avantajları:**
- Daha iyi performans (paralel yükleme)
- Tarayıcı optimizasyonu
- Daha iyi önbellekleme

**Dezavantajları:**
- HTML dosyasını değiştirmek gerekir
- CSS dosyası içinde kontrol yok

---

## 🎯 Best Practices (En İyi Uygulamalar)

### 1. **@import Kullanımından Kaçının (Performans)**

```css
/* ❌ Kötü - Çok fazla @import */
@import url("reset.css");
@import url("base.css");
@import url("components.css");
@import url("utilities.css");

/* ✅ İyi - Tek dosya veya <link> kullanın */
/* HTML'de: */
<link rel="stylesheet" href="styles.css">
```

### 2. **Media Query ile Koşullu Yükleme**

```css
/* ✅ İyi - Sadece gerekli dosyalar yüklenir */
@import url("print.css") print;
@import url("mobile.css") screen and (max-width: 768px);
```

### 3. **CSS Preprocessor Kullanımı**

```scss
// SCSS/Sass ile
@import "base";
@import "components";
@import "utilities";

// Derleme sonrası tek dosya oluşur
```

### 4. **Modern Alternatif: CSS Modules**

```javascript
// CSS Modules ile
import styles from './styles.module.css';
```

---

## ⚠️ Önemli Notlar

1. **@import Kuralı Konumu:** `@import` kuralları CSS dosyasının en başında, diğer tüm kurallardan önce olmalıdır (yorumlar hariç).

```css
/* ✅ Doğru */
@import url("styles.css");
body { color: black; }

/* ❌ Yanlış */
body { color: black; }
@import url("styles.css"); /* Bu çalışmaz! */
```

2. **Performans:** `@import` kullanımı performansı düşürebilir çünkü dosyalar sırayla yüklenir. Mümkünse `<link>` kullanın veya dosyaları birleştirin.

3. **Tarayıcı Desteği:** Tüm modern tarayıcılar `@import` ile media query'leri destekler.

4. **CSS Preprocessor'lar:** Sass, Less gibi preprocessor'lar `@import` kullanır ancak derleme sonrası tek dosya oluşturur.

5. **URL Formatı:** `url()` kullanımı opsiyoneldir:
   ```css
   @import "styles.css" screen;
   @import url("styles.css") screen; /* İkisi de geçerli */
   ```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

# 🎯 CSS ATTRIBUTE (ÖZELLİK) SEÇİCİLER

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) attribute (özellik) seçiciler, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin özelliklerine (attributes) göre seçim yapmak için kullanılır. Bu seçiciler, özellik değerlerini kontrol ederek daha spesifik hedefler oluşturur.

## 📋 Temel Attribute Seçici

Belirli bir özelliğe sahip elementleri seçer. Özelliğin değeri önemli değildir.

### Sözdizimi

```css
element[attribute] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* title özelliğine sahip tüm elementler */
[title] {
    cursor: help;
}

/* href özelliğine sahip tüm linkler */
a[href] {
    color: blue;
}

/* type özelliğine sahip tüm input'lar */
input[type] {
    border: 1px solid gray;
}

/* alt özelliğine sahip tüm resimler */
img[alt] {
    border: 2px solid green;
}
```

## 🎯 Tam Değer Eşleştirme

Özelliğin tam olarak belirtilen değere eşit olması gerekir.

### Sözdizimi

```css
element[attribute="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* type özelliği tam olarak "text" olan input'lar */
input[type="text"] {
    width: 200px;
    padding: 5px;
}

/* type özelliği tam olarak "submit" olan button'lar */
input[type="submit"] {
    background-color: blue;
    color: white;
}

/* href özelliği tam olarak "#" olan linkler */
a[href="#"] {
    cursor: default;
}

/* lang özelliği tam olarak "tr" olan elementler */
[lang="tr"] {
    direction: ltr;
}
```

## 🔍 İçeren Değer Filtresi

Özellik değerinin belirtilen metni içermesi gerekir (herhangi bir yerde).

### Sözdizimi

```css
element[attribute*="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* href özelliğinde "example" kelimesini içeren linkler */
a[href*="example"] {
    color: red;
}

/* src özelliğinde "logo" kelimesini içeren resimler */
img[src*="logo"] {
    border: 2px solid blue;
}

/* class özelliğinde "button" kelimesini içeren elementler */
[class*="button"] {
    padding: 10px;
    cursor: pointer;
}
```

## 📝 İçeren Tam Değer Filtresi

Özellik değerinin belirtilen kelimeyi içermesi gerekir (boşlukla ayrılmış tam kelime).

### Sözdizimi

```css
element[attribute~="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* class özelliğinde "container" kelimesini içeren elementler */
[class~="container"] {
    width: 100%;
    max-width: 1200px;
}

/* class özelliğinde "primary" kelimesini içeren elementler */
[class~="primary"] {
    background-color: blue;
}

/* title özelliğinde "important" kelimesini içeren elementler */
[title~="important"] {
    font-weight: bold;
}
```

### 📝 HTML Örneği

```html
<!-- Bu seçilir -->
<div class="container main">İçerik</div>

<!-- Bu seçilmez (container kelimesi tam değil) -->
<div class="container-main">İçerik</div>
```

## 🚀 Başlayan Değer Filtresi

Özellik değerinin belirtilen metinle başlaması gerekir.

### Sözdizimi

```css
element[attribute^="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* href özelliği "https" ile başlayan linkler */
a[href^="https"] {
    color: green;
}

/* href özelliği "mailto" ile başlayan linkler */
a[href^="mailto"] {
    color: blue;
}

/* src özelliği "/images" ile başlayan resimler */
img[src^="/images"] {
    border: 1px solid gray;
}

/* id özelliği "section" ile başlayan elementler */
[id^="section"] {
    padding: 20px;
}
```

## 🏁 Biten Değer Filtresi

Özellik değerinin belirtilen metinle bitmesi gerekir.

### Sözdizimi

```css
element[attribute$="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* src özelliği ".jpg" ile biten resimler */
img[src$=".jpg"] {
    border: 2px solid black;
}

/* src özelliği ".png" ile biten resimler */
img[src$=".png"] {
    border: 2px solid blue;
}

/* href özelliği ".pdf" ile biten linkler */
a[href$=".pdf"] {
    color: red;
}

/* href özelliği ".html" ile biten linkler */
a[href$=".html"] {
    text-decoration: underline;
}
```

## 🔤 Tireli veya Tiresiz Başlayan Değer Filtresi

Özellik değerinin belirtilen metinle başlaması veya tire ile başlaması gerekir.

### Sözdizimi

```css
element[attribute|="value"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* lang özelliği "tr" veya "tr-" ile başlayan elementler */
[lang|="tr"] {
    direction: ltr;
}

/* lang özelliği "en" veya "en-" ile başlayan elementler */
[lang|="en"] {
    direction: ltr;
}
```

### 📝 HTML Örneği

```html
<!-- Bu seçilir -->
<div lang="tr">İçerik</div>
<div lang="tr-TR">İçerik</div>

<!-- Bu seçilmez -->
<div lang="turkish">İçerik</div>
```

## 🎯 Çoklu Attribute Seçici

Birden fazla özellik koşulunu birleştirerek daha spesifik seçimler yapabiliriz.

### Sözdizimi

```css
element[attribute1="value1"][attribute2="value2"] {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* type="text" ve required özelliğine sahip input'lar */
input[type="text"][required] {
    border: 2px solid red;
}

/* type="checkbox" ve checked özelliğine sahip input'lar */
input[type="checkbox"][checked] {
    background-color: green;
}

/* href özelliği "https" ile başlayan ve target="_blank" olan linkler */
a[href^="https"][target="_blank"] {
    color: blue;
}
```

## 💡 Pratik Kullanım Örnekleri

### Form Elementleri

```css
/* Tüm text input'lar */
input[type="text"],
input[type="email"],
input[type="password"] {
    width: 100%;
    padding: 10px;
}

/* Zorunlu alanlar */
input[required] {
    border-left: 3px solid red;
}

/* Devre dışı input'lar */
input[disabled] {
    background-color: #f0f0f0;
    cursor: not-allowed;
}
```

### Link Yönetimi

```css
/* Dış linkler */
a[href^="http"] {
    color: blue;
}

/* E-posta linkleri */
a[href^="mailto"] {
    color: green;
}

/* PDF dosyaları */
a[href$=".pdf"]::after {
    content: " (PDF)";
    font-size: 0.8em;
}

/* Yeni sekmede açılan linkler */
a[target="_blank"]::after {
    content: " ↗";
}
```

### Resim Yönetimi

```css
/* JPG resimler */
img[src$=".jpg"],
img[src$=".jpeg"] {
    border: 1px solid gray;
}

/* PNG resimler */
img[src$=".png"] {
    border: 1px solid blue;
}

/* Alt text'i olmayan resimler */
img:not([alt]) {
    border: 2px solid red;
}
```

## 📊 Attribute Seçici Filtreleri Tablosu

| Filtre | Sembol | Açıklama | Örnek |
|--------|--------|----------|-------|
| Tam Değer | `[attr="value"]` | Tam eşleşme | `input[type="text"]` |
| İçeren | `[attr*="value"]` | Herhangi bir yerde içerir | `a[href*="example"]` |
| İçeren Tam | `[attr~="value"]` | Boşlukla ayrılmış kelime | `[class~="container"]` |
| Başlayan | `[attr^="value"]` | Belirtilen metinle başlar | `a[href^="https"]` |
| Biten | `[attr$="value"]` | Belirtilen metinle biter | `img[src$=".jpg"]` |
| Tireli Başlayan | `[attr|="value"]` | Değer veya "value-" ile başlar | `[lang|="tr"]` |

## ⚠️ Önemli Notlar

1. **Büyük/Küçük Harf Duyarlılığı**: Attribute seçiciler büyük/küçük harf duyarlıdır (case-sensitive).

2. **Boşluklar**: `~=` filtresi boşlukla ayrılmış tam kelimeleri arar, `*=` filtresi ise herhangi bir yerdeki metni arar.

3. **Performans**: Attribute seçiciler, class ve ID seçicilere göre daha yavaştır.

4. **Okunabilirlik**: Karmaşık attribute seçiciler yerine, mümkün olduğunca class seçiciler kullanılmalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


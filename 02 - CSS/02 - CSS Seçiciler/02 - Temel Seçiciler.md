# 🎯 CSS TEMEL SEÇİCİLER

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) en sık kullanılan ve en temel seçici türleridir. Bu seçiciler HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerini doğrudan hedeflemek için kullanılır.

## 🌟 Genel (Evrensel) Seçici

Tüm HTML elementlerini seçer. Genellikle CSS reset işlemleri için kullanılır.

### Sözdizimi

```css
* {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* Tüm elementlerin margin ve padding değerlerini sıfırlar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Tüm elementlerin font ailesini tanımlar */
* {
    font-family: Arial, sans-serif;
}
```

## 📝 Element (Tür) Seçicileri

Belirli bir HTML element türünü seçer. Tüm aynı türdeki elementlere stil uygular.

### Sözdizimi

```css
element {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* Tüm paragraf elementlerinin metin rengini mavi yapar */
p {
    color: blue;
}

/* Tüm başlık elementlerinin font ağırlığını bold yapar */
h1, h2, h3, h4, h5, h6 {
    font-weight: bold;
}

/* Tüm div elementlerinin genişliğini %100 yapar */
div {
    width: 100%;
}

/* Tüm link elementlerinin alt çizgisini kaldırır */
a {
    text-decoration: none;
}

/* Tüm liste elementlerinin stilini kaldırır */
ul {
    list-style: none;
}
```

## 🆔 ID (Benzersiz Kimlik) Seçicileri

Belirli bir ID değerine sahip elementi seçer. Her sayfada bir ID değeri sadece bir kez kullanılmalıdır.

### Sözdizimi

```css
#id-değeri {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* ID'si "header" olan elementin arka plan rengini siyah yapar */
#header {
    background-color: black;
    color: white;
}

/* ID'si "main-content" olan elementin genişliğini %80 yapar */
#main-content {
    width: 80%;
    margin: 0 auto;
}

/* ID'si "footer" olan elementin konumunu sabitler */
#footer {
    position: fixed;
    bottom: 0;
    width: 100%;
}
```

### ⚠️ Önemli Notlar

- ID seçiciler yüksek önceliğe sahiptir (100 puan)
- Her sayfada bir ID değeri sadece bir kez kullanılmalıdır
- JavaScript ile element seçimi için de kullanılır

## 🏷️ Class (Sınıf) Seçicileri

Belirli bir class (sınıf) değerine sahip tüm elementleri seçer. Bir element birden fazla class'a sahip olabilir.

### Sözdizimi

```css
.class-değeri {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* Class'ı "container" olan tüm elementlerin genişliğini %100 yapar */
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

/* Class'ı "button" olan tüm elementlerin stilini tanımlar */
.button {
    padding: 10px 20px;
    background-color: blue;
    color: white;
    border: none;
    cursor: pointer;
}

/* Class'ı "card" olan tüm elementlerin stilini tanımlar */
.card {
    border: 1px solid gray;
    border-radius: 5px;
    padding: 20px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/* Class'ı "text-center" olan tüm elementlerin metnini ortalar */
.text-center {
    text-align: center;
}
```

### 🔗 Çoklu Class Kullanımı

Bir element birden fazla class'a sahip olabilir:

```html
<div class="container card text-center">
    <!-- İçerik -->
</div>
```

```css
/* Tüm class'ları içeren element */
.container.card.text-center {
    /* Stil tanımları */
}
```

## 🔄 Çoklu Seçici

Birden fazla seçiciyi virgül ile ayırarak aynı stili uygulayabiliriz.

### Sözdizimi

```css
seçici1, seçici2, seçici3 {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* h1, h2 ve h3 elementlerinin metin rengini kırmızı yapar */
h1, h2, h3 {
    color: red;
}

/* Farklı türde seçicileri birleştirme */
#header, .container, div {
    padding: 20px;
}

/* Karmaşık çoklu seçici */
h1.title, h2.subtitle, p.description {
    font-family: 'Arial', sans-serif;
}
```

## 🎯 Seçici Kombinasyonları

Temel seçicileri birleştirerek daha spesifik hedefler oluşturabiliriz.

### 💡 Örnekler

```css
/* Element + Class */
div.container {
    width: 100%;
}

/* Element + ID */
div#main {
    background-color: white;
}

/* Class + Class (tüm class'ları içeren element) */
.button.primary {
    background-color: blue;
}

/* Element + Class + Pseudo Class */
a.button:hover {
    background-color: darkblue;
}
```

## 📊 Seçici Öncelik Karşılaştırması

| Seçici Türü | Öncelik Puanı | Örnek |
|-------------|---------------|-------|
| Genel Seçici | 0 | `*` |
| Element Seçici | 1 | `div` |
| Class Seçici | 10 | `.container` |
| ID Seçici | 100 | `#header` |
| Inline Style | 1000 | `style="..."` |

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


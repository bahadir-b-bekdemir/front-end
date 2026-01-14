# 🎯 CSS SEÇİCİLERİ GENEL BAKIŞ

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) seçicileri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) sayfalarındaki elementleri hedeflemek ve stillendirmek için kullanılan güçlü araçlardır. Seçiciler sayesinde belirli elementlere, sınıflara, ID'lere veya özelliklere göre stil uygulayabiliriz.

## 📋 Seçici Kategorileri

CSS seçicileri genel olarak şu kategorilere ayrılır:

1. **Temel Seçiciler** - Element, ID, Class seçicileri
2. **Kombinatör Seçiciler** - Child, Descendant, Sibling seçicileri
3. **Attribute (Özellik) Seçiciler** - Özellik bazlı seçimler
4. **Pseudo Class Seçiciler** - Durum bazlı seçimler
5. **Pseudo Element Seçiciler** - İçerik bazlı seçimler

## 🎯 Seçici Önceliği (Specificity)

CSS'de birden fazla seçici aynı elementi hedeflediğinde, hangi stil kuralının uygulanacağını belirleyen öncelik sistemi vardır.

### Öncelik Sırası (Yüksekten Düşüğe)

1. **Inline Styles** (`style="..."`) - En yüksek öncelik
2. **ID Seçiciler** (`#id`) - 100 puan
3. **Class, Attribute, Pseudo Class Seçiciler** (`.class`, `[attr]`, `:hover`) - 10 puan
4. **Element, Pseudo Element Seçiciler** (`div`, `::before`) - 1 puan
5. **Genel Seçici** (`*`) - 0 puan

### 💡 Örnekler

```css
/* Öncelik: 0 puan */
* {
    color: black;
}

/* Öncelik: 1 puan */
div {
    color: blue;
}

/* Öncelik: 10 puan */
.container {
    color: green;
}

/* Öncelik: 11 puan (1 + 10) */
div.container {
    color: orange;
}

/* Öncelik: 100 puan */
#header {
    color: red;
}

/* Öncelik: 110 puan (100 + 10) */
#header.container {
    color: purple;
}
```

## 🔗 Seçici Kombinasyonları

Farklı seçici türlerini birleştirerek daha spesifik hedefler oluşturabiliriz.

### 💡 Örnekler

```css
/* Element + Class */
div.container {
    padding: 20px;
}

/* Element + ID */
div#main {
    width: 100%;
}

/* Class + Pseudo Class */
.button:hover {
    background-color: blue;
}

/* Element + Attribute */
input[type="text"] {
    border: 1px solid gray;
}

/* Çoklu Seçici */
h1, h2, h3 {
    font-weight: bold;
}

/* Karmaşık Kombinasyon */
div.container > p:first-child {
    font-size: 18px;
}
```

## ⚠️ Önemli Notlar

1. **Seçici Önceliği**: Daha spesifik seçiciler, daha genel seçicilere göre önceliklidir.

2. **!important Kuralı**: `!important` kullanımı tüm öncelik kurallarını geçersiz kılar, ancak kötü bir pratik olarak kabul edilir.

```css
/* !important kullanımı - Önerilmez */
div {
    color: red !important;
}
```

3. **Seçici Performansı**: ID ve Class seçiciler, element seçicilere göre daha hızlıdır.

4. **Okunabilirlik**: Karmaşık seçiciler yerine, mümkün olduğunca basit ve anlaşılır seçiciler kullanılmalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


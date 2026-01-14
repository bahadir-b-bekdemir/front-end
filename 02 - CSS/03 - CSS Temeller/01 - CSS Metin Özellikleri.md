# 📝 CSS METİN ÖZELLİKLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) metin özellikleri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerindeki metinlerin görünümünü ve düzenini kontrol etmek için kullanılır.

## 🎨 Renk Özellikleri

### `color`

Metin rengini belirler.

```css
p {
    color: blue;
    color: #FF0000;
    color: rgb(255, 0, 0);
    color: rgba(255, 0, 0, 0.5);
}
```

## 📏 Font Özellikleri

### `font-family`

Yazı tipi ailesini belirler.

```css
body {
    font-family: Arial, sans-serif;
    font-family: "Times New Roman", serif;
    font-family: "Courier New", monospace;
}
```

### `font-size`

Yazı tipi boyutunu belirler.

```css
p {
    font-size: 16px;
    font-size: 1em;
    font-size: 1rem;
    font-size: 100%;
}
```

### `font-weight`

Yazı tipi kalınlığını belirler.

```css
p {
    font-weight: normal;    /* 400 */
    font-weight: bold;      /* 700 */
    font-weight: 100;       /* Thin */
    font-weight: 900;       /* Black */
}
```

### `font-style`

Yazı tipi stilini belirler.

```css
p {
    font-style: normal;
    font-style: italic;
    font-style: oblique;
}
```

### `font-variant`

Yazı tipi varyantını belirler.

```css
p {
    font-variant: normal;
    font-variant: small-caps;
}
```

### `font` (Kısa Yazım)

Tüm font özelliklerini tek satırda tanımlar.

```css
p {
    font: italic bold 16px/1.5 Arial, sans-serif;
    /* font-style font-weight font-size/line-height font-family */
}
```

## 📐 Metin Hizalama

### `text-align`

Metni yatay olarak hizalar.

```css
p {
    text-align: left;
    text-align: right;
    text-align: center;
    text-align: justify;
}
```

### `vertical-align`

Metni dikey olarak hizalar (inline elementler için).

```css
span {
    vertical-align: baseline;
    vertical-align: top;
    vertical-align: middle;
    vertical-align: bottom;
    vertical-align: 10px;
}
```

### `text-indent`

İlk satırın girintisini belirler.

```css
p {
    text-indent: 20px;
    text-indent: 2em;
    text-indent: 10%;
}
```

## ✏️ Metin Dekorasyonu

### `text-decoration`

Metin dekorasyonunu belirler.

```css
a {
    text-decoration: none;
    text-decoration: underline;
    text-decoration: overline;
    text-decoration: line-through;
}

/* Ayrı özellikler */
a {
    text-decoration-line: underline;
    text-decoration-color: red;
    text-decoration-style: wavy;
    text-decoration-thickness: 2px;
}
```

### `text-transform`

Metin dönüşümünü belirler.

```css
p {
    text-transform: none;
    text-transform: uppercase;    /* TÜMÜ BÜYÜK */
    text-transform: lowercase;  /* tümü küçük */
    text-transform: capitalize; /* İlk Harfler Büyük */
}
```

### `text-shadow`

Metne gölge efekti ekler.

```css
h1 {
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    /* x-offset y-offset blur-radius color */
    
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5),
                 0 0 10px rgba(255,0,0,0.5);  /* Çoklu gölge */
}
```

## 📏 Satır ve Harf Aralıkları

### `line-height`

Satır yüksekliğini belirler.

```css
p {
    line-height: normal;
    line-height: 1.5;
    line-height: 24px;
    line-height: 150%;
}
```

### `letter-spacing`

Harf aralığını belirler.

```css
h1 {
    letter-spacing: 2px;
    letter-spacing: 0.1em;
    letter-spacing: normal;
}
```

### `word-spacing`

Kelime aralığını belirler.

```css
p {
    word-spacing: 5px;
    word-spacing: 0.2em;
    word-spacing: normal;
}
```

## 📄 Metin Düzeni

### `white-space`

Beyaz boşlukların nasıl işleneceğini belirler.

```css
p {
    white-space: normal;      /* Varsayılan */
    white-space: nowrap;      /* Satır kırılmaz */
    white-space: pre;         /* Önceden biçimlendirilmiş */
    white-space: pre-wrap;    /* Satır kırılır, boşluklar korunur */
    white-space: pre-line;    /* Satır kırılır, boşluklar birleşir */
}
```

### `word-wrap` / `overflow-wrap`

Uzun kelimelerin nasıl kırılacağını belirler.

```css
p {
    word-wrap: normal;
    word-wrap: break-word;
    
    overflow-wrap: normal;
    overflow-wrap: break-word;
    overflow-wrap: anywhere;
}
```

### `word-break`

Kelime kırılma kurallarını belirler.

```css
p {
    word-break: normal;
    word-break: break-all;     /* Herhangi bir karakterde kırılabilir */
    word-break: keep-all;      /* Asya dilleri için */
    word-break: break-word;    /* Uzun kelimeler kırılır */
}
```

### `text-overflow`

Taşan metnin nasıl gösterileceğini belirler.

```css
p {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: clip;       /* Kesilir */
    text-overflow: ellipsis;   /* ... ile gösterilir */
}
```

## 🎯 Metin Seçimi

### `user-select`

Kullanıcının metni seçip seçemeyeceğini belirler.

```css
p {
    user-select: none;         /* Seçilemez */
    user-select: auto;         /* Varsayılan */
    user-select: all;          /* Tıklanınca tümü seçilir */
    user-select: text;         /* Sadece metin seçilebilir */
}
```

## 💡 Pratik Örnekler

### Başlık Stilleri

```css
h1 {
    font-family: "Arial", sans-serif;
    font-size: 2.5rem;
    font-weight: bold;
    color: #333;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 2px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}
```

### Paragraf Stilleri

```css
p {
    font-family: "Georgia", serif;
    font-size: 1.1rem;
    line-height: 1.6;
    color: #555;
    text-align: justify;
    text-indent: 2em;
    word-spacing: 0.1em;
}
```

### Link Stilleri

```css
a {
    color: #0066cc;
    text-decoration: none;
    font-weight: bold;
}

a:hover {
    text-decoration: underline;
    color: #004499;
}
```

### Uzun Metin Kırılması

```css
.truncate {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 300px;
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


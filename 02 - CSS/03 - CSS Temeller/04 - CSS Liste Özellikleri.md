# 📋 CSS LİSTE ÖZELLİKLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) liste özellikleri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) liste elementlerinin (`<ul>`, `<ol>`, `<li>`) görünümünü kontrol etmek için kullanılır.

## 🎯 `list-style-type`

Liste işaretçisinin (marker) türünü belirler.

### Sırasız Listeler (ul)

```css
ul {
    list-style-type: disc;        /* Varsayılan - Dolu daire */
    list-style-type: circle;      /* Boş daire */
    list-style-type: square;      /* Kare */
    list-style-type: none;        /* İşaretçi yok */
}
```

### Sıralı Listeler (ol)

```css
ol {
    list-style-type: decimal;         /* 1, 2, 3, ... */
    list-style-type: decimal-leading-zero;  /* 01, 02, 03, ... */
    list-style-type: lower-roman;     /* i, ii, iii, ... */
    list-style-type: upper-roman;     /* I, II, III, ... */
    list-style-type: lower-alpha;     /* a, b, c, ... */
    list-style-type: upper-alpha;     /* A, B, C, ... */
    list-style-type: lower-latin;     /* a, b, c, ... */
    list-style-type: upper-latin;     /* A, B, C, ... */
    list-style-type: none;            /* İşaretçi yok */
}
```

## 📍 `list-style-position`

Liste işaretçisinin konumunu belirler.

```css
ul {
    list-style-position: outside;  /* Varsayılan - Dışarıda */
    list-style-position: inside;   /* İçeride */
}
```

### Dışarıda (outside)

```
• İlk öğe
• İkinci öğe
• Üçüncü öğe
```

### İçeride (inside)

```
• İlk öğe
  • İkinci öğe
    • Üçüncü öğe
```

## 🖼️ `list-style-image`

Liste işaretçisi olarak resim kullanır.

```css
ul {
    list-style-image: url("bullet.png");
    list-style-image: url("../images/arrow.png");
    list-style-image: none;  /* Resim yok */
}
```

## 🎨 `list-style` (Kısa Yazım)

Tüm liste özelliklerini tek satırda tanımlar.

```css
ul {
    list-style: disc inside url("bullet.png");
    /* type position image */
    
    list-style: none;  /* Tüm özellikleri kaldırır */
}
```

## 📏 Liste Öğeleri için Özel Özellikler

### `marker-offset`

Liste işaretçisi ile içerik arasındaki mesafeyi belirler (artık kullanılmıyor, margin kullanılmalı).

### Pseudo Element: `::marker`

Liste işaretçisini özelleştirmek için kullanılır.

```css
li::marker {
    color: blue;
    font-weight: bold;
    font-size: 1.2em;
}

/* Sadece belirli liste öğeleri için */
li.special::marker {
    content: "★ ";
    color: gold;
}
```

## 💡 Pratik Örnekler

### Basit Liste Stilleri

```css
ul {
    list-style-type: disc;
    list-style-position: outside;
    padding-left: 20px;
}
```

### Özel İşaretçi

```css
ul.custom {
    list-style: none;
    padding-left: 0;
}

ul.custom li::before {
    content: "→ ";
    color: blue;
    font-weight: bold;
    margin-right: 10px;
}
```

### Resim İşaretçisi

```css
ul.image-bullets {
    list-style-image: url("arrow.png");
    list-style-position: inside;
}
```

### Yatay Menü

```css
ul.horizontal {
    list-style: none;
    display: flex;
    gap: 20px;
}

ul.horizontal li {
    display: inline-block;
}
```

### İç İçe Listeler

```css
ul {
    list-style-type: disc;
}

ul ul {
    list-style-type: circle;
}

ul ul ul {
    list-style-type: square;
}
```

### Sıralı Liste Stilleri

```css
ol {
    list-style-type: decimal;
    padding-left: 30px;
}

ol.roman {
    list-style-type: upper-roman;
}

ol.alpha {
    list-style-type: lower-alpha;
}
```

### Özel Numaralandırma

```css
ol.custom {
    list-style: none;
    counter-reset: item;
    padding-left: 0;
}

ol.custom li {
    counter-increment: item;
    margin-bottom: 10px;
}

ol.custom li::before {
    content: counter(item) ". ";
    color: blue;
    font-weight: bold;
    margin-right: 10px;
}
```

### Kart Tasarımı Listesi

```css
ul.cards {
    list-style: none;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    padding: 0;
}

ul.cards li {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    background: white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

## ⚠️ Önemli Notlar

1. **list-style: none**: Liste işaretçisini kaldırır, ancak liste yapısını korur.

2. **Pseudo Element**: `::marker` modern tarayıcılarda desteklenir ve liste işaretçisini özelleştirmek için kullanılabilir.

3. **Erişilebilirlik**: Liste işaretçilerini kaldırırken, içeriğin hala liste olarak algılanması için `list-style: none` yerine `::marker` kullanılabilir.

4. **Performans**: Resim işaretçileri yerine CSS ile oluşturulan işaretçiler daha performanslıdır.

5. **Flexbox/Grid**: Liste öğeleri Flexbox veya Grid ile düzenlenebilir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


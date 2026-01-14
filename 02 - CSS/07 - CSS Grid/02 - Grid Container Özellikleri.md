# 📦 CSS GRID CONTAINER ÖZELLİKLERİ

CSS Grid'te container (ana kutu) özellikleri, grid item'ların nasıl düzenleneceğini kontrol eder.

## 🎯 `display: grid`

Elementi grid container yapar.

```css
.container {
    display: grid;
}
```

## 📐 `grid-template-columns`

Sütunların boyutlarını belirler.

```css
.container {
    grid-template-columns: 200px 200px 200px;  /* 3 sabit sütun */
    grid-template-columns: 1fr 1fr 1fr;        /* 3 eşit sütun */
    grid-template-columns: repeat(3, 1fr);     /* 3 eşit sütun */
    grid-template-columns: 1fr 2fr 1fr;        /* Orta sütun 2 kat */
    grid-template-columns: auto 1fr auto;      /* Kenarlar otomatik */
    grid-template-columns: minmax(200px, 1fr);  /* Minimum 200px */
}
```

### 💡 Örnekler

```css
/* 3 eşit sütun */
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

/* Responsive sütunlar */
.responsive {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}
```

## 📏 `grid-template-rows`

Satırların boyutlarını belirler.

```css
.container {
    grid-template-rows: 100px 200px 100px;  /* 3 sabit satır */
    grid-template-rows: auto auto auto;     /* 3 otomatik satır */
    grid-template-rows: 1fr 2fr 1fr;        /* Orta satır 2 kat */
    grid-template-rows: repeat(3, auto);     /* 3 otomatik satır */
}
```

### 💡 Örnek

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 100px auto 100px;
}
```

## 🎯 `grid-template-areas`

Grid alanlarını isimlendirerek düzen oluşturur.

```css
.container {
    grid-template-areas:
        "header header header"
        "sidebar content content"
        "footer footer footer";
}

.header {
    grid-area: header;
}

.sidebar {
    grid-area: sidebar;
}

.content {
    grid-area: content;
}

.footer {
    grid-area: footer;
}
```

## 🔄 `grid-template` (Kısa Yazım)

`grid-template-rows`, `grid-template-columns` ve `grid-template-areas` özelliklerini birleştirir.

```css
.container {
    grid-template:
        "header header" 100px
        "sidebar content" auto
        "footer footer" 50px
        / 200px 1fr;
}
```

## 📊 `grid-auto-columns` ve `grid-auto-rows`

Otomatik oluşturulan sütun ve satırların boyutlarını belirler.

```css
.container {
    grid-auto-columns: 100px;
    grid-auto-rows: 150px;
}
```

## 🔢 `gap`

Öğeler arasındaki boşluğu belirler.

```css
.container {
    gap: 20px;           /* Tüm yönlerde */
    gap: 10px 20px;      /* Satır sütun */
    row-gap: 10px;       /* Sadece satır */
    column-gap: 20px;    /* Sadece sütun */
}
```

### 💡 Örnek

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;  /* Öğeler arası 20px boşluk */
}
```

## 📐 `justify-items`

Sütun ekseninde (inline axis) öğelerin hizalanmasını belirler.

```css
.container {
    justify-items: start;    /* Başta */
    justify-items: end;      /* Sonda */
    justify-items: center;    /* Ortada */
    justify-items: stretch;   /* Varsayılan - Uzatılır */
}
```

## 📏 `align-items`

Satır ekseninde (block axis) öğelerin hizalanmasını belirler.

```css
.container {
    align-items: start;    /* Başta */
    align-items: end;       /* Sonda */
    align-items: center;    /* Ortada */
    align-items: stretch;   /* Varsayılan - Uzatılır */
}
```

## 🎯 `place-items` (Kısa Yazım)

`align-items` ve `justify-items` özelliklerini birleştirir.

```css
.container {
    place-items: center;        /* Her iki eksende ortada */
    place-items: start end;    /* align justify */
}
```

## 📊 `justify-content` ve `align-content`

Grid container'ın kendisinin hizalanmasını belirler (grid öğeleri değil).

```css
.container {
    justify-content: start;      /* Sütun ekseninde */
    align-content: center;       /* Satır ekseninde */
}
```

## 💡 Pratik Örnekler

### Basit Grid

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### Responsive Grid

```css
.responsive-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
}
```

### Layout Grid

```css
.layout {
    display: grid;
    grid-template-areas:
        "header header"
        "sidebar content"
        "footer footer";
    grid-template-columns: 200px 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 20px;
}
```

### Ortalanmış Grid

```css
.center-grid {
    display: grid;
    grid-template-columns: repeat(3, 200px);
    justify-content: center;
    align-content: center;
    gap: 20px;
}
```

## 📊 Özellik Özeti

| Özellik | Açıklama |
|---------|----------|
| `grid-template-columns` | Sütun boyutları |
| `grid-template-rows` | Satır boyutları |
| `grid-template-areas` | Alan isimleri |
| `gap` | Öğeler arası boşluk |
| `justify-items` | Sütun ekseni hizalama |
| `align-items` | Satır ekseni hizalama |

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


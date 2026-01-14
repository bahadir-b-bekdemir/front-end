# 🎯 CSS GRID ITEM ÖZELLİKLERİ

CSS Grid'te item (öğe) özellikleri, grid container içindeki her bir öğenin konumunu ve davranışını kontrol eder.

## 📐 `grid-column` ve `grid-row`

Öğenin hangi sütun ve satırlarda yer alacağını belirler.

### `grid-column`

```css
.item {
    grid-column: 1 / 3;        /* 1. sütundan 3. sütuna kadar */
    grid-column: 1 / span 2;   /* 1. sütundan başla, 2 sütun kapla */
    grid-column: span 2;       /* 2 sütun kapla */
    grid-column: auto;         /* Varsayılan - Otomatik */
}
```

### `grid-row`

```css
.item {
    grid-row: 1 / 3;        /* 1. satırdan 3. satıra kadar */
    grid-row: 1 / span 2;  /* 1. satırdan başla, 2 satır kapla */
    grid-row: span 2;      /* 2 satır kapla */
    grid-row: auto;         /* Varsayılan - Otomatik */
}
```

### Ayrı Özellikler

```css
.item {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
}
```

### 💡 Örnekler

```css
/* Öğe 2 sütun kaplar */
.wide-item {
    grid-column: 1 / 3;
}

/* Öğe 2 satır kaplar */
.tall-item {
    grid-row: 1 / 3;
}

/* Öğe hem 2 sütun hem 2 satır kaplar */
.large-item {
    grid-column: 1 / 3;
    grid-row: 1 / 3;
}

/* Span kullanımı */
.span-item {
    grid-column: span 2;
    grid-row: span 2;
}
```

## 🎯 `grid-area`

Öğenin grid alanını belirler. `grid-template-areas` ile birlikte kullanılabilir veya `grid-row` ve `grid-column` için kısa yazım olarak kullanılabilir.

### İsimlendirilmiş Alan

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
```

### Kısa Yazım (grid-row / grid-column)

```css
.item {
    grid-area: 1 / 1 / 3 / 3;
    /* row-start / column-start / row-end / column-end */
}
```

### 💡 Örnek

```css
.item {
    grid-area: 2 / 2 / 4 / 4;
    /* 2. satırdan 4. satıra, 2. sütundan 4. sütuna */
}
```

## 📍 `justify-self` ve `align-self`

Tek bir öğenin hizalanmasını belirler (container'ın `justify-items` ve `align-items`'ini geçersiz kılar).

### `justify-self`

Sütun ekseninde (inline axis) hizalama.

```css
.item {
    justify-self: start;    /* Başta */
    justify-self: end;      /* Sonda */
    justify-self: center;   /* Ortada */
    justify-self: stretch;  /* Varsayılan - Uzatılır */
}
```

### `align-self`

Satır ekseninde (block axis) hizalama.

```css
.item {
    align-self: start;    /* Başta */
    align-self: end;      /* Sonda */
    align-self: center;   /* Ortada */
    align-self: stretch;  /* Varsayılan - Uzatılır */
}
```

### `place-self` (Kısa Yazım)

`align-self` ve `justify-self` özelliklerini birleştirir.

```css
.item {
    place-self: center;        /* Her iki eksende ortada */
    place-self: start end;    /* align justify */
}
```

### 💡 Örnek

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-items: start;
    align-items: start;
}

.special-item {
    justify-self: center;  /* Bu öğe ortada */
    align-self: center;    /* Bu öğe ortada */
}
```

## 💡 Pratik Örnekler

### Magazine Layout

```css
.magazine {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, 200px);
    gap: 10px;
}

.featured {
    grid-column: 1 / 3;
    grid-row: 1 / 3;
}

.sidebar {
    grid-column: 3 / 5;
    grid-row: 1 / 4;
}

.small-item {
    grid-column: span 1;
    grid-row: span 1;
}
```

### Responsive Card Grid

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}

.card {
    /* Otomatik yerleştirilir */
}

.featured-card {
    grid-column: 1 / -1;  /* Tüm sütunları kaplar */
}
```

### Overlapping Items

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.background {
    grid-column: 1 / 4;
    grid-row: 1;
}

.overlay {
    grid-column: 2 / 3;
    grid-row: 1;
    z-index: 10;
}
```

### Named Grid Lines

```css
.container {
    display: grid;
    grid-template-columns: [start] 200px [sidebar-end] 1fr [end];
    grid-template-rows: [header-start] 100px [header-end content-start] auto [content-end];
}

.item {
    grid-column: start / sidebar-end;
    grid-row: header-start / header-end;
}
```

### Negative Line Numbers

```css
.item {
    grid-column: 1 / -1;  /* İlk sütundan son sütuna */
    grid-row: 1 / -1;     /* İlk satırdan son satıra */
}
```

## 📊 Özellik Özeti

| Özellik | Açıklama | Varsayılan |
|---------|----------|------------|
| `grid-column` | Sütun konumu | `auto` |
| `grid-row` | Satır konumu | `auto` |
| `grid-column-start` | Sütun başlangıcı | `auto` |
| `grid-column-end` | Sütun bitişi | `auto` |
| `grid-row-start` | Satır başlangıcı | `auto` |
| `grid-row-end` | Satır bitişi | `auto` |
| `grid-area` | Alan tanımı | `auto` |
| `justify-self` | Sütun ekseni hizalama | `auto` |
| `align-self` | Satır ekseni hizalama | `auto` |
| `place-self` | Her iki eksen hizalama | `auto` |

## ⚠️ Önemli Notlar

1. **Grid Lines**: Grid çizgileri 1'den başlar (0 değil).

2. **Negative Lines**: Son çizgiden geriye doğru saymak için negatif değerler kullanılabilir: `-1` son çizgi.

3. **Span**: `span` kullanımı öğenin kaç hücre kaplayacağını belirler.

4. **Auto Placement**: Öğe için konum belirtilmezse otomatik yerleştirilir.

5. **Overlap**: Öğeler aynı hücreyi kaplayabilir, `z-index` ile sıralama yapılabilir.

6. **grid-area**: Hem isimlendirilmiş alanlar hem de satır/sütun konumu için kullanılabilir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


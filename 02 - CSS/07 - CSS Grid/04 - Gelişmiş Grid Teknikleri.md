# 🚀 GELİŞMİŞ CSS GRID TEKNİKLERİ

CSS Grid'in gelişmiş özellikleri ve teknikleri ile daha karmaşık ve esnek düzenler oluşturabilirsiniz.

## 📐 Grid Lines (Izgara Çizgileri)

Grid çizgileri, grid öğelerini konumlandırmak için kullanılır.

```css
.item {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
}
```

### Kısa Yazım

```css
.item {
    grid-column: 1 / 3;  /* start / end */
    grid-row: 1 / 2;
}
```

## 🎯 Grid Spanning (Yayılma)

Öğelerin birden fazla hücreyi kaplaması.

```css
.item {
    grid-column: span 2;  /* 2 sütun kaplar */
    grid-row: span 3;     /* 3 satır kaplar */
}
```

## 📊 Named Grid Lines (İsimlendirilmiş Çizgiler)

Grid çizgilerini isimlendirerek daha okunabilir kod yazabilirsiniz.

```css
.container {
    display: grid;
    grid-template-columns: [start] 200px [sidebar-end] 1fr [end];
    grid-template-rows: [header-start] 100px [header-end content-start] auto [content-end footer-start] 50px [footer-end];
}

.item {
    grid-column: start / sidebar-end;
    grid-row: header-start / header-end;
}
```

## 🔢 `repeat()` Fonksiyonu

Tekrarlanan değerler için kullanılır.

```css
.container {
    grid-template-columns: repeat(3, 1fr);
    grid-template-columns: repeat(4, 100px);
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

### `auto-fill` vs `auto-fit`

- **auto-fill**: Mümkün olduğunca çok sütun oluşturur
- **auto-fit**: Öğeleri sığdıracak kadar sütun oluşturur

## 📏 `minmax()` Fonksiyonu

Minimum ve maksimum boyutları belirler.

```css
.container {
    grid-template-columns: minmax(200px, 1fr);
    grid-template-columns: minmax(auto, 300px);
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}
```

## 🎨 Subgrid (Alt Grid)

Grid item'ın kendi grid container'ı olması.

```css
.parent {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.child {
    display: grid;
    grid-template-columns: subgrid;  /* Parent'ın sütunlarını kullanır */
}
```

**⚠️ Not:** Subgrid henüz tüm tarayıcılarda desteklenmiyor.

## 📐 Grid Auto Placement

Öğelerin otomatik yerleştirilmesi.

```css
.container {
    grid-auto-flow: row;        /* Varsayılan - Satır */
    grid-auto-flow: column;     /* Sütun */
    grid-auto-flow: dense;      /* Yoğun yerleştirme */
}
```

### Dense Yerleştirme

```css
.container {
    grid-auto-flow: row dense;  /* Boşlukları doldurur */
}
```

## 🎯 Grid Item Hizalama

### `justify-self` ve `align-self`

Tek bir öğenin hizalanması.

```css
.item {
    justify-self: center;  /* Sütun ekseninde */
    align-self: center;     /* Satır ekseninde */
    place-self: center;     /* Her iki eksende */
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
```

### Masonry Layout (Hack)

```css
.masonry {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    grid-auto-rows: 10px;
}

.item {
    grid-row-end: span var(--row-span);
}
```

### Overlapping Items

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.overlay {
    grid-column: 1 / 4;
    grid-row: 1;
    z-index: 10;
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
    display: grid;
    grid-template-rows: auto 1fr auto;
}
```

## ⚠️ Önemli Notlar

1. **Grid Lines**: 1'den başlar (0 değil)

2. **Negative Lines**: Son çizgiden geriye doğru saymak için negatif değerler kullanılabilir: `-1` son çizgi

3. **Span**: `span` kullanımı öğenin kaç hücre kaplayacağını belirler

4. **Auto Placement**: `grid-auto-flow` ile öğelerin otomatik yerleştirilmesi kontrol edilir

5. **Browser Support**: Subgrid gibi bazı özellikler henüz tüm tarayıcılarda desteklenmiyor

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


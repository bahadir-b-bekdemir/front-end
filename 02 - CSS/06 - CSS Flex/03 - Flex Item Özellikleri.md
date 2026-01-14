# 🎯 CSS FLEX ITEM ÖZELLİKLERİ

CSS Flexbox'ta item (öğe) özellikleri, flex container içindeki her bir öğenin davranışını kontrol eder.

## 📏 `flex-grow`

Öğenin mevcut alanda ne kadar büyüyeceğini belirler.

```css
.item {
    flex-grow: 0;    /* Varsayılan - Büyümez */
    flex-grow: 1;    /* Mevcut alanı eşit paylaşır */
    flex-grow: 2;    /* Diğerlerinden 2 kat fazla büyür */
}
```

### 💡 Örnek

```css
.item1 {
    flex-grow: 1;  /* 1 birim */
}

.item2 {
    flex-grow: 2;  /* 2 birim - 2 kat fazla */
}
```

## 📉 `flex-shrink`

Öğenin yetersiz alanda ne kadar küçüleceğini belirler.

```css
.item {
    flex-shrink: 1;    /* Varsayılan - Küçülür */
    flex-shrink: 0;    /* Küçülmez */
    flex-shrink: 2;    /* Diğerlerinden 2 kat fazla küçülür */
}
```

### 💡 Örnek

```css
.item {
    flex-shrink: 0;  /* Sabit genişlik - küçülmez */
    width: 200px;
}
```

## 📐 `flex-basis`

Öğenin başlangıç boyutunu belirler.

```css
.item {
    flex-basis: auto;    /* Varsayılan - İçeriğe göre */
    flex-basis: 200px;   /* Sabit genişlik */
    flex-basis: 50%;     /* Yüzde */
    flex-basis: 0;       /* Minimum boyut */
}
```

### 💡 Örnek

```css
.item {
    flex-basis: 250px;  /* Başlangıç genişliği 250px */
}
```

## 🎯 `flex` (Kısa Yazım)

`flex-grow`, `flex-shrink` ve `flex-basis` özelliklerini birleştirir.

```css
.item {
    flex: 1;              /* flex-grow: 1, shrink: 1, basis: 0% */
    flex: 0 1 auto;        /* grow shrink basis */
    flex: 1 0 200px;      /* grow: 1, shrink: 0, basis: 200px */
    flex: none;            /* grow: 0, shrink: 0, basis: auto */
    flex: auto;            /* grow: 1, shrink: 1, basis: auto */
}
```

### 💡 Yaygın Kullanımlar

```css
/* Eşit dağılım */
.item {
    flex: 1;
}

/* Sabit genişlik */
.item {
    flex: 0 0 200px;
}

/* Esnek ama minimum boyut */
.item {
    flex: 1 1 200px;
}
```

## 📍 `align-self`

Tek bir öğenin çapraz eksende hizalanmasını belirler (container'ın `align-items`'ini geçersiz kılar).

```css
.item {
    align-self: auto;        /* Varsayılan - Container'dan alır */
    align-self: flex-start;  /* Başta */
    align-self: flex-end;    /* Sonda */
    align-self: center;      /* Ortada */
    align-self: stretch;     /* Uzatılır */
    align-self: baseline;    /* Baseline'a göre */
}
```

### 💡 Örnek

```css
.container {
    display: flex;
    align-items: center;
}

.special-item {
    align-self: flex-start;  /* Bu öğe üstte */
}
```

## 🔢 `order`

Öğelerin görüntülenme sırasını belirler.

```css
.item {
    order: 0;    /* Varsayılan */
    order: 1;    /* Daha sonra görünür */
    order: -1;   /* Daha önce görünür */
}
```

### 💡 Örnek

```css
.item1 {
    order: 3;  /* En sonda */
}

.item2 {
    order: 1;  /* En başta */
}

.item3 {
    order: 2;  /* Ortada */
}
```

## 💡 Pratik Örnekler

### Eşit Genişlikli Öğeler

```css
.container {
    display: flex;
}

.item {
    flex: 1;  /* Tüm öğeler eşit genişlikte */
}
```

### Sabit + Esnek Genişlik

```css
.sidebar {
    flex: 0 0 250px;  /* Sabit 250px */
}

.content {
    flex: 1;  /* Kalan alanı alır */
}
```

### Responsive Kartlar

```css
.card {
    flex: 1 1 300px;  /* Minimum 300px, esnek */
    max-width: 100%;
}
```

### Sıralama

```css
.first {
    order: -1;  /* En başta */
}

.last {
    order: 999;  /* En sonda */
}
```

### Özel Hizalama

```css
.container {
    display: flex;
    align-items: center;
}

.top-item {
    align-self: flex-start;  /* Üstte */
}

.bottom-item {
    align-self: flex-end;  /* Altta */
}
```

## 📊 Özellik Özeti

| Özellik | Açıklama | Varsayılan |
|---------|----------|------------|
| `flex-grow` | Büyüme faktörü | `0` |
| `flex-shrink` | Küçülme faktörü | `1` |
| `flex-basis` | Başlangıç boyutu | `auto` |
| `flex` | Kısa yazım | `0 1 auto` |
| `align-self` | Özel hizalama | `auto` |
| `order` | Görüntülenme sırası | `0` |

## ⚠️ Önemli Notlar

1. **flex: 1**: Öğenin mevcut alanı eşit paylaşmasını sağlar.

2. **flex: 0 0 auto**: Öğe sabit boyutta kalır, büyümez veya küçülmez.

3. **order**: Sadece görsel sırayı değiştirir, DOM sırasını değiştirmez.

4. **align-self**: Container'ın `align-items` değerini geçersiz kılar.

5. **flex-basis**: `width` veya `height` yerine kullanılabilir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📦 CSS FLEX CONTAINER ÖZELLİKLERİ

CSS Flexbox'ta container (ana kutu) özellikleri, flex item'ların nasıl düzenleneceğini kontrol eder.

## 🎯 `display: flex`

Elementi flex container yapar.

```css
.container {
    display: flex;
}
```

## 📐 `flex-direction`

Ana eksenin yönünü belirler.

```css
.container {
    flex-direction: row;           /* Varsayılan - Soldan sağa */
    flex-direction: row-reverse;   /* Sağdan sola */
    flex-direction: column;        /* Yukarıdan aşağıya */
    flex-direction: column-reverse; /* Aşağıdan yukarıya */
}
```

### 💡 Örnekler

```css
/* Yatay düzen */
.horizontal {
    display: flex;
    flex-direction: row;
}

/* Dikey düzen */
.vertical {
    display: flex;
    flex-direction: column;
}
```

## 🔄 `flex-wrap`

Öğelerin sarmalanıp sarmalanmayacağını belirler.

```css
.container {
    flex-wrap: nowrap;    /* Varsayılan - Sarmalanmaz */
    flex-wrap: wrap;      /* Sarmalanır */
    flex-wrap: wrap-reverse; /* Ters sarmalanır */
}
```

### 💡 Örnek

```css
.container {
    display: flex;
    flex-wrap: wrap;  /* Yer yoksa alt satıra geçer */
}
```

## 🔀 `flex-flow` (Kısa Yazım)

`flex-direction` ve `flex-wrap` özelliklerini birleştirir.

```css
.container {
    flex-flow: row wrap;
    /* flex-direction flex-wrap */
}
```

## 📏 `justify-content`

Ana eksende (main axis) öğelerin hizalanmasını belirler.

```css
.container {
    justify-content: flex-start;    /* Varsayılan - Başta */
    justify-content: flex-end;      /* Sonda */
    justify-content: center;        /* Ortada */
    justify-content: space-between; /* Aralarında eşit boşluk */
    justify-content: space-around;  /* Çevresinde eşit boşluk */
    justify-content: space-evenly;  /* Tüm aralıklarda eşit boşluk */
}
```

### 💡 Örnekler

```css
/* Ortalanmış */
.center {
    display: flex;
    justify-content: center;
}

/* Aralarında boşluk */
.spaced {
    display: flex;
    justify-content: space-between;
}
```

## 📐 `align-items`

Çapraz eksende (cross axis) öğelerin hizalanmasını belirler.

```css
.container {
    align-items: stretch;      /* Varsayılan - Uzatılır */
    align-items: flex-start;   /* Başta */
    align-items: flex-end;     /* Sonda */
    align-items: center;       /* Ortada */
    align-items: baseline;     /* Baseline'a göre */
}
```

### 💡 Örnek

```css
.container {
    display: flex;
    align-items: center;  /* Dikey ortalama */
}
```

## 📊 `align-content`

Çok satırlı flex container'larda satırların hizalanmasını belirler.

```css
.container {
    align-content: stretch;      /* Varsayılan */
    align-content: flex-start;   /* Başta */
    align-content: flex-end;     /* Sonda */
    align-content: center;       /* Ortada */
    align-content: space-between; /* Aralarında boşluk */
    align-content: space-around; /* Çevresinde boşluk */
}
```

### ⚠️ Not

`align-content` sadece `flex-wrap: wrap` olduğunda etkilidir.

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
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;  /* Öğeler arası 20px boşluk */
}
```

## 💡 Pratik Örnekler

### Ortalanmış İçerik

```css
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

### Yatay Menü

```css
.menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
```

### Kart Düzeni

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}
```

### Dikey Düzen

```css
.sidebar {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
```

## 📊 Özellik Özeti

| Özellik | Açıklama | Varsayılan |
|---------|----------|------------|
| `flex-direction` | Ana eksen yönü | `row` |
| `flex-wrap` | Sarmalama | `nowrap` |
| `justify-content` | Ana eksen hizalama | `flex-start` |
| `align-items` | Çapraz eksen hizalama | `stretch` |
| `align-content` | Çok satırlı hizalama | `stretch` |
| `gap` | Öğeler arası boşluk | `0` |

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


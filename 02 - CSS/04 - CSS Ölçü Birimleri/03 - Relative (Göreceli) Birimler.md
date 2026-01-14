# 🔄 CSS RELATIVE (GÖRECELİ) BİRİMLER

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) relative (göreceli) birimler, başka bir değere göre hesaplanan birimlerdir. Bu birimler responsive (duyarlı) tasarımlar için idealdir.

## 📏 em Birimi

Parent (üst) elementin font boyutuna göre hesaplanır.

```css
.parent {
    font-size: 16px;
}

.child {
    font-size: 1.5em;  /* 16px * 1.5 = 24px */
    padding: 1em;       /* 16px */
    margin: 2em;       /* 16px * 2 = 32px */
}
```

### Özellikler

- Parent elementin font boyutuna bağlıdır
- İç içe elementlerde birikimli etki yaratır
- Component içi ölçekleme için idealdir

### ⚠️ Dikkat

```css
.parent {
    font-size: 16px;
}

.child {
    font-size: 1.5em;  /* 24px */
}

.grandchild {
    font-size: 1.5em;  /* 24px * 1.5 = 36px (birikimli) */
}
```

## 📐 rem Birimi

Root (kök) elementin (`<html>`) font boyutuna göre hesaplanır.

```css
:root {
    font-size: 16px;
}

.element {
    font-size: 1.5rem;  /* 16px * 1.5 = 24px */
    padding: 1rem;       /* 16px */
    margin: 2rem;        /* 16px * 2 = 32px */
}
```

### Özellikler

- Root elementin font boyutuna bağlıdır
- Birikimli etki yaratmaz
- Responsive tasarım için idealdir
- Kullanıcı font boyutu tercihlerine saygı gösterir

### 💡 Best Practice

```css
:root {
    font-size: 16px;  /* Varsayılan */
}

@media (max-width: 768px) {
    :root {
        font-size: 14px;
    }
}

.element {
    font-size: 1.5rem;  /* Tüm ekranlarda tutarlı */
}
```

## 📊 ex Birimi

Font'un x yüksekliğine göre hesaplanır. Nadir kullanılır.

```css
.element {
    font-size: 2ex;  /* Font'un x yüksekliğinin 2 katı */
}
```

### Özellikler

- Font'un x yüksekliğine bağlıdır
- Font ailesine göre değişir
- Nadir kullanılır

## 🔤 ch Birimi

"0" (sıfır) karakterinin genişliğine göre hesaplanır.

```css
.element {
    width: 50ch;  /* 50 karakter genişliği */
}
```

### Özellikler

- Monospace fontlar için idealdir
- Metin genişliği kontrolü için kullanılır
- Kod blokları için uygundur

### 💡 Örnek

```css
.code-block {
    font-family: monospace;
    width: 80ch;  /* 80 karakter genişliği */
}
```

## 🖥️ Viewport Birimleri

Viewport (görünür alan) boyutuna göre hesaplanan birimlerdir.

### vw (Viewport Width)

Viewport genişliğinin %1'ine eşittir.

```css
.element {
    width: 50vw;  /* Viewport genişliğinin %50'si */
}
```

### vh (Viewport Height)

Viewport yüksekliğinin %1'ine eşittir.

```css
.element {
    height: 100vh;  /* Viewport yüksekliğinin %100'ü */
}
```

### vmin (Viewport Minimum)

Viewport genişliği ve yüksekliğinden küçük olanının %1'ine eşittir.

```css
.element {
    font-size: 5vmin;  /* Küçük boyutun %5'i */
}
```

### vmax (Viewport Maximum)

Viewport genişliği ve yüksekliğinden büyük olanının %1'ine eşittir.

```css
.element {
    font-size: 5vmax;  /* Büyük boyutun %5'i */
}
```

### 💡 Pratik Örnekler

```css
/* Fullscreen hero section */
.hero {
    width: 100vw;
    height: 100vh;
}

/* Responsive font size */
h1 {
    font-size: 5vw;  /* Viewport genişliğine göre */
}

/* Responsive padding */
.container {
    padding: 5vmin;  /* Her iki yönde de responsive */
}
```

## 📊 % (Yüzde) Birimi

Parent elementin ilgili özelliğine göre hesaplanır.

```css
.parent {
    width: 1000px;
}

.child {
    width: 50%;  /* 1000px * 0.5 = 500px */
    height: 25%; /* Parent yüksekliğinin %25'i */
}
```

### Özellikler

- Parent elemente göre hesaplanır
- Her özellik için farklı parent referansı olabilir
- Responsive tasarım için idealdir

### ⚠️ Dikkat

```css
.parent {
    width: 1000px;
    /* height belirtilmemiş */
}

.child {
    height: 50%;  /* Çalışmayabilir - parent height yok */
}
```

## 📊 Birim Karşılaştırması

| Birim | Referans | Birikimli | Kullanım |
|-------|----------|-----------|----------|
| `em` | Parent font-size | ✅ Evet | Component içi |
| `rem` | Root font-size | ❌ Hayır | Global ölçekleme |
| `ex` | Font x-height | - | Nadir |
| `ch` | "0" genişliği | - | Metin genişliği |
| `vw` | Viewport width | ❌ Hayır | Responsive genişlik |
| `vh` | Viewport height | ❌ Hayır | Responsive yükseklik |
| `vmin` | Viewport min | ❌ Hayır | Küçük boyut |
| `vmax` | Viewport max | ❌ Hayır | Büyük boyut |
| `%` | Parent özellik | ❌ Hayır | Responsive boyutlar |

## 💡 Best Practices

### Font Boyutları İçin

```css
:root {
    font-size: 16px;
}

body {
    font-size: 1rem;  /* 16px */
}

h1 {
    font-size: 2rem;  /* 32px */
}

h2 {
    font-size: 1.5rem;  /* 24px */
}
```

### Spacing İçin

```css
.container {
    padding: 1.5rem;  /* 24px */
    margin-bottom: 2rem;  /* 32px */
}

.card {
    margin: 1rem;  /* 16px */
}
```

### Responsive Genişlik İçin

```css
.container {
    width: 100%;
    max-width: 1200px;
}

.column {
    width: 50%;  /* Parent'a göre */
}

.fullscreen {
    width: 100vw;
    height: 100vh;
}
```

## ⚠️ Önemli Notlar

1. **em vs rem**: `em` birikimli etki yaratır, `rem` yaratmaz. Genellikle `rem` tercih edilir.

2. **Viewport Birimleri**: Scrollbar'ları hesaba katmaz, dikkatli kullanılmalıdır.

3. **Yüzde Kullanımı**: Parent elementin ilgili özelliği tanımlı olmalıdır.

4. **Performans**: Relative birimler absolute birimlere göre daha fazla hesaplama gerektirir.

5. **Erişilebilirlik**: `rem` birimi kullanıcı font boyutu tercihlerine saygı gösterir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


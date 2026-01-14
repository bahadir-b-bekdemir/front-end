# 📺 CSS MEDIA QUERIES

CSS Media Queries, farklı cihazlar ve ekran boyutları için farklı stiller uygulamak için kullanılır.

## 📋 Media Query Nedir?

Media Query, belirli koşullara göre CSS stillerini uygulayan bir özelliktir. Genellikle responsive tasarım için kullanılır.

## 🎯 Temel Kullanım

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
        padding: 10px;
    }
}
```

## 📐 Media Types (Medya Türleri)

```css
@media screen { }      /* Ekranlar */
@media print { }       /* Yazdırma */
@media speech { }      /* Ekran okuyucular */
@media all { }         /* Tümü */
```

## 🔍 Media Features (Medya Özellikleri)

### Width (Genişlik)

```css
@media (min-width: 768px) { }  /* Minimum genişlik */
@media (max-width: 768px) { }  /* Maksimum genişlik */
@media (width: 768px) { }      /* Tam genişlik */
```

### Height (Yükseklik)

```css
@media (min-height: 600px) { }
@media (max-height: 600px) { }
```

### Orientation (Yön)

```css
@media (orientation: portrait) { }   /* Dikey */
@media (orientation: landscape) { }  /* Yatay */
```

### Aspect Ratio (En-Boy Oranı)

```css
@media (aspect-ratio: 16/9) { }
@media (min-aspect-ratio: 16/9) { }
```

### Resolution (Çözünürlük)

```css
@media (min-resolution: 192dpi) { }
@media (min-resolution: 2dppx) { }  /* Dots per pixel */
```

### Color (Renk)

```css
@media (color) { }                    /* Renk desteği var mı */
@media (min-color: 8) { }             /* Minimum renk bit derinliği */
```

### Prefers-Reduced-Motion (Azaltılmış Hareket)

```css
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

### Prefers-Color-Scheme (Renk Şeması)

```css
@media (prefers-color-scheme: dark) {
    body {
        background-color: #1a1a1a;
        color: #ffffff;
    }
}

@media (prefers-color-scheme: light) {
    body {
        background-color: #ffffff;
        color: #333333;
    }
}
```

## 🔗 Logical Operators (Mantıksal Operatörler)

### `and` (Ve)

```css
@media (min-width: 768px) and (max-width: 1024px) {
    /* Tablet */
}
```

### `or` (Veya) - `,` ile

```css
@media (max-width: 768px), (orientation: portrait) {
    /* Mobil veya dikey */
}
```

### `not` (Değil)

```css
@media not screen {
    /* Ekran değil */
}
```

### `only` (Sadece)

```css
@media only screen and (min-width: 768px) {
    /* Sadece ekran ve minimum 768px */
}
```

## 💡 Pratik Örnekler

### Responsive Container

```css
.container {
    width: 100%;
    padding: 10px;
}

@media (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
        padding: 20px;
    }
}

@media (min-width: 992px) {
    .container {
        width: 970px;
        padding: 30px;
    }
}
```

### Responsive Grid

```css
.grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
}

@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 992px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

### Print Styles

```css
@media print {
    body {
        font-size: 12pt;
        color: black;
        background: white;
    }
    
    .no-print {
        display: none;
    }
    
    a::after {
        content: " (" attr(href) ")";
    }
}
```

### Dark Mode

```css
:root {
    --bg-color: #ffffff;
    --text-color: #333333;
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: #1a1a1a;
        --text-color: #ffffff;
    }
}

body {
    background-color: var(--bg-color);
    color: var(--text-color);
}
```

### Reduced Motion

```css
.element {
    animation: slideIn 0.5s ease;
}

@media (prefers-reduced-motion: reduce) {
    .element {
        animation: none;
    }
}
```

## 📊 Yaygın Breakpoints

```css
/* Mobil */
@media (max-width: 575.98px) { }

/* Tablet - Küçük */
@media (min-width: 576px) and (max-width: 767.98px) { }

/* Tablet - Büyük */
@media (min-width: 768px) and (max-width: 991.98px) { }

/* Desktop - Küçük */
@media (min-width: 992px) and (max-width: 1199.98px) { }

/* Desktop - Büyük */
@media (min-width: 1200px) { }
```

## ⚠️ Önemli Notlar

1. **Mobile-First**: Küçük ekranlardan başlayın, büyük ekranlara doğru genişletin.

2. **Breakpoint Seçimi**: İçeriğe göre breakpoint seçin, sabit değerlere bağlı kalmayın.

3. **Performance**: Gereksiz medya sorgularından kaçının.

4. **Testing**: Farklı cihazlarda test edin.

5. **Accessibility**: `prefers-reduced-motion` ve `prefers-color-scheme` gibi özellikleri destekleyin.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


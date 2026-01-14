# 📱 CSS RESPONSIVE TASARIM GİRİŞ

Responsive (Duyarlı) Tasarım, web sayfalarının farklı ekran boyutlarına ve cihazlara uyum sağlaması için kullanılan bir tasarım yaklaşımıdır.

## 📋 Responsive Tasarım Nedir?

Responsive tasarım, tek bir web sayfasının farklı cihazlarda (masaüstü, tablet, mobil) optimal şekilde görüntülenmesini sağlar. CSS Media Queries, Flexible Grids ve Flexible Images kullanılarak gerçekleştirilir.

## 🎯 Responsive Tasarım Prensipleri

1. **Fluid Grids** - Esnek ızgara sistemleri
2. **Flexible Images** - Esnek resimler
3. **Media Queries** - Medya sorguları

## 📐 Viewport Meta Tag

Mobil cihazlar için viewport ayarı yapılmalıdır.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Viewport Parametreleri

- `width=device-width` - Cihaz genişliğine göre
- `initial-scale=1.0` - Başlangıç yakınlaştırma
- `maximum-scale=1.0` - Maksimum yakınlaştırma
- `user-scalable=no` - Kullanıcı yakınlaştıramaz

## 📏 Breakpoints (Kırılma Noktaları)

Yaygın kullanılan breakpoint'ler:

```css
/* Mobil */
@media (max-width: 576px) { }

/* Tablet */
@media (min-width: 577px) and (max-width: 768px) { }

/* Küçük Desktop */
@media (min-width: 769px) and (max-width: 992px) { }

/* Desktop */
@media (min-width: 993px) and (max-width: 1200px) { }

/* Büyük Desktop */
@media (min-width: 1201px) { }
```

## 💡 Responsive Teknikler

### Flexible Units (Esnek Birimler)

```css
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.column {
    width: 50%;  /* Yüzde kullanımı */
}
```

### Media Queries

```css
.container {
    width: 100%;
}

@media (min-width: 768px) {
    .container {
        width: 750px;
    }
}

@media (min-width: 992px) {
    .container {
        width: 970px;
    }
}
```

### Flexible Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

## 🎯 Mobile-First Yaklaşımı

Önce mobil tasarım yapılır, sonra büyük ekranlar için genişletilir.

```css
/* Mobil önce */
.container {
    width: 100%;
    padding: 10px;
}

/* Tablet ve üzeri */
@media (min-width: 768px) {
    .container {
        width: 750px;
        padding: 20px;
    }
}

/* Desktop */
@media (min-width: 992px) {
    .container {
        width: 970px;
        padding: 30px;
    }
}
```

## 📊 Responsive Grid Sistemi

```css
.row {
    display: flex;
    flex-wrap: wrap;
}

.col {
    width: 100%;
}

@media (min-width: 768px) {
    .col-md-6 {
        width: 50%;
    }
    
    .col-md-4 {
        width: 33.333%;
    }
}

@media (min-width: 992px) {
    .col-lg-4 {
        width: 33.333%;
    }
    
    .col-lg-3 {
        width: 25%;
    }
}
```

## ⚠️ Önemli Notlar

1. **Viewport**: Mutlaka viewport meta tag ekleyin.

2. **Flexible Units**: Sabit pixel değerleri yerine yüzde, rem, em kullanın.

3. **Images**: Resimler için `max-width: 100%` kullanın.

4. **Testing**: Farklı cihazlarda test edin.

5. **Performance**: Gereksiz medya sorgularından kaçının.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


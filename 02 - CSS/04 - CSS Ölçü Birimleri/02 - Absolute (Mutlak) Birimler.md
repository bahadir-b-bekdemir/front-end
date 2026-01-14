# 📐 CSS ABSOLUTE (MUTLAK) BİRİMLER

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) absolute (mutlak) birimler, sabit değerlere sahip birimlerdir. Bu birimler ekran çözünürlüğünden veya başka bir değerden etkilenmez.

## 🖥️ Pixel (px)

En yaygın kullanılan absolute birimdir. Ekran çözünürlüğüne bağlıdır.

```css
div {
    width: 300px;
    height: 200px;
    font-size: 16px;
    padding: 10px;
    margin: 20px;
}
```

### Özellikler

- Ekran çözünürlüğüne bağlıdır
- En yaygın kullanılan birim
- Responsive tasarım için ideal değildir
- Border, shadow gibi küçük değerler için uygundur

## 📄 Point (pt)

Baskı işlemleri için kullanılan birimdir. 1 inç = 72 punto.

```css
@media print {
    body {
        font-size: 12pt;
        margin: 0.5in;
    }
}
```

### Dönüşüm

- 1 pt = 1.333333 px (96 DPI ekran için)
- 1 pt = 0.352778 mm
- 1 pt = 0.01388889 in

## 📏 Pica (pc)

Baskı işlemleri için kullanılan birimdir. 1 pica = 12 punto.

```css
@media print {
    .column {
        width: 30pc;
    }
}
```

### Dönüşüm

- 1 pc = 16 px
- 1 pc = 12 pt
- 1 pc = 4.233333 mm

## 📐 Milimetre (mm)

Fiziksel uzunluk ölçüsü. Baskı işlemleri için kullanılır.

```css
@media print {
    .page {
        width: 210mm;  /* A4 genişlik */
        height: 297mm; /* A4 yükseklik */
    }
}
```

### Dönüşüm

- 1 mm = 3.779528 px
- 1 mm = 2.834646 pt
- 1 mm = 0.1 cm

## 📏 Santimetre (cm)

Fiziksel uzunluk ölçüsü. Baskı işlemleri için kullanılır.

```css
@media print {
    .document {
        width: 21cm;
        height: 29.7cm;
    }
}
```

### Dönüşüm

- 1 cm = 37.795276 px
- 1 cm = 28.346457 pt
- 1 cm = 10 mm

## 📐 İnç (in)

Fiziksel uzunluk ölçüsü. Baskı işlemleri için kullanılır. 1 inç = 2.54 cm.

```css
@media print {
    .page {
        width: 8.5in;
        height: 11in;
    }
}
```

### Dönüşüm

- 1 in = 96 px
- 1 in = 72 pt
- 1 in = 6 pc
- 1 in = 25.4 mm
- 1 in = 2.54 cm

## 📊 Birim Karşılaştırma Tablosu

| Birim | Pixel (px) | Point (pt) | Pica (pc) | mm | cm | in |
|-------|------------|------------|-----------|----|----|----|
| **1 px =** | 1 px | 0.75 pt | 0.0625 pc | 0.264583 mm | 0.02645833 cm | 0.01041667 in |
| **1 pt =** | 1.333333 px | 1 pt | 0.08333333 pc | 0.352778 mm | 0.03527778 cm | 0.01388889 in |
| **1 pc =** | 16 px | 12 pt | 1 pc | 4.233333 mm | 0.423333 cm | 0.166667 in |
| **1 mm =** | 3.779528 px | 2.834646 pt | 0.236221 pc | 1 mm | 0.1 cm | 0.03937008 in |
| **1 cm =** | 37.795276 px | 28.346457 pt | 2.362205 pc | 10 mm | 1 cm | 0.393701 in |
| **1 in =** | 96 px | 72 pt | 6 pc | 25.4 mm | 2.54 cm | 1 in |

## 💡 Kullanım Örnekleri

### Ekran İçin

```css
/* Pixel kullanımı - Ekran için */
.container {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
}

.button {
    padding: 10px 20px;
    font-size: 16px;
    border: 1px solid #ccc;
}
```

### Baskı İçin

```css
@media print {
    body {
        font-size: 12pt;
        line-height: 1.5;
    }
    
    .page {
        width: 21cm;
        height: 29.7cm;
        margin: 2cm;
    }
    
    h1 {
        font-size: 18pt;
        margin-bottom: 0.5cm;
    }
}
```

## ⚠️ Önemli Notlar

1. **Ekran vs Baskı**: Pixel ekran için, pt/cm/mm/in baskı için kullanılmalıdır.

2. **Responsive Tasarım**: Absolute birimler responsive tasarım için ideal değildir.

3. **DPI Farklılıkları**: Farklı ekranlarda pixel boyutları değişebilir.

4. **Kullanıcı Tercihleri**: Absolute birimler kullanıcı font boyutu tercihlerine saygı göstermez.

5. **Baskı Medya Sorguları**: Baskı için `@media print` kullanılmalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


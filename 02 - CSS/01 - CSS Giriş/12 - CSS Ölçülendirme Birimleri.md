# 📏 CSS'DE ÖLÇÜLENDİRME BİRİMLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) genişlik, yükseklik, konum, boyut, kalınlık vb. ölçülendirme işlemlerinde kullanılan farklı birimler bulunmaktadır. Bu birimler sayılar ile birlikte kullanılmaktadır.

## 🔢 Sayı Türleri

CSS ölçülendirme birimlerinde kullanılan sayılar üç farklı şekildedir:

- **Tam sayılar**: `10`, `20`, `100` vb.
- **Ondalıklı sayılar**: `10.5`, `20.75`, `0.5` vb.
- **Yüzdeler**: `50%`, `100%`, `25%` vb.

**⚠️ Not:** Bazı durumlarda ölçülendirme birimlerinde kullanılan sayılar negatif değerler de alabilirler. En önemli kural hangi sayının hangi birim ile kullanılması gerektiğini bilmektir.

## 📊 Ölçülendirme Türleri

CSS'de **relative (göreceli)** ve **absolute (kesin)** olmak üzere 2 farklı ölçülendirme türü vardır. Her iki türün de kendilerine has kullanılan birimleri mevcuttur.

---

## 🔄 Relative (Göreceli) Ölçülendirme Birimleri

Göreceli ölçülendirme birimleri, başka bir değere göre hesaplanan birimlerdir. Bu birimler responsive (duyarlı) tasarımlar için idealdir.

| Birim | Açıklama | Örnek |
|-------|----------|-------|
| `em` | Boyuta bağlı ölçülendirme birimidir. Atanmış boyut değerine göre hesaplanarak bulunur. Boyut atanmamış ise, varsayılan boyut olarak font (yazı tipi) ailesinde yer alan "M" harfinin genişliğini ve yüksekliğini baz alır. | Boyut 12px atanmış ise; `1em = 12px`, boyut 30px atanmış ise; `1em = 30px`'dir. |
| `rem` | Boyuta bağlı ölçülendirme birimidir. Belgenin root (kök) elementine (`<html>`) atanmış boyut değerine göre hesaplanarak bulunur. | Boyut 12px atanmış ise; `1rem = 12px`, boyut 30px atanmış ise; `1rem = 30px`'dir. |
| `ex` | Font (Yazı tipi) boyutuna bağlı ölçülendirme birimidir. Font boyutunun x yüksekliği değerine göre hesaplanarak bulunur. Başka bir deyiş ile font'un orta işaretidir. Değişiklik gösterebilir ve bu nedenle nadir kullanılan bir ölçülendirme birimidir. | Font boyutuna göre değişir. |
| `ch` | "0" genişliğine bağlı ölçülendirme birimidir. Atanmış boyut değerine göre hesaplanarak bulunur. Boyut atanmamış ise, varsayılan boyut olarak font ailesinde yer alan "0" rakamının genişliğini baz alır. | Boyut 12px atanmış ise; `1ch = 6px`, boyut 30px atanmış ise; `1ch = 15px`'dir. |
| `vw` | Viewport (Görünür alan) genişlik boyutuna bağlı ölçülendirme birimidir. Viewport genişlik boyutu değerine göre hesaplanarak bulunur. Hesaplama formülü, viewport genişliğinin %1'i olarak belirlenmiştir. | Viewport genişlik boyutu 1200px ise; `1vw = 12px`, viewport genişlik boyutu 992px ise; `1vw = 9.92px`'dir. |
| `vh` | Viewport (Görünür alan) yükseklik boyutuna bağlı ölçülendirme birimidir. Viewport yükseklik boyutu değerine göre hesaplanarak bulunur. Hesaplama formülü, viewport yüksekliğinin %1'i olarak belirlenmiştir. | Viewport yükseklik boyutu 900px ise; `1vh = 9px`, viewport yükseklik boyutu 768px ise; `1vh = 7.68px`'dir. |
| `vmin` | Viewport boyutlarına bağlı ölçülendirme birimidir. Viewport boyutlarının diğerine kıyasla daha küçük olanının değerine göre hesaplanarak bulunur. Hesaplama formülü, viewport genişliğinin veya yüksekliğinin küçük olanı baz alınarak %1'i olarak belirlenmiştir. | Viewport genişlik veya yükseklik boyutunun küçük olanı 1000px ise; `1vmin = 10px`'dir. |
| `vmax` | Viewport boyutlarına bağlı ölçülendirme birimidir. Viewport boyutlarının diğerine kıyasla daha büyük olanının değerine göre hesaplanarak bulunur. Hesaplama formülü, viewport genişliğinin veya yüksekliğinin büyük olanı baz alınarak %1'i olarak belirlenmiştir. | Viewport genişlik veya yükseklik boyutunun büyük olanı 1000px ise; `1vmax = 10px`'dir. |
| `%` | Yüzdesel ölçülendirme birimidir. Daima başka bir ölçülendirme birimine orantılı olarak çalışır. Hesaplama formülü, üst ölçülendirme değeri / (bölü) 100 * (çarpı) değerdir. | Üst ölçülendirme boyutu değeri 1000px ise; `50% = 500px`'dir. |

### 💡 Relative Birim Örnekleri

```css
/* em - Parent elementin font boyutuna göre */
.parent {
    font-size: 16px;
}

.child {
    font-size: 1.5em; /* 16px * 1.5 = 24px */
    padding: 1em; /* 16px */
}

/* rem - Root elementin font boyutuna göre */
:root {
    font-size: 16px;
}

.element {
    font-size: 1.5rem; /* 16px * 1.5 = 24px */
    margin: 2rem; /* 16px * 2 = 32px */
}

/* Viewport birimleri - Responsive tasarım için */
.full-width {
    width: 100vw; /* Viewport genişliğinin %100'ü */
}

.full-height {
    height: 100vh; /* Viewport yüksekliğinin %100'ü */
}

.half-viewport {
    width: 50vw; /* Viewport genişliğinin %50'si */
    height: 50vh; /* Viewport yüksekliğinin %50'si */
}

/* Yüzde - Parent elemente göre */
.container {
    width: 1000px;
}

.box {
    width: 50%; /* 1000px * 0.5 = 500px */
    height: 25%; /* Parent yüksekliğinin %25'i */
}
```

---

## 📐 Absolute (Kesin) Ölçülendirme Birimleri

Kesin ölçülendirme birimleri, sabit değerlere sahip birimlerdir. Bu birimler genellikle baskı işlemleri için kullanılır.

| Birim | Açıklama | Kullanım Alanı |
|-------|----------|----------------|
| `px` | Pixel (Piksel) ölçülendirme birimidir. Ekran çözünürlüğüne bağlıdır. | Ekran işlemleri için en yaygın kullanılan birimdir. |
| `pt` | Point (Punto) ölçülendirme birimidir. 1 inç = 72 punto. | Baskı işlemleri için kullanılır. |
| `pc` | Pica (Pika) ölçülendirme birimidir. 1 pica = 12 punto. | Baskı işlemleri için kullanılır. |
| `mm` | Milimetre uzunluk ölçüsüne bağlı ölçülendirme birimidir. | Baskı işlemleri için kullanılır. |
| `cm` | Santimetre uzunluk ölçüsüne bağlı ölçülendirme birimidir. | Baskı işlemleri için kullanılır. |
| `in` | İnç uzunluk ölçüsüne bağlı ölçülendirme birimidir. 1 inç = 2.54 cm. | Baskı işlemleri için kullanılır. |

### 📊 Absolute Birimlerin Karşılaştırılması

| Birim | Pixel (px) | Point (pt) | Pica (pc) | mm | cm | in |
|-------|------------|------------|-----------|----|----|----|
| **1 px =** | 1 px | 0.75 pt | 0.0625 pc | 0.264583 mm | 0.02645833 cm | 0.01041667 in |
| **1 pt =** | 1.333333 px | 1 pt | 0.08333333 pc | 0.352778 mm | 0.03527778 cm | 0.01388889 in |
| **1 pc =** | 16 px | 12 pt | 1 pc | 4.233333 mm | 0.423333 cm | 0.166667 in |
| **1 mm =** | 3.779528 px | 2.834646 pt | 0.236221 pc | 1 mm | 0.1 cm | 0.03937008 in |
| **1 cm =** | 37.795276 px | 28.346457 pt | 2.362205 pc | 10 mm | 1 cm | 0.393701 in |
| **1 in =** | 96 px | 72 pt | 6 pc | 25.4 mm | 2.54 cm | 1 in |

### 💡 Absolute Birim Örnekleri

```css
/* Pixel - En yaygın kullanılan birim */
.box {
    width: 300px;
    height: 200px;
    font-size: 16px;
}

/* Point - Baskı için */
@media print {
    .text {
        font-size: 12pt;
        margin: 0.5in;
    }
}
```

---

## 🎯 Ölçülendirme Birimlerinin Kullanım Alanları

### ✅ Tavsiye Edilen Kullanım Alanları

#### Ekran İşlemleri İçin (Genel)
- `px` - Pixel, en yaygın kullanılan birim
- `em` - Parent elemente göre ölçeklenir
- `%` - Yüzde, parent elemente göre ölçeklenir

#### Ekran İşlemleri İçin (Nadiren)
- `rem` - Root elemente göre ölçeklenir (modern projelerde yaygın)
- `ex` - X yüksekliğine göre
- `ch` - Karakter genişliğine göre
- `vw`, `vh`, `vmin`, `vmax` - Viewport birimleri (responsive tasarım için)

#### Baskı İşlemleri İçin
- `px` - Pixel
- `pt` - Point (punto)
- `pc` - Pica
- `mm` - Milimetre
- `cm` - Santimetre
- `in` - İnç
- `em` - Em
- `%` - Yüzde

#### Baskı İşlemleri İçin (Nadiren)
- `ex` - X yüksekliğine göre
- `rem` - Root elemente göre
- `ch` - Karakter genişliğine göre

### ❌ Tavsiye Edilmeyen Kullanım Alanları

#### Ekran İşlemleri İçin
- `pt` - Point (punto)
- `pc` - Pica
- `mm` - Milimetre
- `cm` - Santimetre
- `in` - İnç

**Neden?** Bu birimler fiziksel ölçü birimleridir ve ekran çözünürlüğüne göre değişkenlik gösterir.

#### Baskı İşlemleri İçin
- `vw` - Viewport width
- `vh` - Viewport height
- `vmin` - Viewport minimum
- `vmax` - Viewport maximum

**Neden?** Bu birimler ekran görünür alanına bağlıdır ve baskı için uygun değildir.

---

## 💡 Best Practices (En İyi Uygulamalar)

### 1. **Responsive Tasarım İçin**
```css
/* rem kullanımı - Önerilen */
:root {
    font-size: 16px;
}

.container {
    font-size: 1.5rem; /* 24px */
    padding: 1rem; /* 16px */
}

/* Viewport birimleri - Fullscreen için */
.hero {
    width: 100vw;
    height: 100vh;
}
```

### 2. **Font Boyutları İçin**
```css
/* rem - Tutarlılık için */
body {
    font-size: 1rem; /* 16px */
}

h1 {
    font-size: 2rem; /* 32px */
}

h2 {
    font-size: 1.5rem; /* 24px */
}
```

### 3. **Spacing (Boşluk) İçin**
```css
/* rem veya em - Ölçeklenebilir boşluklar */
.card {
    padding: 1.5rem; /* 24px */
    margin-bottom: 2rem; /* 32px */
}
```

### 4. **Genişlik ve Yükseklik İçin**
```css
/* Yüzde - Responsive için */
.container {
    width: 100%;
    max-width: 1200px;
}

.column {
    width: 50%; /* Parent'a göre */
}
```

---

## ⚠️ Önemli Notlar

1. **em vs rem**: `em` parent elemente göre, `rem` root elemente göre ölçeklenir. `rem` kullanımı genellikle daha tutarlı sonuçlar verir.

2. **Viewport Birimleri**: `vw` ve `vh` birimleri scrollbar'ları hesaba katmaz, bu yüzden dikkatli kullanılmalıdır.

3. **Yüzde Kullanımı**: Yüzde değerleri her zaman parent elemente göre hesaplanır. Parent elementin boyutu yoksa, yüzde çalışmayabilir.

4. **Pixel Kullanımı**: `px` birimi responsive tasarım için ideal değildir, ancak bazı durumlarda (border, shadow vb.) gerekli olabilir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

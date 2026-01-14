# 📋 CSS CHEAT SHEET

Hızlı referans için CSS özellikleri ve değerleri. Her özellik için açıklamalar, kullanım senaryoları ve pratik örnekler.

---

## 📐 BOX MODEL

Box Model, her HTML elementinin içerik (content), padding, border ve margin'den oluşan yapısıdır.

### Margin (Dış Boşluk)
Elementin dışındaki boşluk. Diğer elementlerle arasındaki mesafeyi belirler.

```css
/* Tüm yönlerde aynı boşluk */
margin: 10px;

/* Üst/Alt ve Sol/Sağ */
margin: 10px 20px;  /* Üst/Alt: 10px, Sol/Sağ: 20px */

/* Üst, Sağ, Alt, Sol (saat yönü) */
margin: 10px 20px 15px 5px;

/* Yönlere özel */
margin-top: 10px;
margin-right: 20px;
margin-bottom: 15px;
margin-left: 5px;

/* Ortalama için */
margin: 0 auto;  /* Yatay ortalama */
```

**💡 Kullanım:** Elementler arası boşluk, sayfa kenarlarından uzaklık, ortalama için.

**⚠️ Not:** Dikey margin'ler birleşir (collapse), yatay margin'ler birleşmez.

### Padding (İç Boşluk)
Elementin içeriği ile border arasındaki boşluk.

```css
/* Margin ile aynı kullanım şekli */
padding: 10px;
padding: 10px 20px;
padding: 10px 20px 15px 5px;

padding-top: 10px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 5px;
```

**💡 Kullanım:** İçerik ile kenarlık arası boşluk, buton içi boşluk, kart içi boşluk.

### Border (Kenarlık)
Elementin etrafındaki çizgi.

```css
/* Kısa yazım: width style color */
border: 2px solid #000;

/* Ayrı ayrı */
border-width: 2px;
border-style: solid;  /* solid, dashed, dotted, double, groove, ridge, inset, outset, none */
border-color: #000;

/* Yönlere özel */
border-top: 2px solid red;
border-right: 3px dashed blue;
border-bottom: 1px dotted green;
border-left: 4px double orange;

/* Köşe yuvarlama */
border-radius: 5px;  /* Tüm köşeler */
border-radius: 10px 20px;  /* Üst-sol/alt-sağ ve üst-sağ/alt-sol */
border-top-left-radius: 5px;
border-top-right-radius: 10px;
border-bottom-right-radius: 15px;
border-bottom-left-radius: 20px;
```

**💡 Kullanım:** Elementleri vurgulama, ayırma, dekoratif amaçlar.

### Box Sizing
Kutu modelinin boyut hesaplama yöntemi.

```css
/* Padding ve border, width/height'e dahil edilir (ÖNERİLEN) */
box-sizing: border-box;

/* Padding ve border, width/height'e eklenir (Varsayılan) */
box-sizing: content-box;
```

**💡 Kullanım:** `border-box` kullanımı daha öngörülebilir boyutlar sağlar.

**💡 Best Practice:**
```css
* {
    box-sizing: border-box;
}
```

---

## 📏 DIMENSIONS (Boyutlar)

Elementlerin genişlik ve yükseklik değerleri.

```css
/* Genişlik */
width: 100%;        /* Parent'ın %100'ü */
width: 300px;       /* Sabit pixel değeri */
width: 50vw;        /* Viewport genişliğinin %50'si */
width: auto;        /* İçeriğe göre otomatik */
min-width: 200px;  /* Minimum genişlik */
max-width: 1200px; /* Maksimum genişlik */

/* Yükseklik */
height: 100%;      /* Parent'ın %100'ü */
height: 300px;     /* Sabit pixel değeri */
height: 50vh;      /* Viewport yüksekliğinin %50'si */
height: auto;      /* İçeriğe göre otomatik */
min-height: 200px; /* Minimum yükseklik */
max-height: 600px; /* Maksimum yükseklik */
```

**💡 Kullanım Senaryoları:**
- `width: 100%` - Responsive container'lar için
- `max-width: 1200px` - İçerik genişliğini sınırlama
- `min-height: 100vh` - Full screen yükseklik
- `width: auto` - İçeriğe göre ayarlama

---

## 🎨 COLORS & BACKGROUNDS

### Color (Renk)
Metin rengini belirler.

```css
/* Hex renk kodu (En yaygın) */
color: #ff0000;      /* Kırmızı */
color: #00ff00;      /* Yeşil */
color: #0000ff;      /* Mavi */
color: #fff;         /* Beyaz (kısa) */
color: #000;         /* Siyah (kısa) */

/* RGB */
color: rgb(255, 0, 0);        /* Kırmızı */
color: rgb(0, 255, 0);        /* Yeşil */

/* RGBA (Alpha kanalı ile şeffaflık) */
color: rgba(255, 0, 0, 0.5);  /* %50 şeffaf kırmızı */

/* HSL (Hue, Saturation, Lightness) */
color: hsl(0, 100%, 50%);     /* Kırmızı */
color: hsl(120, 100%, 50%);   /* Yeşil */

/* İsimlendirilmiş renkler */
color: red;
color: blue;
color: green;
color: transparent;  /* Şeffaf */
```

**💡 Kullanım:** Metin rengi, link rengi, border rengi.

### Background (Arka Plan)
Elementin arka planını belirler.

```css
/* Arka plan rengi */
background-color: #fff;
background-color: rgba(0, 0, 0, 0.5);  /* Şeffaf siyah */

/* Arka plan resmi */
background-image: url('image.jpg');
background-image: linear-gradient(to right, red, blue);

/* Arka plan tekrarı */
background-repeat: no-repeat;  /* Tekrarlama */
background-repeat: repeat;     /* Tekrarla (varsayılan) */
background-repeat: repeat-x;   /* Sadece yatay */
background-repeat: repeat-y;   /* Sadece dikey */

/* Arka plan konumu */
background-position: center;   /* Ortala */
background-position: top left;
background-position: 50% 50%;  /* X% Y% */
background-position: 10px 20px; /* Xpx Ypx */

/* Arka plan boyutu */
background-size: cover;        /* Kaplar, kırpılabilir */
background-size: contain;     /* Sığdırır, boşluk kalabilir */
background-size: 100% 100%;    /* Tam boyut */
background-size: 200px 150px;  /* Sabit boyut */

/* Arka plan sabitleme (scroll ile hareket etmez) */
background-attachment: fixed;
background-attachment: scroll;  /* Varsayılan */

/* Kısa yazım (shorthand) */
background: #fff url('img.jpg') no-repeat center/cover;
/* color image repeat position/size */
```

**💡 Kullanım Senaryoları:**
- Hero section'lar için büyük arka plan resimleri
- Pattern'ler için tekrarlanan arka planlar
- Gradient arka planlar
- Şeffaf overlay'ler

---

## 📝 TYPOGRAPHY (Tipografi)

### Font (Yazı Tipi)

```css
/* Font ailesi */
font-family: Arial, sans-serif;
font-family: "Times New Roman", serif;
font-family: "Courier New", monospace;
/* Fallback: İlk bulunamazsa ikinci kullanılır */

/* Font boyutu */
font-size: 16px;      /* Pixel */
font-size: 1rem;      /* Root font size'a göre (ÖNERİLEN) */
font-size: 1em;       /* Parent font size'a göre */
font-size: 100%;      /* Parent'a göre yüzde */
font-size: 2vw;       /* Viewport genişliğine göre */

/* Font kalınlığı */
font-weight: normal;  /* 400 */
font-weight: bold;    /* 700 */
font-weight: 100;     /* Thin */
font-weight: 300;     /* Light */
font-weight: 400;     /* Normal */
font-weight: 500;     /* Medium */
font-weight: 700;     /* Bold */
font-weight: 900;     /* Black */

/* Font stili */
font-style: normal;
font-style: italic;   /* İtalik */
font-style: oblique;  /* Eğik */

/* Font varyantı */
font-variant: normal;
font-variant: small-caps;  /* Küçük büyük harf */

/* Kısa yazım (shorthand) */
font: italic bold 16px/1.5 Arial, sans-serif;
/* style weight size/line-height family */
```

**💡 Best Practice:**
```css
body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    font-size: 1rem;  /* 16px varsayılan */
    line-height: 1.6;
}
```

### Text (Metin)

```css
/* Hizalama */
text-align: left;      /* Sol */
text-align: right;     /* Sağ */
text-align: center;    /* Orta */
text-align: justify;   /* İki yana yasla */

/* Dekorasyon */
text-decoration: none;         /* Yok */
text-decoration: underline;   /* Alt çizgi */
text-decoration: overline;     /* Üst çizgi */
text-decoration: line-through; /* Üstü çizili */

/* Dönüşüm */
text-transform: none;      /* Değişiklik yok */
text-transform: uppercase; /* TÜMÜ BÜYÜK */
text-transform: lowercase; /* tümü küçük */
text-transform: capitalize; /* İlk Harfler Büyük */

/* Girinti */
text-indent: 20px;  /* İlk satır girintisi */

/* Gölge */
text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
/* x-offset y-offset blur-radius color */

/* Harf aralığı */
letter-spacing: 2px;   /* Harfler arası boşluk */
letter-spacing: -1px;  /* Negatif değer */

/* Kelime aralığı */
word-spacing: 5px;     /* Kelimeler arası boşluk */

/* Satır yüksekliği */
line-height: 1.5;       /* Font size'ın 1.5 katı (ÖNERİLEN) */
line-height: 24px;      /* Sabit değer */
line-height: 150%;      /* Yüzde */

/* Boşluk işleme */
white-space: normal;    /* Varsayılan */
white-space: nowrap;    /* Satır kırılmaz */
white-space: pre;       /* Önceden biçimlendirilmiş */
white-space: pre-wrap;  /* Satır kırılır, boşluklar korunur */
white-space: pre-line;  /* Satır kırılır, boşluklar birleşir */
```

**💡 Kullanım Senaryoları:**
- `text-align: center` - Başlıklar, butonlar
- `text-decoration: none` - Link alt çizgisini kaldırma
- `text-transform: uppercase` - Buton metinleri
- `line-height: 1.6` - Okunabilirlik için

---

## 📍 POSITIONING (Pozisyonlandırma)

### Position
Elementin konumlandırma yöntemi.

```css
/* Static - Varsayılan, normal akış */
position: static;

/* Relative - Normal akışta, kaydırılabilir */
position: relative;
top: 10px;      /* Kendi konumundan 10px aşağı */
left: 20px;     /* Kendi konumundan 20px sağa */

/* Absolute - En yakın positioned parent'a göre */
position: absolute;
top: 0;
right: 0;
/* Parent'ın üst sağ köşesine yerleşir */

/* Fixed - Viewport'a göre, scroll'da sabit kalır */
position: fixed;
top: 0;
left: 0;
width: 100%;
/* Sabit header/footer için */

/* Sticky - Scroll'da belirli noktada sabitlenir */
position: sticky;
top: 0;
/* Scroll ile top: 0'a ulaştığında sabitlenir */
```

**💡 Kullanım Senaryoları:**
- `relative` - Tooltip, overlay için referans noktası
- `absolute` - Modal, dropdown menüler
- `fixed` - Navigation bar, chat widget
- `sticky` - Tablo başlıkları, navigation

### Z-Index
Elementlerin üst üste gelme sırası.

```css
z-index: 1;     /* Düşük */
z-index: 10;    /* Orta */
z-index: 100;   /* Yüksek */
z-index: 9999;  /* Çok yüksek (modal için) */
```

**💡 Kullanım:** Overlay'ler, modal'lar, dropdown'lar için.

**⚠️ Not:** Sadece `position: relative/absolute/fixed/sticky` elementler için çalışır.

---

## 🎭 DISPLAY

Elementin görüntülenme türü.

```css
display: block;         /* Blok seviyesi (div, p, h1) */
display: inline;        /* Satır içi (span, a, strong) */
display: inline-block;  /* Hem inline hem block özellikleri */
display: flex;          /* Flexbox container */
display: grid;         /* Grid container */
display: none;          /* Gizli, yer kaplamaz */
display: table;         /* Tablo gibi davranır */
display: inline-flex;   /* Inline flex container */
display: inline-grid;   /* Inline grid container */
```

**💡 Kullanım Senaryoları:**
- `block` - Tam genişlik, yeni satır
- `inline` - Sadece içerik kadar, yan yana
- `inline-block` - Yatay menü öğeleri
- `flex` - Modern layout için
- `grid` - İki boyutlu layout için
- `none` - Responsive'de gizleme

---

## 🔄 FLEXBOX

Tek boyutlu (satır veya sütun) esnek layout sistemi.

### Container Özellikleri

```css
display: flex;

/* Yön */
flex-direction: row;            /* Varsayılan - Yatay */
flex-direction: column;         /* Dikey */
flex-direction: row-reverse;    /* Ters yatay */
flex-direction: column-reverse; /* Ters dikey */

/* Sarmalama */
flex-wrap: nowrap;    /* Varsayılan - Sarmaz */
flex-wrap: wrap;      /* Sarmalar */
flex-wrap: wrap-reverse; /* Ters sarmalar */

/* Ana eksen hizalama (yatay) */
justify-content: flex-start;    /* Başta */
justify-content: flex-end;       /* Sonda */
justify-content: center;         /* Ortada */
justify-content: space-between;  /* Aralarında eşit boşluk */
justify-content: space-around;   /* Etrafında eşit boşluk */
justify-content: space-evenly;   /* Tamamen eşit boşluk */

/* Çapraz eksen hizalama (dikey) */
align-items: flex-start;    /* Üstte */
align-items: flex-end;      /* Altta */
align-items: center;        /* Ortada */
align-items: stretch;       /* Uzatılır (varsayılan) */
align-items: baseline;      /* Baseline'a göre */

/* Çoklu satır hizalama */
align-content: flex-start;
align-content: center;
align-content: space-between;

/* Boşluk */
gap: 20px;              /* Tüm yönlerde */
gap: 10px 20px;         /* Satır Sütun */
row-gap: 10px;          /* Sadece satır */
column-gap: 20px;       /* Sadece sütun */
```

### Item Özellikleri

```css
/* Büyüme faktörü */
flex-grow: 0;    /* Büyümez (varsayılan) */
flex-grow: 1;    /* Mevcut alanı paylaşır */

/* Küçülme faktörü */
flex-shrink: 1;  /* Küçülür (varsayılan) */
flex-shrink: 0;  /* Küçülmez */

/* Başlangıç boyutu */
flex-basis: auto;    /* İçeriğe göre */
flex-basis: 200px;   /* Sabit genişlik */
flex-basis: 50%;     /* Yüzde */

/* Kısa yazım */
flex: 1;              /* flex: 1 1 0% - Eşit paylaşım */
flex: 0 0 200px;      /* Sabit 200px */
flex: 1 1 auto;       /* Esnek ama minimum boyut */

/* Özel hizalama */
align-self: flex-start;
align-self: center;
align-self: flex-end;

/* Sıralama */
order: 0;    /* Varsayılan */
order: 1;    /* Daha sonra */
order: -1;   /* Daha önce */
```

**💡 Kullanım Senaryoları:**
- Navigation menüleri
- Kart düzenleri
- Form düzenleri
- İçerik hizalama

**💡 Pratik Örnekler:**
```css
/* Ortalanmış içerik */
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

/* Eşit genişlikli öğeler */
.equal-width {
    display: flex;
}
.equal-width > * {
    flex: 1;
}
```

---

## 📐 GRID

İki boyutlu (satır ve sütun) layout sistemi.

### Container Özellikleri

```css
display: grid;

/* Sütun tanımları */
grid-template-columns: 200px 200px 200px;  /* 3 sabit sütun */
grid-template-columns: 1fr 1fr 1fr;       /* 3 eşit sütun */
grid-template-columns: repeat(3, 1fr);    /* 3 eşit sütun */
grid-template-columns: 1fr 2fr 1fr;        /* Orta sütun 2 kat */
grid-template-columns: auto 1fr auto;      /* Kenarlar otomatik */
grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); /* Responsive */

/* Satır tanımları */
grid-template-rows: 100px auto 100px;
grid-template-rows: repeat(3, auto);

/* Alan isimleri */
grid-template-areas:
    "header header header"
    "sidebar content content"
    "footer footer footer";

/* Otomatik sütun/satır boyutları */
grid-auto-columns: 100px;
grid-auto-rows: 150px;

/* Boşluk */
gap: 20px;
gap: 10px 20px;      /* Satır Sütun */
row-gap: 10px;
column-gap: 20px;

/* Hizalama */
justify-items: start;    /* Sütun ekseninde */
align-items: center;     /* Satır ekseninde */
place-items: center;     /* Her iki eksende */

/* Container hizalama */
justify-content: center;
align-content: center;
```

### Item Özellikleri

```css
/* Konum */
grid-column: 1 / 3;      /* 1. sütundan 3. sütuna */
grid-row: 1 / 2;         /* 1. satırdan 2. satıra */
grid-column: span 2;      /* 2 sütun kaplar */
grid-row: span 3;         /* 3 satır kaplar */

/* Ayrı özellikler */
grid-column-start: 1;
grid-column-end: 3;
grid-row-start: 1;
grid-row-end: 2;

/* Alan ismi */
grid-area: header;

/* Özel hizalama */
justify-self: center;
align-self: center;
place-self: center;
```

**💡 Kullanım Senaryoları:**
- Sayfa düzenleri (header, sidebar, content, footer)
- Karmaşık layoutlar
- Magazine tarzı düzenler
- Responsive kart grid'leri

**💡 Pratik Örnek:**
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

---

## 🎨 BORDERS & OUTLINES

### Border (Kenarlık)
Elementin etrafındaki çizgi.

```css
/* Kısa yazım */
border: 2px solid #000;

/* Ayrı özellikler */
border-width: 2px;
border-style: solid;  /* solid, dashed, dotted, double, groove, ridge, inset, outset, none */
border-color: #000;

/* Yönlere özel */
border-top: 2px solid red;
border-right: 3px dashed blue;
border-bottom: 1px dotted green;
border-left: 4px double orange;

/* Köşe yuvarlama */
border-radius: 5px;
border-radius: 10px 20px;  /* Üst-sol/alt-sağ ve üst-sağ/alt-sol */
border-radius: 10px 20px 30px 40px;  /* Tüm köşeler */
border-top-left-radius: 5px;
```

**💡 Kullanım:** Kartlar, butonlar, input'lar için.

### Outline (Dış Çizgi)
Focus durumunda görünen çizgi (border'dan farklı, yer kaplamaz).

```css
outline: 2px solid #000;
outline: none;           /* Focus çizgisini kaldır (erişilebilirlik için önerilmez) */
outline-offset: 2px;     /* Border'dan uzaklık */
```

**💡 Kullanım:** Focus durumları, erişilebilirlik.

---

## 🎬 TRANSITIONS & ANIMATIONS

### Transition (Geçiş)
Özellik değişikliklerini yumuşak geçiş yapar.

```css
/* Kısa yazım */
transition: property duration timing-function delay;
transition: all 0.3s ease;
transition: color 0.3s ease, transform 0.2s ease;

/* Ayrı özellikler */
transition-property: color;        /* Hangi özellik */
transition-duration: 0.3s;         /* Süre */
transition-timing-function: ease;   /* Hız eğrisi */
transition-delay: 0.1s;            /* Gecikme */

/* Timing Functions */
transition-timing-function: linear;      /* Sabit hız */
transition-timing-function: ease;        /* Yavaş başla, hızlan, yavaşla */
transition-timing-function: ease-in;     /* Yavaş başla */
transition-timing-function: ease-out;    /* Yavaş bitir */
transition-timing-function: ease-in-out; /* Yavaş başla ve bitir */
transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1); /* Özel eğri */
```

**💡 Kullanım Senaryoları:**
- Hover efektleri
- Renk değişimleri
- Transform animasyonları
- Opacity değişimleri

**💡 Pratik Örnek:**
```css
.button {
    background-color: blue;
    transition: background-color 0.3s ease, transform 0.2s ease;
}
.button:hover {
    background-color: darkblue;
    transform: translateY(-2px);
}
```

### Animation (Animasyon)
Keyframe'ler ile tanımlanan animasyonlar.

```css
/* Kısa yazım */
animation: name duration timing-function delay iteration-count direction fill-mode;
animation: slideIn 0.5s ease-in-out;

/* Ayrı özellikler */
animation-name: slideIn;
animation-duration: 0.5s;
animation-timing-function: ease;
animation-delay: 0.1s;
animation-iteration-count: 1;      /* 1, 2, 3, infinite */
animation-direction: normal;        /* normal, reverse, alternate, alternate-reverse */
animation-fill-mode: forwards;      /* none, forwards, backwards, both */
animation-play-state: running;     /* running, paused */

/* Keyframes */
@keyframes slideIn {
    from {
        transform: translateX(-100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

/* Yüzde ile */
@keyframes fadeIn {
    0% { opacity: 0; }
    50% { opacity: 0.5; }
    100% { opacity: 1; }
}
```

**💡 Kullanım Senaryoları:**
- Sayfa yüklenme animasyonları
- Loading spinner'lar
- Hover efektleri
- Scroll animasyonları

---

## 🔄 TRANSFORMS

Elementleri dönüştürür (yer kaplamaz, diğer elementler etkilenmez).

```css
/* Translate (Taşıma) */
transform: translateX(10px);      /* X ekseninde */
transform: translateY(10px);      /* Y ekseninde */
transform: translate(10px, 20px); /* X ve Y */

/* Rotate (Döndürme) */
transform: rotate(45deg);         /* 45 derece saat yönünde */
transform: rotate(-45deg);        /* 45 derece saat yönü tersine */

/* Scale (Ölçekleme) */
transform: scale(1.5);            /* %150 büyüt */
transform: scale(0.5);             /* %50 küçült */
transform: scaleX(1.5);           /* Sadece X ekseni */
transform: scaleY(1.5);           /* Sadece Y ekseni */
transform: scale(1.5, 0.8);       /* X ve Y farklı */

/* Skew (Eğme) */
transform: skew(10deg, 5deg);     /* X ve Y ekseninde eğme */
transform: skewX(10deg);
transform: skewY(5deg);

/* Matrix (Matris) */
transform: matrix(1, 0, 0, 1, 0, 0);

/* Birden fazla transform */
transform: translateX(10px) rotate(45deg) scale(1.2);

/* Transform origin (Dönüşüm merkezi) */
transform-origin: center;         /* Ortada */
transform-origin: top left;       /* Üst sol */
transform-origin: 50% 50%;        /* Yüzde */
transform-origin: 10px 20px;      /* Pixel */
```

**💡 Kullanım Senaryoları:**
- Hover efektleri (scale, translate)
- Loading animasyonları (rotate)
- Modal açılma (scale, translate)
- Kart flip efektleri

**💡 Pratik Örnek:**
```css
.card:hover {
    transform: translateY(-10px) scale(1.05);
    transition: transform 0.3s ease;
}
```

---

## 👁️ VISIBILITY & OPACITY

### Visibility
Elementin görünürlüğü (yer kaplar).

```css
visibility: visible;    /* Görünür (varsayılan) */
visibility: hidden;    /* Gizli ama yer kaplar */
visibility: collapse;  /* Tablo için (satır/hücre gizler) */
```

### Opacity
Elementin şeffaflığı.

```css
opacity: 1;      /* Tamamen opak (varsayılan) */
opacity: 0.5;    /* %50 şeffaf */
opacity: 0;      /* Tamamen şeffaf */
```

### Display None
Elementi gizler ve yer kaplamaz.

```css
display: none;   /* Gizli, yer kaplamaz */
```

**💡 Farklar:**
- `visibility: hidden` - Yer kaplar, tıklanamaz
- `opacity: 0` - Yer kaplar, tıklanabilir
- `display: none` - Yer kaplamaz, DOM'da yok gibi

---

## 📦 OVERFLOW

Taşan içeriğin nasıl gösterileceği.

```css
overflow: visible;    /* Taşan içerik gösterilir (varsayılan) */
overflow: hidden;     /* Taşan içerik gizlenir */
overflow: scroll;     /* Her zaman scroll bar */
overflow: auto;       /* Gerektiğinde scroll bar */

/* Yönlere özel */
overflow-x: hidden;   /* Yatay */
overflow-y: scroll;   /* Dikey */

/* Metin taşması */
overflow-wrap: break-word;  /* Uzun kelimeleri kır */
overflow-wrap: normal;      /* Varsayılan */
```

**💡 Kullanım Senaryoları:**
- `overflow: hidden` - Taşan içeriği gizleme
- `overflow: auto` - Scroll edilebilir alanlar
- `overflow-wrap: break-word` - Uzun URL'ler için

---

## 🖼️ OBJECT FIT & POSITION

Resim ve video elementlerinin nasıl sığdırılacağı.

```css
/* Object Fit */
object-fit: fill;        /* Doldurur, oran bozulabilir */
object-fit: contain;     /* Sığdırır, oran korunur, boşluk kalabilir */
object-fit: cover;       /* Kaplar, oran korunur, kırpılabilir (ÖNERİLEN) */
object-fit: none;        /* Orijinal boyut */
object-fit: scale-down;  /* contain veya none'dan küçük olan */

/* Object Position */
object-position: center;     /* Ortada */
object-position: top left;   /* Üst sol */
object-position: 50% 50%;    /* Yüzde */
```

**💡 Kullanım:** Responsive resimler, video player'lar, avatar'lar.

---

## 🎨 FILTERS

Görsel efektler uygular.

```css
filter: blur(5px);              /* Bulanıklaştırma */
filter: brightness(1.5);        /* Parlaklık (1 = normal, >1 = daha parlak) */
filter: contrast(1.5);          /* Kontrast */
filter: grayscale(100%);        /* Gri tonlama (0-100%) */
filter: hue-rotate(90deg);      /* Renk döndürme */
filter: invert(100%);           /* Ters çevirme */
filter: opacity(0.5);           /* Şeffaflık */
filter: saturate(200%);         /* Doygunluk */
filter: sepia(100%);            /* Sepia efekti */
filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.5)); /* Gölge */

/* Birden fazla filter */
filter: blur(5px) brightness(1.2) contrast(1.1);
```

**💡 Kullanım Senaryoları:**
- Hover efektleri
- Görsel efektler
- Loading durumları
- Overlay'ler

---

## 📐 CLIP & MASK

Elementin görünür kısmını belirler.

```css
/* Clip Path */
clip-path: circle(50%);                    /* Daire */
clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); /* Çokgen */
clip-path: inset(10px 20px);              /* İçeriden kırpma */

/* Mask */
mask: url('mask.svg');
mask-image: linear-gradient(black, transparent);
mask-size: cover;
mask-position: center;
```

**💡 Kullanım:** Şekilli görseller, geçiş efektleri.

---

## 🎯 PSEUDO CLASSES

Elementin durumuna göre stil uygular.

```css
/* Link durumları */
:link        /* Ziyaret edilmemiş link */
:visited     /* Ziyaret edilmiş link */
:hover       /* Fare üzerindeyken */
:active      /* Tıklanırken */
:focus       /* Odaklanmışken */

/* Yapısal */
:first-child     /* İlk çocuk */
:last-child      /* Son çocuk */
:nth-child(2)    /* 2. çocuk */
:nth-child(odd)  /* Tek sayılı çocuklar */
:nth-child(even) /* Çift sayılı çocuklar */
:nth-child(3n)   /* 3'ün katları */
:first-of-type   /* İlk tip */
:last-of-type    /* Son tip */
:nth-of-type(2)  /* 2. tip */

/* Durum */
:checked     /* Checkbox/radio seçili */
:disabled    /* Devre dışı */
:enabled     /* Aktif */
:required    /* Zorunlu alan */
:optional    /* Opsiyonel alan */
:valid       /* Geçerli */
:invalid     /* Geçersiz */

/* Diğer */
:not(.class)     /* Seçici değil */
:empty           /* Boş element */
:root            /* HTML root elementi */
```

**💡 Kullanım Senaryoları:**
- `:hover` - Buton, link efektleri
- `:focus` - Form input'ları
- `:nth-child()` - Zebra striping, özel seçimler
- `:checked` - Custom checkbox/radio

---

## 🎨 PSEUDO ELEMENTS

Elementin belirli kısımlarına stil uygular.

```css
/* ::before ve ::after */
.element::before {
    content: "";  /* ZORUNLU - içerik olmalı */
    /* Stil tanımları */
}

.element::after {
    content: "→";
    /* Stil tanımları */
}

/* Diğer */
::first-letter   /* İlk harf */
::first-line     /* İlk satır */
::selection      /* Seçili metin */
::placeholder    /* Input placeholder */
```

**💡 Kullanım Senaryoları:**
- Dekoratif öğeler
- İkonlar
- Tooltip'ler
- Özel list marker'ları

**💡 Pratik Örnek:**
```css
.link::after {
    content: " →";
    transition: transform 0.3s ease;
}
.link:hover::after {
    transform: translateX(5px);
}
```

---

## 📱 MEDIA QUERIES

Farklı ekran boyutları için farklı stiller.

```css
/* Genişlik */
@media (max-width: 768px) { }
@media (min-width: 769px) { }
@media (min-width: 769px) and (max-width: 1024px) { }

/* Yükseklik */
@media (min-height: 600px) { }

/* Yön */
@media (orientation: portrait) { }   /* Dikey */
@media (orientation: landscape) { }  /* Yatay */

/* Çözünürlük */
@media (min-resolution: 192dpi) { }
@media (min-resolution: 2dppx) { }

/* Print */
@media print { }

/* Dark Mode */
@media (prefers-color-scheme: dark) {
    body {
        background-color: #1a1a1a;
        color: #fff;
    }
}

/* Reduced Motion */
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

**💡 Yaygın Breakpoint'ler:**
```css
/* Mobile */
@media (max-width: 575.98px) { }

/* Tablet */
@media (min-width: 576px) and (max-width: 767.98px) { }

/* Desktop */
@media (min-width: 768px) and (max-width: 991.98px) { }

/* Large Desktop */
@media (min-width: 992px) and (max-width: 1199.98px) { }

/* Extra Large */
@media (min-width: 1200px) { }
```

---

## 🎨 CSS VARIABLES (Custom Properties)

Tekrar kullanılabilir değerler.

```css
/* Tanımlama */
:root {
    --primary-color: #0066cc;
    --spacing: 16px;
    --font-size-base: 1rem;
}

/* Kullanım */
.element {
    color: var(--primary-color);
    padding: var(--spacing);
    font-size: var(--font-size-base);
}

/* Fallback (Yedek değer) */
.element {
    color: var(--primary-color, #000);  /* --primary-color yoksa #000 kullan */
}

/* Kapsam (Scope) */
.container {
    --local-color: red;  /* Sadece .container içinde geçerli */
}
```

**💡 Kullanım Senaryoları:**
- Tema renkleri
- Spacing sistemi
- Font boyutları
- Dark mode

**💡 Best Practice:**
```css
:root {
    --primary: #0066cc;
    --secondary: #ff6600;
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 1.5rem;
}
```

---

## 📊 UNITS (Birimler)

### Absolute (Mutlak) Birimler
```css
px  /* Pixel - En yaygın */
pt  /* Point - Baskı için */
pc  /* Pica - Baskı için */
in  /* İnç - Baskı için */
cm  /* Santimetre - Baskı için */
mm  /* Milimetre - Baskı için */
```

### Relative (Göreceli) Birimler
```css
em   /* Parent font size'a göre */
rem  /* Root font size'a göre (ÖNERİLEN) */
%    /* Parent özelliğine göre */
vw   /* Viewport width - %1 */
vh   /* Viewport height - %1 */
vmin /* Viewport min (width veya height) */
vmax /* Viewport max (width veya height) */
ch   /* "0" karakter genişliği */
ex   /* Font x yüksekliği */
```

**💡 Kullanım Önerileri:**
- `rem` - Font boyutları, spacing (ÖNERİLEN)
- `%` - Genişlik, yükseklik
- `vw/vh` - Fullscreen bölümler
- `px` - Border, shadow, küçük değerler

---

## 🎯 SELECTORS (Seçiciler)

```css
/* Element */
div { }

/* Class */
.class { }

/* ID */
#id { }

/* Attribute */
[type="text"] { }           /* Tam eşleşme */
[href^="https"] { }         /* Başlangıç */
[href$=".pdf"] { }          /* Bitiş */
[href*="example"] { }       /* İçerik */
[class~="active"] { }       /* Kelime içerik */

/* Descendant (Torun) */
div p { }                   /* div içindeki tüm p */

/* Child (Çocuk) */
div > p { }                 /* div'in doğrudan çocuğu p */

/* Adjacent Sibling (Bitişik Kardeş) */
div + p { }                 /* div'den hemen sonraki p */

/* General Sibling (Genel Kardeş) */
div ~ p { }                 /* div'den sonraki tüm p */

/* Multiple (Çoklu) */
div, p, .class { }          /* Hepsi */

/* Not */
:not(.class) { }            /* .class olmayan */
:not(div) { }               /* div olmayan */
```

**💡 Specificity (Öncelik) Sırası:**
1. Inline styles (`style="..."`)
2. ID seçiciler (`#id`)
3. Class, Attribute, Pseudo class (`.class`, `[attr]`, `:hover`)
4. Element, Pseudo element (`div`, `::before`)

---

## 🎨 GRADIENTS (Gradyanlar)

### Linear Gradient (Doğrusal)
```css
/* Yön ile */
background: linear-gradient(to right, red, blue);
background: linear-gradient(to bottom, red, blue);
background: linear-gradient(to top right, red, blue);

/* Açı ile */
background: linear-gradient(45deg, red, blue);
background: linear-gradient(90deg, red, blue);

/* Çoklu renk */
background: linear-gradient(red, yellow, blue);
background: linear-gradient(red 0%, yellow 50%, blue 100%);
```

### Radial Gradient (Dairesel)
```css
background: radial-gradient(circle, red, blue);
background: radial-gradient(ellipse at center, red, blue);
background: radial-gradient(circle at top left, red, blue);
```

### Repeating Gradient (Tekrarlayan)
```css
background: repeating-linear-gradient(45deg, red, red 10px, blue 10px, blue 20px);
background: repeating-radial-gradient(circle, red, red 10px, blue 10px, blue 20px);
```

**💡 Kullanım:** Arka planlar, butonlar, dekoratif öğeler.

---

## 📦 SHADOWS (Gölgeler)

### Box Shadow
```css
/* Temel */
box-shadow: 2px 2px 4px rgba(0,0,0,0.5);
/* x-offset y-offset blur-radius color */

/* İç gölge */
box-shadow: inset 2px 2px 4px rgba(0,0,0,0.5);

/* Çoklu gölge */
box-shadow: 
    0 2px 4px rgba(0,0,0,0.1),
    0 4px 8px rgba(0,0,0,0.1);

/* Spread radius ile */
box-shadow: 0 0 0 5px rgba(0,0,0,0.2);
/* x-offset y-offset blur-radius spread-radius color */
```

### Text Shadow
```css
text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
/* x-offset y-offset blur-radius color */

/* Çoklu gölge */
text-shadow: 
    0 2px 4px rgba(0,0,0,0.1),
    0 4px 8px rgba(0,0,0,0.1);
```

**💡 Kullanım:** Derinlik hissi, vurgulama, modern görünüm.

---

## 🎯 COMMON PATTERNS (Yaygın Desenler)

```css
/* Ortalanmış Element */
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

/* Tam Genişlik */
.full-width {
    width: 100%;
}

/* Clearfix (Float temizleme) */
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}

/* Metin Kırpma (Truncate) */
.truncate {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

/* Responsive Resim */
img {
    max-width: 100%;
    height: auto;
}

/* Smooth Scroll */
html {
    scroll-behavior: smooth;
}

/* Yatay Ortalama */
.center-horizontal {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

/* Dikey Ortalama */
.center-vertical {
    display: flex;
    align-items: center;
    height: 100vh;
}

/* Aspect Ratio (En-Boy Oranı) */
.aspect-ratio {
    aspect-ratio: 16 / 9;
    width: 100%;
}
```

---

## 📱 COMMON BREAKPOINTS (Yaygın Kırılma Noktaları)

```css
/* Mobile First Yaklaşımı (ÖNERİLEN) */
/* Mobil */
@media (max-width: 575.98px) {
    /* Mobil stilleri */
}

/* Tablet */
@media (min-width: 576px) {
    /* Tablet ve üzeri */
}

/* Desktop */
@media (min-width: 768px) {
    /* Desktop ve üzeri */
}

/* Large Desktop */
@media (min-width: 992px) {
    /* Büyük ekranlar */
}

/* Extra Large */
@media (min-width: 1200px) {
    /* Çok büyük ekranlar */
}
```

**💡 Mobile-First Best Practice:**
```css
/* Önce mobil için yaz */
.container {
    width: 100%;
    padding: 10px;
}

/* Sonra büyük ekranlar için genişlet */
@media (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
        padding: 20px;
    }
}
```

---

## 🎯 COMMON VALUES (Yaygın Değerler)

```css
/* Auto - Otomatik hesaplama */
width: auto;
margin: auto;  /* Ortalama için */

/* Inherit - Parent'tan al */
color: inherit;
font-size: inherit;

/* Initial - Varsayılan değer */
display: initial;

/* Unset - Inherit veya initial */
margin: unset;

/* None - Yok */
display: none;
border: none;
list-style: none;
```

---

## 💡 BEST PRACTICES (En İyi Uygulamalar)

### 1. CSS Reset
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

### 2. CSS Variables Kullanımı
```css
:root {
    --primary: #0066cc;
    --spacing: 1rem;
}
```

### 3. Mobile-First Yaklaşımı
```css
/* Önce mobil, sonra desktop */
```

### 4. Semantic Class İsimleri
```css
/* İyi */
.button-primary { }
.card-header { }

/* Kötü */
.red-button { }
.big-box { }
```

### 5. BEM Metodolojisi
```css
.block { }
.block__element { }
.block--modifier { }
```

---

**💡 İpucu:** Bu cheat sheet'i sık kullandığınız yerde saklayın ve hızlı referans için kullanın!

**📚 Daha fazla bilgi için:** Proje içindeki detaylı dokümantasyon dosyalarına bakın.

# 🎨 CSS ARKA PLAN ÖZELLİKLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) arka plan özellikleri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin arka plan görünümünü kontrol etmek için kullanılır.

## 🎨 `background-color`

Elementin arka plan rengini belirler.

```css
div {
    background-color: red;
    background-color: #FF0000;
    background-color: rgb(255, 0, 0);
    background-color: rgba(255, 0, 0, 0.5);
    background-color: transparent;  /* Şeffaf */
}
```

## 🖼️ `background-image`

Elementin arka plan resmini belirler.

```css
div {
    background-image: url("resim.jpg");
    background-image: url("../images/logo.png");
    background-image: linear-gradient(to bottom, blue, red);
    background-image: none;  /* Resim yok */
}
```

## 🔄 `background-repeat`

Arka plan resminin nasıl tekrarlanacağını belirler.

```css
div {
    background-repeat: repeat;        /* Varsayılan - Her iki yönde tekrarlanır */
    background-repeat: repeat-x;      /* Sadece yatay */
    background-repeat: repeat-y;      /* Sadece dikey */
    background-repeat: no-repeat;     /* Tekrarlanmaz */
    background-repeat: space;         /* Boşluk bırakarak tekrarlanır */
    background-repeat: round;         /* Yuvarlanarak tekrarlanır */
}
```

## 📍 `background-position`

Arka plan resminin konumunu belirler.

```css
div {
    background-position: top left;
    background-position: center center;
    background-position: bottom right;
    background-position: 50% 50%;
    background-position: 20px 30px;
    background-position: left top, right bottom;  /* Çoklu resim */
}
```

### Pozisyon Değerleri

- **Yatay**: `left`, `center`, `right`, yüzde veya pixel değeri
- **Dikey**: `top`, `center`, `bottom`, yüzde veya pixel değeri

## 📏 `background-size`

Arka plan resminin boyutunu belirler.

```css
div {
    background-size: auto;           /* Orijinal boyut */
    background-size: cover;           /* Kaplar, oran korunur */
    background-size: contain;         /* Sığdırır, oran korunur */
    background-size: 100% 100%;      /* Genişlik ve yükseklik */
    background-size: 200px 150px;    /* Sabit boyut */
    background-size: 50% auto;        /* Genişlik yüzde, yükseklik otomatik */
}
```

## 📌 `background-attachment`

Arka plan resminin kaydırma davranışını belirler.

```css
div {
    background-attachment: scroll;    /* Varsayılan - Kaydırma ile birlikte hareket eder */
    background-attachment: fixed;    /* Sabit - Kaydırmada sabit kalır */
    background-attachment: local;     /* Element içeriği ile birlikte hareket eder */
}
```

## 🎨 `background` (Kısa Yazım)

Tüm arka plan özelliklerini tek satırda tanımlar.

```css
div {
    background: #ffffff url("resim.jpg") no-repeat center center / cover fixed;
    /* color image repeat position / size attachment */
}
```

## 🌈 Gradient Arka Planlar

### Linear Gradient (Doğrusal Gradyan)

```css
div {
    background: linear-gradient(to right, blue, red);
    background: linear-gradient(45deg, blue, red);
    background: linear-gradient(to bottom, blue, green, red);
    background: linear-gradient(to right, rgba(0,0,255,0.5), rgba(255,0,0,0.5));
}
```

### Radial Gradient (Dairesel Gradyan)

```css
div {
    background: radial-gradient(circle, blue, red);
    background: radial-gradient(ellipse at center, blue, red);
    background: radial-gradient(circle at top left, blue, red);
}
```

### Conic Gradient (Koni Gradyan)

```css
div {
    background: conic-gradient(blue, red, green);
    background: conic-gradient(from 45deg, blue, red);
    background: conic-gradient(blue 0deg, red 90deg, green 180deg);
}
```

## 🎭 Çoklu Arka Plan Resimleri

Birden fazla arka plan resmi kullanılabilir.

```css
div {
    background-image: 
        url("resim1.jpg"),
        url("resim2.png"),
        linear-gradient(to bottom, blue, red);
    background-position: 
        top left,
        bottom right,
        center;
    background-repeat: 
        no-repeat,
        repeat,
        no-repeat;
    background-size: 
        200px 150px,
        100% 100%,
        cover;
}
```

## 💡 Pratik Örnekler

### Tam Ekran Arka Plan

```css
.hero {
    background-image: url("hero.jpg");
    background-size: cover;
    background-position: center center;
    background-repeat: no-repeat;
    background-attachment: fixed;
    height: 100vh;
}
```

### Pattern Arka Plan

```css
.pattern {
    background-image: url("pattern.png");
    background-repeat: repeat;
    background-size: 50px 50px;
}
```

### Gradient Arka Plan

```css
.gradient {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    height: 100vh;
}
```

### Overlay Arka Plan

```css
.overlay {
    background-image: 
        linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
        url("resim.jpg");
    background-size: cover;
    background-position: center;
}
```

### Parallax Efekti

```css
.parallax {
    background-image: url("resim.jpg");
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: 500px;
}
```

## ⚠️ Önemli Notlar

1. **Performans**: Büyük arka plan resimleri sayfa yükleme süresini artırabilir.

2. **Responsive**: `background-size: cover` ve `contain` responsive tasarım için idealdir.

3. **Erişilebilirlik**: Arka plan resimlerinin üzerindeki metinlerin okunabilirliğini kontrol edin.

4. **Fallback**: Arka plan resmi yüklenemezse, `background-color` kullanılmalıdır.

5. **CSS Variables**: Arka plan renkleri için CSS değişkenleri kullanılabilir:

```css
:root {
    --primary-color: #0066cc;
    --secondary-color: #ff6600;
}

div {
    background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


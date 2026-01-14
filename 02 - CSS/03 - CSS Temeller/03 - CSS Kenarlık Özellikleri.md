# 🔲 CSS KENARLIK ÖZELLİKLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) kenarlık özellikleri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin kenarlıklarını kontrol etmek için kullanılır.

## 📏 `border-width`

Kenarlık kalınlığını belirler.

```css
div {
    border-width: 1px;
    border-width: thin;      /* 1px */
    border-width: medium;     /* 3px */
    border-width: thick;      /* 5px */
    border-width: 2px 4px;    /* üst-alt sol-sağ */
    border-width: 1px 2px 3px 4px;  /* üst sağ alt sol */
}

/* Yönlere özel */
div {
    border-top-width: 2px;
    border-right-width: 3px;
    border-bottom-width: 1px;
    border-left-width: 4px;
}
```

## 🎨 `border-style`

Kenarlık stilini belirler.

```css
div {
    border-style: solid;      /* Düz çizgi */
    border-style: dashed;     /* Kesikli çizgi */
    border-style: dotted;     /* Noktalı çizgi */
    border-style: double;     /* Çift çizgi */
    border-style: groove;      /* 3D oyuk */
    border-style: ridge;       /* 3D kabartma */
    border-style: inset;       /* 3D içe gömülü */
    border-style: outset;      /* 3D dışa çıkık */
    border-style: none;        /* Kenarlık yok */
    border-style: hidden;      /* Gizli */
}

/* Yönlere özel */
div {
    border-top-style: solid;
    border-right-style: dashed;
    border-bottom-style: dotted;
    border-left-style: double;
}
```

## 🌈 `border-color`

Kenarlık rengini belirler.

```css
div {
    border-color: red;
    border-color: #FF0000;
    border-color: rgb(255, 0, 0);
    border-color: rgba(255, 0, 0, 0.5);
    border-color: red blue;    /* üst-alt sol-sağ */
    border-color: red blue green yellow;  /* üst sağ alt sol */
}

/* Yönlere özel */
div {
    border-top-color: red;
    border-right-color: blue;
    border-bottom-color: green;
    border-left-color: yellow;
}
```

## 🎯 `border` (Kısa Yazım)

Tüm kenarlık özelliklerini tek satırda tanımlar.

```css
div {
    border: 2px solid red;
    /* width style color */
}

/* Yönlere özel */
div {
    border-top: 2px solid red;
    border-right: 3px dashed blue;
    border-bottom: 1px dotted green;
    border-left: 4px double yellow;
}
```

## 🔄 `border-radius`

Kenarlık köşelerini yuvarlar.

```css
div {
    border-radius: 10px;
    border-radius: 50%;        /* Daire */
    border-radius: 10px 20px; /* üst-sol-alt-sağ üst-sağ-alt-sol */
    border-radius: 10px 20px 30px 40px;  /* üst-sol üst-sağ alt-sağ alt-sol */
}

/* Yönlere özel */
div {
    border-top-left-radius: 10px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 30px;
    border-bottom-left-radius: 40px;
}

/* Elips şekli */
div {
    border-radius: 50px / 25px;  /* yatay / dikey */
}
```

## 🖼️ `border-image`

Kenarlık için resim kullanır.

```css
div {
    border-image: url("border.png") 30 round;
    /* source slice repeat */
    
    border-image: url("border.png") 30 stretch;
    border-image: url("border.png") 30 30 30 30 round;
}

/* Ayrı özellikler */
div {
    border-image-source: url("border.png");
    border-image-slice: 30;
    border-image-width: 10px;
    border-image-outset: 5px;
    border-image-repeat: round;
}
```

## 📐 `border-collapse`

Tablo hücrelerinin kenarlıklarının nasıl birleşeceğini belirler.

```css
table {
    border-collapse: separate;  /* Varsayılan - Ayrı */
    border-collapse: collapse;  /* Birleşik */
}
```

## 🎨 Kenarlık Gölgesi

### `box-shadow`

Elemente gölge efekti ekler (kenarlık ile ilgili).

```css
div {
    box-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    /* x-offset y-offset blur-radius color */
    
    box-shadow: 2px 2px 4px rgba(0,0,0,0.3),
                0 0 10px rgba(255,0,0,0.5);  /* Çoklu gölge */
    
    box-shadow: inset 2px 2px 4px rgba(0,0,0,0.3);  /* İç gölge */
}
```

## 💡 Pratik Örnekler

### Basit Kenarlık

```css
.box {
    border: 1px solid #ccc;
    padding: 20px;
}
```

### Yuvarlatılmış Köşeler

```css
.card {
    border: 2px solid #333;
    border-radius: 10px;
    padding: 20px;
}
```

### Daire Şekli

```css
.circle {
    width: 100px;
    height: 100px;
    border: 3px solid blue;
    border-radius: 50%;
}
```

### Farklı Kenarlıklar

```css
.mixed-border {
    border-top: 2px solid red;
    border-right: 3px dashed blue;
    border-bottom: 1px dotted green;
    border-left: 4px double yellow;
}
```

### Gölgeli Kenarlık

```css
.shadow-border {
    border: 1px solid #ccc;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

### Hover Efekti

```css
.button {
    border: 2px solid blue;
    transition: border-color 0.3s;
}

.button:hover {
    border-color: red;
    border-width: 3px;
}
```

### Gradient Kenarlık (Hack)

```css
.gradient-border {
    border: 2px solid transparent;
    background: 
        linear-gradient(white, white) padding-box,
        linear-gradient(to right, blue, red) border-box;
}
```

## ⚠️ Önemli Notlar

1. **Box Model**: Kenarlık, kutu modelinin bir parçasıdır ve elementin toplam boyutuna eklenir (varsayılan olarak).

2. **Transparent**: `border-color: transparent` kullanarak görünmez kenarlık oluşturulabilir.

3. **Border vs Outline**: `outline` özelliği kenarlıktan farklıdır ve kutu modeline dahil değildir.

4. **Performans**: `border-radius` ve `box-shadow` performansı etkileyebilir, özellikle animasyonlarda.

5. **Erişilebilirlik**: Kenarlık renkleri, yeterli kontrast sağlamalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


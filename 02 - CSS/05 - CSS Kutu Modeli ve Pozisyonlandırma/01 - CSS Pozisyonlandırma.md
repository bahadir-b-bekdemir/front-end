# 📍 CSS POZİSYONLANDIRMA

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) `position` özelliği, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin sayfa içindeki konumunu belirler.

## 📋 Position Türleri

CSS'de beş farklı position değeri vardır:

1. `static` - Varsayılan
2. `relative` - Göreceli
3. `absolute` - Mutlak
4. `fixed` - Sabit
5. `sticky` - Yapışkan

## 📄 `static` (Varsayılan)

Element normal akışta konumlanır. `top`, `right`, `bottom`, `left` ve `z-index` özellikleri etkisizdir.

```css
.element {
    position: static;
}
```

## 🔄 `relative` (Göreceli)

Element normal akışta konumlanır, ancak `top`, `right`, `bottom`, `left` özellikleri ile kendi konumundan kaydırılabilir.

```css
.element {
    position: relative;
    top: 20px;
    left: 30px;
}
```

### Özellikler

- Normal akışta kalır
- Diğer elementler etkilenmez
- Kendi konumundan kaydırılır
- `z-index` kullanılabilir

### 💡 Örnek

```css
.box {
    position: relative;
    top: 10px;
    left: 20px;
    background-color: blue;
}
```

## 🎯 `absolute` (Mutlak)

Element normal akıştan çıkar ve en yakın positioned (relative, absolute, fixed, sticky) parent elementine göre konumlanır.

```css
.element {
    position: absolute;
    top: 0;
    right: 0;
}
```

### Özellikler

- Normal akıştan çıkar
- En yakın positioned parent'a göre konumlanır
- Parent yoksa `<body>`'ye göre konumlanır
- Diğer elementler tarafından görmezden gelinir

### 💡 Örnek

```css
.container {
    position: relative;  /* Parent positioned olmalı */
}

.box {
    position: absolute;
    top: 10px;
    right: 20px;
}
```

## 📌 `fixed` (Sabit)

Element viewport'a göre konumlanır ve sayfa kaydırıldığında sabit kalır.

```css
.element {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
}
```

### Özellikler

- Viewport'a göre konumlanır
- Sayfa kaydırıldığında sabit kalır
- Normal akıştan çıkar
- Diğer elementler tarafından görmezden gelinir

### 💡 Örnekler

```css
/* Sabit header */
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
}

/* Sabit footer */
.footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
}

/* Sabit sidebar */
.sidebar {
    position: fixed;
    top: 0;
    right: 0;
    width: 250px;
    height: 100vh;
}
```

## 🧲 `sticky` (Yapışkan)

Element normal akışta kalır, ancak belirli bir scroll pozisyonuna ulaştığında `fixed` gibi davranır.

```css
.element {
    position: sticky;
    top: 0;
}
```

### Özellikler

- Normal akışta başlar
- Scroll ile belirli pozisyona ulaştığında sabitlenir
- Parent container içinde kalır
- Modern tarayıcılarda desteklenir

### 💡 Örnek

```css
.sticky-header {
    position: sticky;
    top: 0;
    background-color: white;
    z-index: 100;
}

/* Tablo başlıkları için */
th {
    position: sticky;
    top: 0;
    background-color: #f0f0f0;
}
```

## 📐 Konum Özellikleri

Position ile birlikte kullanılan özellikler:

### `top`, `right`, `bottom`, `left`

Elementin konumunu belirler.

```css
.element {
    position: absolute;
    top: 10px;
    right: 20px;
    bottom: 30px;
    left: 40px;
}
```

### `z-index`

Elementlerin üst üste gelme sırasını belirler. Sadece positioned elementler için çalışır.

```css
.element1 {
    position: relative;
    z-index: 1;
}

.element2 {
    position: relative;
    z-index: 2;  /* element1'in üstünde */
}
```

## 💡 Pratik Örnekler

### Overlay (Kaplama)

```css
.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1000;
}
```

### Modal (Pencere)

```css
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2000;
    background-color: white;
    padding: 20px;
}
```

### Tooltip (İpucu)

```css
.tooltip {
    position: absolute;
    bottom: 100%;
    left: 50%;
    transform: translateX(-50%);
    background-color: black;
    color: white;
    padding: 5px 10px;
    white-space: nowrap;
}
```

### Sticky Navigation

```css
.nav {
    position: sticky;
    top: 0;
    background-color: white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    z-index: 100;
}
```

### Centered Element

```css
.center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

## ⚠️ Önemli Notlar

1. **Positioned Parent**: `absolute` ve `fixed` elementler, en yakın positioned parent'a göre konumlanır.

2. **Z-Index**: Sadece positioned elementler için çalışır (`static` hariç).

3. **Overflow**: Parent'ta `overflow: hidden` varsa, `fixed` element görünmeyebilir.

4. **Performance**: `fixed` ve `sticky` elementler performansı etkileyebilir.

5. **Mobile**: `fixed` elementler mobil cihazlarda sorun yaratabilir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


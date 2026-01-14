# 🎭 CSS DISPLAY ÖZELLİĞİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) `display` özelliği, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin nasıl görüntüleneceğini ve diğer elementlerle nasıl etkileşime gireceğini belirler.

## 📋 Display Türleri

CSS'de birçok display değeri vardır:

1. **Block** - Blok seviyesi
2. **Inline** - Satır içi
3. **Inline-Block** - Satır içi blok
4. **Flex** - Esnek kutu
5. **Grid** - Izgara
6. **None** - Gizli
7. **Table** - Tablo
8. **Inline-Flex** - Satır içi esnek
9. **Inline-Grid** - Satır içi izgara

## 📦 `block` (Blok Seviyesi)

Element blok seviyesinde görüntülenir. Tam genişlik alır ve yeni satırdan başlar.

```css
div {
    display: block;
}
```

### Özellikler

- Tam genişlik alır
- Yeni satırdan başlar
- Yükseklik, genişlik, margin, padding ayarlanabilir
- Varsayılan: `<div>`, `<p>`, `<h1>-<h6>`, `<section>`, vb.

### 💡 Örnek

```css
.block-element {
    display: block;
    width: 100%;
    height: 50px;
    margin: 10px 0;
    padding: 20px;
}
```

## 📝 `inline` (Satır İçi)

Element satır içinde görüntülenir. Sadece içeriği kadar yer kaplar.

```css
span {
    display: inline;
}
```

### Özellikler

- Sadece içeriği kadar yer kaplar
- Yeni satırdan başlamaz
- Yükseklik ve genişlik ayarlanamaz
- Üst-alt margin çalışmaz
- Varsayılan: `<span>`, `<a>`, `<strong>`, `<em>`, vb.

### 💡 Örnek

```css
.inline-element {
    display: inline;
    /* width ve height çalışmaz */
    /* margin-top ve margin-bottom çalışmaz */
    padding: 5px;
    background-color: yellow;
}
```

## 🔲 `inline-block` (Satır İçi Blok)

Element hem inline hem de block özelliklerine sahiptir.

```css
.element {
    display: inline-block;
}
```

### Özellikler

- Satır içinde kalır
- Yükseklik ve genişlik ayarlanabilir
- Margin ve padding çalışır
- Yatay hizalama için idealdir

### 💡 Örnek

```css
.button {
    display: inline-block;
    width: 150px;
    height: 40px;
    padding: 10px 20px;
    margin: 5px;
    text-align: center;
}
```

## 🎯 `flex` (Esnek Kutu)

Element flex container olur. Flexbox düzeni için kullanılır.

```css
.container {
    display: flex;
}
```

### Özellikler

- Flex container oluşturur
- Çocuk elementler flex item olur
- Esnek düzen sağlar
- Modern layout için idealdir

### 💡 Örnek

```css
.flex-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

## 📐 `grid` (Izgara)

Element grid container olur. CSS Grid düzeni için kullanılır.

```css
.container {
    display: grid;
}
```

### Özellikler

- Grid container oluşturur
- Çocuk elementler grid item olur
- İki boyutlu düzen sağlar
- Karmaşık layoutlar için idealdir

### 💡 Örnek

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

## 🚫 `none` (Gizli)

Element tamamen gizlenir ve sayfa akışından çıkar.

```css
.hidden {
    display: none;
}
```

### Özellikler

- Element görünmez
- Sayfa akışından çıkar
- Yer kaplamaz
- `visibility: hidden`'dan farklıdır

### 💡 Örnek

```css
.mobile-menu {
    display: none;
}

@media (max-width: 768px) {
    .mobile-menu {
        display: block;
    }
}
```

## 📊 `table` (Tablo)

Element tablo gibi davranır.

```css
.element {
    display: table;
}
```

### İlgili Değerler

- `table` - Tablo
- `table-row` - Satır
- `table-cell` - Hücre
- `table-header-group` - Başlık grubu
- `table-footer-group` - Alt bilgi grubu

### 💡 Örnek

```css
.table {
    display: table;
    width: 100%;
}

.table-row {
    display: table-row;
}

.table-cell {
    display: table-cell;
    padding: 10px;
    border: 1px solid #ccc;
}
```

## 🔄 `inline-flex` ve `inline-grid`

Flex ve Grid'in inline versiyonları.

```css
.inline-flex {
    display: inline-flex;
}

.inline-grid {
    display: inline-grid;
}
```

### Özellikler

- Satır içinde kalır
- Flex/Grid özelliklerini korur
- Yatay hizalama için idealdir

## 📊 Display Değerleri Karşılaştırması

| Display | Genişlik | Yükseklik | Margin | Padding | Yeni Satır |
|---------|----------|-----------|--------|---------|------------|
| `block` | ✅ Tam | ✅ | ✅ Tümü | ✅ | ✅ |
| `inline` | ❌ İçerik | ❌ İçerik | ⚠️ Yatay | ✅ | ❌ |
| `inline-block` | ✅ | ✅ | ✅ Tümü | ✅ | ❌ |
| `flex` | ✅ | ✅ | ✅ Tümü | ✅ | ✅ |
| `grid` | ✅ | ✅ | ✅ Tümü | ✅ | ✅ |
| `none` | - | - | - | - | - |

## 💡 Pratik Örnekler

### Yatay Menü

```css
.menu {
    display: flex;
    list-style: none;
    gap: 20px;
}

.menu li {
    display: inline-block;
}
```

### Kart Düzeni

```css
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
}
```

### Responsive Gizleme

```css
.desktop-only {
    display: block;
}

.mobile-only {
    display: none;
}

@media (max-width: 768px) {
    .desktop-only {
        display: none;
    }
    
    .mobile-only {
        display: block;
    }
}
```

### Ortalanmış İçerik

```css
.center {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

## ⚠️ Önemli Notlar

1. **Display Değişikliği**: Display değeri değiştirildiğinde, elementin tüm davranışı değişir.

2. **Varsayılan Değerler**: Her HTML elementi varsayılan bir display değerine sahiptir.

3. **Override**: Display değeri, elementin varsayılan davranışını geçersiz kılar.

4. **Performance**: `display: none` kullanımı, `visibility: hidden`'dan daha performanslıdır.

5. **Accessibility**: Screen reader'lar `display: none` elementleri okumaz.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


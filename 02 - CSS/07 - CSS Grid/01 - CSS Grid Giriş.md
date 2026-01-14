# 🎯 CSS GRID GİRİŞ

CSS Grid (Izgara Düzeni), HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerini iki boyutlu (satır ve sütun) bir düzende düzenlemek için kullanılan güçlü bir CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) layout sistemidir.

## 📋 Grid Nedir?

Grid, bir container içindeki öğeleri satır ve sütunlara yerleştiren iki boyutlu bir düzen sistemidir. Flexbox'tan farklı olarak, hem satır hem de sütun ekseninde kontrol sağlar.

## 🏗️ Grid Yapısı

Grid iki ana bileşenden oluşur:

1. **Grid Container** - Ana container (parent element)
2. **Grid Items** - Container içindeki öğeler (child elements)

```css
.container {
    display: grid;  /* Grid container */
}

.item {
    /* Grid item */
}
```

## 📐 Grid Eksenleri

Grid iki eksen üzerinde çalışır:

1. **Block Axis (Blok Ekseni)** - Dikey eksen (satırlar)
2. **Inline Axis (Satır İçi Ekseni)** - Yatay eksen (sütunlar)

## 🎯 Temel Kullanım

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);  /* 3 eşit sütun */
    grid-template-rows: auto;  /* Otomatik satır yüksekliği */
    gap: 20px;  /* Öğeler arası boşluk */
}
```

## 💡 Avantajlar

1. **İki Boyutlu Düzen** - Hem satır hem sütun kontrolü
2. **Esnek Düzen** - Öğeler kolayca yerleştirilir
3. **Responsive** - Responsive tasarım için idealdir
4. **Karmaşık Düzenler** - Karmaşık layoutlar için mükemmel
5. **Overlap** - Öğeler üst üste gelebilir

## 🔄 Grid vs Flexbox

| Özellik | Grid | Flexbox |
|---------|------|---------|
| **Boyut** | İki boyutlu | Tek boyutlu |
| **Kullanım** | Sayfa düzeni | Component düzeni |
| **Eksen** | Satır + Sütun | Tek eksen |
| **Overlap** | ✅ Evet | ❌ Hayır |

## 💡 Ne Zaman Kullanılmalı?

### Grid Kullan

- Sayfa düzeni
- İki boyutlu düzenler
- Karmaşık layoutlar
- Öğelerin üst üste gelmesi

### Flexbox Kullan

- Component düzeni
- Tek boyutlu düzenler
- İçerik hizalaması
- Navigation menüleri

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


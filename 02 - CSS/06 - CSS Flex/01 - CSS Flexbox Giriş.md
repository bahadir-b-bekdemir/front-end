# 🎯 CSS FLEXBOX GİRİŞ

CSS Flexbox (Flexible Box Layout), HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerini esnek bir şekilde düzenlemek için kullanılan modern bir CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) layout sistemidir.

## 📋 Flexbox Nedir?

Flexbox, bir boyutlu (tek eksenli) düzen sistemi olup, container içindeki item'ları esnek bir şekilde hizalamak, dağıtmak ve boyutlandırmak için kullanılır.

## 🏗️ Flexbox Yapısı

Flexbox iki ana bileşenden oluşur:

1. **Flex Container** - Ana container (parent element)
2. **Flex Items** - Container içindeki öğeler (child elements)

```css
.container {
    display: flex;  /* Flex container */
}

.item {
    /* Flex item */
}
```

## 📐 Flexbox Eksenleri

Flexbox iki eksen üzerinde çalışır:

1. **Main Axis (Ana Eksen)** - `flex-direction` ile belirlenir
2. **Cross Axis (Çapraz Eksen)** - Ana eksene dik eksen

### Ana Eksen Yönleri

- **Row (Satır)** - Varsayılan, soldan sağa
- **Row-Reverse** - Sağdan sola
- **Column (Sütun)** - Yukarıdan aşağıya
- **Column-Reverse** - Aşağıdan yukarıya

## 🎯 Temel Kullanım

```css
.flex-container {
    display: flex;
    flex-direction: row;  /* Varsayılan */
    justify-content: flex-start;  /* Ana eksende hizalama */
    align-items: stretch;  /* Çapraz eksende hizalama */
    flex-wrap: nowrap;  /* Sarmalama */
    gap: 20px;  /* Öğeler arası boşluk */
}
```

## 💡 Avantajlar

1. **Esnek Düzen** - Öğeler otomatik olarak esner
2. **Kolay Hizalama** - Öğeler kolayca hizalanır
3. **Responsive** - Responsive tasarım için idealdir
4. **Tek Eksenli** - Tek boyutlu düzenler için mükemmel
5. **Modern Tarayıcı Desteği** - Tüm modern tarayıcılarda desteklenir

## ⚠️ Sınırlamalar

1. **Tek Boyutlu** - İki boyutlu düzenler için Grid daha uygundur
2. **Karmaşık Düzenler** - Çok karmaşık düzenler için Grid tercih edilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


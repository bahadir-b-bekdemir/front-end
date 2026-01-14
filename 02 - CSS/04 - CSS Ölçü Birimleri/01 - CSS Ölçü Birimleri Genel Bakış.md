# 📏 CSS ÖLÇÜ BİRİMLERİ GENEL BAKIŞ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) ölçü birimleri, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerinin boyutlarını, konumlarını ve aralıklarını belirlemek için kullanılır.

## 📊 Birim Kategorileri

CSS ölçü birimleri iki ana kategoriye ayrılır:

1. **Absolute (Mutlak) Birimler** - Sabit değerlere sahip birimler
2. **Relative (Göreceli) Birimler** - Başka bir değere göre hesaplanan birimler

## 🔢 Sayı Türleri

CSS ölçü birimlerinde kullanılan sayılar:

- **Tam sayılar**: `10`, `20`, `100`
- **Ondalıklı sayılar**: `10.5`, `20.75`, `0.5`
- **Yüzdeler**: `50%`, `100%`, `25%`
- **Negatif değerler**: `-10px`, `-50%` (bazı özellikler için)

## 📐 Birim Kullanım Kuralları

1. Sayı ile birim arasında **boşluk olmamalıdır**
2. Sıfır değeri için birim **opsiyoneldir**: `0` veya `0px` aynıdır
3. Bazı özellikler için **negatif değerler** kullanılabilir

### ✅ Doğru Kullanım

```css
div {
    width: 100px;
    height: 50%;
    margin: 10px 20px;
    padding: 0;
}
```

### ❌ Yanlış Kullanım

```css
div {
    width: 100 px;  /* Boşluk yanlış */
    height: 50 %;   /* Boşluk yanlış */
}
```

## 🎯 Hangi Birim Ne Zaman Kullanılmalı?

### Responsive Tasarım İçin

- `rem` - Font boyutları ve spacing için
- `%` - Genişlik ve yükseklik için
- `vw`, `vh` - Viewport boyutları için
- `em` - Component içi ölçekleme için

### Sabit Boyutlar İçin

- `px` - Border, shadow, küçük spacing için
- `px` - Pixel-perfect tasarımlar için

### Baskı İçin

- `pt`, `cm`, `mm`, `in` - Fiziksel ölçü birimleri

## ⚠️ Önemli Notlar

1. **Browser Uyumluluğu**: Tüm birimler tüm tarayıcılarda desteklenmeyebilir
2. **Performans**: Relative birimler absolute birimlere göre daha fazla hesaplama gerektirir
3. **Erişilebilirlik**: `rem` birimi kullanıcı font boyutu tercihlerine saygı gösterir
4. **Karma Kullanım**: Farklı birimleri birleştirirken dikkatli olunmalıdır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


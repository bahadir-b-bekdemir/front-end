# 🎨 CSS'DE RENK TANIMLARI

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları), HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementine biçimlendirme işlemi yaparken birçok renk tanımlama çeşidini kullanabilmektedir. Bu sayede istenilen herhangi bir HTML elementine, özelliğine veya içeriğine kolaylıkla renk tanımlama işlemleri yapılabilir.

CSS'de renk tanımlama işlemleri **4 farklı grup** ile sağlanmaktadır:

1. **Ana Renk (Named Colors)**
2. **RGB ve RGBA**
3. **HSL ve HSLA**
4. **Hexadecimal (Onaltılık)**

---

## 🎯 1. Ana Renk (Named Colors)

HTML'de tanımlı olan ana renkler, CSS kodları içerisinde doğrudan yazılarak kullanılabilir. Bu renkler, tarayıcılar tarafından önceden tanımlanmış standart renklerdir.

### 💡 Örnekler

```css
/* Temel renkler */
.text-black { color: black; }
.text-white { color: white; }
.text-red { color: red; }
.text-green { color: green; }
.text-blue { color: blue; }
.text-yellow { color: yellow; }
.text-orange { color: orange; }
.text-purple { color: purple; }
.text-pink { color: pink; }
.text-gray { color: gray; }
```

**Yaygın Kullanılan Ana Renkler:**
- `black`, `white`, `red`, `green`, `blue`, `yellow`, `orange`, `purple`, `pink`, `gray`, `brown`, `cyan`, `magenta`, `lime`, `navy`, `olive`, `teal`, `silver`, `maroon` vb.

**⚠️ Not:** Ana renkler sınırlıdır ve tüm renk tonlarını kapsamaz. Daha fazla renk seçeneği için diğer yöntemler kullanılmalıdır.

---

## 🔴 2. RGB ve RGBA

**RGB** (Red, Green, Blue - Kırmızı, Yeşil, Mavi), İngilizce olarak red (kırmızı), green (yeşil) ve blue (mavi) kelimelerinin baş harflerinden adını almış olan bir renk uzayıdır. Günümüzde tüm browser'lar (tarayıcılar) tarafından desteklendiği için en sık kullanılan renk tanımlaması özelliğini taşır.

### 📊 RGB Özellikleri

- Işığı temel alarak, doğadaki tüm renkleri tanımlayabilir
- Renk tanımlaması 3 temel referans (red, green, blue) ile belirtilir
- Her renk **0 ila 255** arasındaki değerlerle belirtilir
- Her renk %100 oranında karıştırılacak olursa **beyaz**, %0 oranında karıştırılacak olursa **siyah** renk elde edilir

### 💡 RGB Örnekleri

```css
/* RGB formatı */
.text-black { color: rgb(0, 0, 0); }
.text-white { color: rgb(255, 255, 255); }
.text-red { color: rgb(255, 0, 0); }
.text-green { color: rgb(0, 255, 0); }
.text-blue { color: rgb(0, 0, 255); }
.text-yellow { color: rgb(255, 255, 0); }
.text-custom { color: rgb(128, 64, 200); }
```

### 🌈 RGBA (Alpha Kanalı)

**RGBA**, RGB renk uzayına **alpha (alfa) kanalı** eklenmesiyle oluşur. Alpha kanalı şeffaflık / saydamlık ölçüsü özelliğini taşır.

- Alpha değeri **0.0 ila 1.0** arasında yazılır
- `0.0` = Tamamen şeffaf (görünmez)
- `1.0` = Tamamen opak (şeffaf değil)
- `0.5` = %50 şeffaf

### 💡 RGBA Örnekleri

```css
/* RGBA formatı */
.semi-transparent {
    background-color: rgba(0, 0, 0, 0.5); /* Siyah ve %50 şeffaf */
}

.light-overlay {
    background-color: rgba(255, 255, 255, 0.7); /* Beyaz ve %30 şeffaf */
}

.solid-red {
    background-color: rgba(255, 0, 0, 1.0); /* Kırmızı ve tamamen opak */
}

/* Modern CSS syntax (virgülsüz) */
.modern-rgb {
    background-color: rgb(255 0 0 / 0.5); /* Kırmızı, %50 şeffaf */
}
```

**💡 Modern CSS Syntax:** Modern CSS modülleri ile birlikte virgülsüz syntax da desteklenmektedir: `rgb(255 0 0 / 0.5)`

---

## 🌈 3. HSL ve HSLA

**HSL** (Hue, Saturation, Lightness - Renk Özü, Doygunluk, Açıklık), İngilizce olarak hue (renk özü), saturation (doygunluk) ve lightness (açıklık) kelimelerinin baş harflerinden adını almış olan bir renk uzayıdır.

### 📊 HSL Özellikleri

HSL bir renk kontrol ve düzeltme modeli olarak bilinir:

- **Hue (Renk Özü)**: Rengin baskın olan dalga uzunluğunu belirler. Açısal derece değeri alır ve bu değer **0° ila 360°** arasındadır. Derece değiştikçe farklı renkler elde edilir.
- **Saturation (Doygunluk)**: Rengin canlılığını belirler. Yüzdesel değer alır ve bu değer **%0 ila %100** arasındadır. Yüzde değeri düştükçe renk tonu grileşir, değer yükseldikçe renk tonu canlı renklere neden olur.
- **Lightness (Açıklık)**: Rengin aydınlığını belirler. Diğer bir deyiş ile rengin içerisindeki beyaz oranını belirler. Yüzdesel değer alır ve bu değer **%0 ila %100** arasındadır. Yüzde değeri düştükçe renk tonu koyulaşır, değer yükseldikçe renk tonu açıklaşır.

**En önemli kullanım alanı:** Bir resim üzerinde detay kaybetmeden renk değişikliklerini yapma olanağı verir.

### 💡 HSL Örnekleri

```css
/* HSL formatı */
.text-black { color: hsl(0, 0%, 0%); }
.text-white { color: hsl(0, 0%, 100%); }
.text-red { color: hsl(0, 100%, 50%); }
.text-green { color: hsl(120, 100%, 50%); }
.text-blue { color: hsl(240, 100%, 50%); }
.text-yellow { color: hsl(60, 100%, 50%); }

/* Farklı tonlar */
.light-blue { color: hsl(240, 100%, 75%); }
.dark-blue { color: hsl(240, 100%, 25%); }
.desaturated-red { color: hsl(0, 50%, 50%); }
```

### 🌈 HSLA (Alpha Kanalı)

**HSLA**, HSL renk uzayına **alpha (alfa) kanalı** eklenmesiyle oluşur. Alpha kanalı şeffaflık / saydamlık ölçüsü özelliğini taşır.

- Alpha değeri **0.0 ila 1.0** arasında yazılır

### 💡 HSLA Örnekleri

```css
/* HSLA formatı */
.semi-transparent {
    background-color: hsla(0, 0%, 0%, 0.5); /* Siyah ve %50 şeffaf */
}

.light-overlay {
    background-color: hsla(0, 0%, 100%, 0.7); /* Beyaz ve %30 şeffaf */
}

.solid-red {
    background-color: hsla(0, 100%, 50%, 1.0); /* Kırmızı ve tamamen opak */
}

/* Modern CSS syntax (virgülsüz) */
.modern-hsl {
    background-color: hsl(240 100% 50% / 0.5); /* Mavi, %50 şeffaf */
}
```

**💡 Modern CSS Syntax:** Modern CSS modülleri ile birlikte virgülsüz syntax da desteklenmektedir: `hsl(240 100% 50% / 0.5)`

---

## 🔢 4. Hexadecimal (Onaltılık)

**Hexadecimal (Onaltılık)** sayı sistemi, RGB renk uzayının hexadecimal formatında ifade edilmesidir. RGB renk uzayı, `00` ile `FF` arasında hexadecimal sayı sistemi ile hareket eder.

### 📊 Hexadecimal Özellikleri

- Doğadaki tüm renkleri tanımlayabilir
- Hexadecimal sayı sistemi yapısında `0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F` değerleri kullanılır
- Büyük harf küçük harf duyarlı değildir (`#FF0000` = `#ff0000`)
- Günümüzde tüm browser'lar tarafından desteklendiği için en sık kullanılan renk tanımlaması özelliğini taşır

### 💡 Hexadecimal Örnekleri

```css
/* 6 haneli format (tam format) */
.text-black { color: #000000; }
.text-white { color: #ffffff; }
.text-red { color: #ff0000; }
.text-green { color: #00ff00; }
.text-blue { color: #0000ff; }

/* 3 haneli format (kısa format) - Sadece aynı karakterler tekrarlanıyorsa */
.text-black { color: #000; } /* #000000 yerine */
.text-white { color: #fff; } /* #ffffff yerine */
.text-red { color: #f00; } /* #ff0000 yerine */
.text-green { color: #0f0; } /* #00ff00 yerine */
.text-blue { color: #00f; } /* #0000ff yerine */

/* Özel renkler */
.custom-color { color: #a1b2c3; }
.brand-color { color: #FF5733; }
```

**⚠️ Not:** 3 haneli format sadece her iki karakter aynı olduğunda kullanılabilir. Örneğin `#a1b2c3` için kısa format kullanılamaz.

---

## 🎨 Renk Formatlarının Karşılaştırılması

| Format | Avantajlar | Dezavantajlar | Kullanım Alanı |
|--------|------------|---------------|----------------|
| **Ana Renk** | Kolay hatırlanır, yazımı basit | Sınırlı renk seçeneği | Hızlı prototipleme, temel renkler |
| **RGB/RGBA** | Yaygın kullanım, tarayıcı desteği | Renk ayarlaması zor | Genel kullanım, şeffaflık gerektiğinde |
| **HSL/HSLA** | Renk ayarlaması kolay, sezgisel | Daha az yaygın | Renk tonları değiştirirken, tema sistemleri |
| **Hexadecimal** | Kısa yazım, yaygın kullanım | Okunması zor, renk ayarlaması zor | Production kod, tasarım dosyalarından kopyalama |

---

## 💡 Pratik Örnekler

### Örnek 1: Farklı Formatlarda Aynı Renk

```css
/* Hepsi aynı kırmızı rengi temsil eder */
.color-red-1 { color: red; }
.color-red-2 { color: rgb(255, 0, 0); }
.color-red-3 { color: rgba(255, 0, 0, 1.0); }
.color-red-4 { color: hsl(0, 100%, 50%); }
.color-red-5 { color: hsla(0, 100%, 50%, 1.0); }
.color-red-6 { color: #ff0000; }
.color-red-7 { color: #f00; }
```

### Örnek 2: Şeffaflık Kullanımı

```css
/* Yarı şeffaf arka plan */
.overlay {
    background-color: rgba(0, 0, 0, 0.5);
}

/* Şeffaf kenarlık */
.border-transparent {
    border: 2px solid rgba(255, 0, 0, 0.3);
}

/* Şeffaf gölge */
.shadow-transparent {
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
```

### Örnek 3: HSL ile Renk Tonları

```css
/* Ana renk */
.primary { color: hsl(240, 100%, 50%); }

/* Açık ton */
.light { color: hsl(240, 100%, 75%); }

/* Koyu ton */
.dark { color: hsl(240, 100%, 25%); }

/* Soluk ton */
.muted { color: hsl(240, 30%, 50%); }
```

---

## 🎯 Best Practices (En İyi Uygulamalar)

### 1. **Renk Değişkenleri Kullanın**

```css
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --text-color: #333333;
    --bg-color: #ffffff;
}

.element {
    color: var(--primary-color);
    background-color: var(--bg-color);
}
```

### 2. **HSL Kullanarak Tema Sistemi Oluşturun**

```css
:root {
    --hue: 240;
    --saturation: 100%;
    --lightness: 50%;
}

.element {
    color: hsl(var(--hue), var(--saturation), var(--lightness));
}

/* Tema değiştirmek için sadece --hue değerini değiştirin */
```

### 3. **Şeffaflık için RGBA/HSLA Kullanın**

```css
/* İyi */
.overlay {
    background-color: rgba(0, 0, 0, 0.5);
}

/* Kötü - opacity tüm içeriği etkiler */
.overlay {
    background-color: black;
    opacity: 0.5; /* Tüm içerik şeffaf olur */
}
```

---

## ⚠️ Önemli Notlar

1. **Büyük/Küçük Harf Duyarlılığı:** Hexadecimal renklerde büyük/küçük harf farkı yoktur (`#FF0000` = `#ff0000`).

2. **Modern CSS Syntax:** Modern CSS modülleri ile birlikte virgülsüz syntax desteklenmektedir:
   - `rgb(255 0 0 / 0.5)` (eski: `rgba(255, 0, 0, 0.5)`)
   - `hsl(240 100% 50% / 0.5)` (eski: `hsla(240, 100%, 50%, 0.5)`)

3. **Alpha Kanalı:** RGBA ve HSLA'da alpha değeri 0.0-1.0 arasındadır. Yüzde değeri de kullanılabilir: `rgba(255, 0, 0, 50%)`

4. **Renk Erişilebilirliği:** Renk seçerken kontrast oranlarını göz önünde bulundurun (WCAG standartları).

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

# 🎯 CSS KURALLARINDA SEVİYE BASAMAKLANDIRMA YAPISI (SPECIFICITY)

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) kodları ile HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementlerine biçimlendirme yapıldığında, browser'lar (tarayıcılar) web sayfalarını görüntülerken bir **seviye basamaklandırma yapısı** (CSS Specificity - Özgüllük) kurarlar. Bu sayede web sayfasının CSS ile atanmış olan biçimlendirmesi oluşmuş olur.

## 📊 Specificity (Özgüllük) Nedir?

Birden fazla CSS kuralı aynı HTML elementine uygulandığında, tarayıcı hangi kuralın öncelikli olacağını belirlemek için **specificity** (özgüllük) değerini hesaplar. Yüksek özgüllük değerine sahip kurallar, düşük özgüllük değerine sahip kuralları geçersiz kılar.

## 🔢 Specificity Hesaplama Sistemi

CSS seçicilerine göre seviye basamaklandırma yapısı için değerlendirme sırası 4 temel birim üzerinden gerçekleşir ve bir numaralandırma yapısı kurulur. Her birim 0 veya 1 değerini alabilir (veya daha fazla, bazı durumlarda).

| Öncelik | Birim | Değer | Tanım | Numaralandırmaya Etkisi |
|---------|-------|-------|-------|-------------------------|
| **1** | **a** | 0 veya 1 | Satır içi CSS (Inline CSS) tanımı | `X000` |
| **2** | **b** | 0 veya 1+ | ID (Benzersiz kimlik) seçicisi ile CSS tanımı | `0X00` |
| **3** | **c** | 0 veya 1+ | Class (Sınıf), Attribute (Özellik) ve Pseudo-class seçicileri ile CSS tanımı | `00X0` |
| **4** | **d** | 0 veya 1+ | Element (Tür) ve Pseudo-element seçicileri ile CSS tanımı | `000X` |

### 📝 Önemli Notlar

- **Satır içi CSS** (`style` attribute) en yüksek önceliğe sahiptir (a=1)
- **ID seçicileri** class seçicilerinden daha güçlüdür
- **Class seçicileri** element seçicilerinden daha güçlüdür
- **Element seçicileri** en düşük önceliğe sahiptir
- Birden fazla seçici türü bir arada kullanıldığında değerler toplanır

## 📋 Örnek Specificity Hesaplamaları

Aşağıda farklı seçicilerin specificity değerleri örneklerle gösterilmiştir:

| Seçici | Seçici Değerlendirmesi | Seviye Değerlendirmesi | Seviye Değeri |
|--------|------------------------|------------------------|--------------|
| `*` | Genel (Evrensel) seçici | a=0, b=0, c=0, d=0 | `0000` |
| `div` | Element seçici | a=0, b=0, c=0, d=1 | `0001` |
| `ul li` | İkili Element seçici | a=0, b=0, c=0, d=2 | `0002` |
| `div div + span` | Üçlü Element seçici | a=0, b=0, c=0, d=3 | `0003` |
| `img[title="saat"]` | Element ve Attribute seçici | a=0, b=0, c=1, d=1 | `0011` |
| `.renkler` | Class (Sınıf) seçici | a=0, b=0, c=1, d=0 | `0010` |
| `div.renkler` | Element ve Class seçici | a=0, b=0, c=1, d=1 | `0011` |
| `#esyalar` | ID (Benzersiz kimlik) seçici | a=0, b=1, c=0, d=0 | `0100` |
| `div#esyalar` | Element ve ID seçici | a=0, b=1, c=0, d=1 | `0101` |
| `div.renkler#esyalar` | Element, Class ve ID seçici | a=0, b=1, c=1, d=1 | `0111` |
| `<a style="color:black">` | Satır içi tanımlama | a=1, b=0, c=0, d=0 | `1000` |

## 💡 Pratik Örnekler

### Örnek 1: Basit Specificity Karşılaştırması

```css
/* Specificity: 0001 (Element seçici) */
div {
    color: blue;
}

/* Specificity: 0010 (Class seçici) - Bu kazanır! */
.container {
    color: red;
}
```

**Sonuç:** `.container` class'ına sahip div elementleri kırmızı renkte görünecektir.

### Örnek 2: ID vs Class

```css
/* Specificity: 0010 (Class seçici) */
.menu {
    background-color: white;
}

/* Specificity: 0100 (ID seçici) - Bu kazanır! */
#header {
    background-color: black;
}
```

**Sonuç:** ID seçicisi class seçicisinden daha güçlü olduğu için `#header` kazanır.

### Örnek 3: Satır İçi CSS (En Güçlü)

```css
/* Specificity: 0010 (Class seçici) */
.text {
    color: blue;
}
```

```html
<!-- Specificity: 1000 (Satır içi) - Bu kazanır! -->
<p class="text" style="color: red;">Bu metin kırmızıdır</p>
```

**Sonuç:** Satır içi CSS en yüksek önceliğe sahip olduğu için metin kırmızı görünecektir.

### Örnek 4: Karmaşık Seçiciler

```css
/* Specificity: 0002 (İki element seçici) */
div p {
    font-size: 14px;
}

/* Specificity: 0011 (Element + Class) - Bu kazanır! */
div.content p {
    font-size: 16px;
}
```

**Sonuç:** `div.content p` seçicisi daha yüksek specificity değerine sahip olduğu için kazanır.

## ⚠️ Özel Durumlar

### `!important` Kuralı

`!important` kullanıldığında, o kural tüm specificity hesaplamalarını geçersiz kılar ve en yüksek önceliğe sahip olur.

```css
div {
    color: blue !important; /* Bu her zaman kazanır */
}

#header {
    color: red; /* Specificity: 0100 ama !important yok */
}
```

**⚠️ Uyarı:** `!important` kullanımından mümkün olduğunca kaçınılmalıdır çünkü CSS kodlarının bakımını zorlaştırır.

### Aynı Specificity Değerine Sahip Kurallar

Aynı specificity değerine sahip kurallar varsa, **en son tanımlanan kural** geçerli olur (Cascade - Basamaklama prensibi).

```css
/* Her ikisi de 0010 specificity değerine sahip */
.text {
    color: blue;
}

.text {
    color: red; /* Bu kazanır çünkü en son tanımlanan */
}
```

## 🎯 Best Practices (En İyi Uygulamalar)

1. **ID seçicilerinden kaçının:** ID seçicileri çok yüksek specificity değerine sahiptir ve kod bakımını zorlaştırır.
2. **Class seçicilerini tercih edin:** Class seçicileri daha esnek ve yeniden kullanılabilirdir.
3. **Satır içi CSS'den kaçının:** Satır içi CSS kullanımı specificity sorunlarına yol açar.
4. **`!important` kullanmayın:** Mümkün olduğunca `!important` kullanımından kaçının.
5. **Specificity değerlerini düşük tutun:** Mümkün olduğunca düşük specificity değerli seçiciler kullanın.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

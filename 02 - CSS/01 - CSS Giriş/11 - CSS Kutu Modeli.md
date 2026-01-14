# 📦 CSS'DE KUTU MODELİ (BOX MODEL)

HTML'de (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) her element dikdörtgen şeklinde bir alan işgal eder. HTML elementlerinin işgal ettikleri alan, CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) **kutu modeli** (Box Model) olarak isimlendirilmektedir. Çünkü CSS her HTML elementini kutu olarak kabul eder. Hemen hemen her kutu modeli, her HTML elementinin işlevselliğini açıklamaya ve anlamaya yardımcı olur.

Bir HTML elementinin blok düzeyinde olması veya satır düzeyinde olması, pozisyonları, varsayılan özellikleri, gösterim türleri, renklendirilmesi vs. tüm işlemler CSS sayesinde belirlenebilir.

## 🎯 Kutu Modelinin Bileşenleri

Bir HTML elementinin kutu modelinde dört temel alan bulunur. Bu alanlar içten dışa doğru şu şekildedir:

1. **Content (İçerik)**: Elementin gerçek içeriği (metin, resim, video vb.)
2. **Padding (Dolgu / İç Boşluk)**: İçerik ile kenarlık arasındaki boşluk
3. **Border (Kenarlık / Çerçeve)**: Padding'i çevreleyen görünür çizgi
4. **Margin (Kenar Boşluğu / Dış Boşluk)**: Border'ın dışındaki boşluk (diğer elementlerle arasındaki mesafe)

Aynı zamanda bir HTML elementinin kutu modeline göre konum değerleri de bulunmaktadır. Konum değerlerinde, **top** (üst), **right** (sağ), **bottom** (alt) ve **left** (sol) pozisyonları bulunur.

## 📐 Kutu Modelinin Görsel Yapısı

Kutu modelinin tam yapısı aşağıdaki şekildedir:

![CSS Kutu Modeli](11%20-%20CSS%20Kutu%20Modeli.png)

## 📏 Kutu Modeli Boyut Hesaplaması

Kutu modeli dikdörtgen şeklinde bir alan işgal eder. Bu alanın boyutları sayesinde bir HTML elementinin tüm browser'larda (tarayıcılarda) en doğru şekilde görüntülenmesi sağlanır. Fakat bunun için öncelikle kutu modeli boyutunun nasıl hesaplandığını bilmek gerekir.

Hesaplama işlemi 2 yapı ile sağlanır:
1. **Genişlik hesaplama**
2. **Yükseklik hesaplama**

### 📊 Genişlik Hesaplaması

Bir HTML elementi kutu modelinin genişlik hesaplaması:

```
Total width = width + left padding + right padding + left border + right border + left margin + right margin
```

**Türkçe:**
```
Toplam genişlik = genişlik + sol dolgu / iç boşluk + sağ dolgu / iç boşluk + sol kenarlık / çerçeve + sağ kenarlık / çerçeve + sol kenar boşluğu / dış boşluk + sağ kenar boşluğu / dış boşluk
```

### 📊 Yükseklik Hesaplaması

Bir HTML elementi kutu modelinin yükseklik hesaplaması:

```
Total height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin
```

**Türkçe:**
```
Toplam yükseklik = yükseklik + üst dolgu / iç boşluk + alt dolgu / iç boşluk + üst kenarlık / çerçeve + alt kenarlık / çerçeve + üst kenar boşluğu / dış boşluk + alt kenar boşluğu / dış boşluk
```

## 💡 Pratik Örnek

```css
.box {
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
```

**Hesaplama:**
- **Toplam Genişlik**: 200px (width) + 20px (left padding) + 20px (right padding) + 5px (left border) + 5px (right border) + 10px (left margin) + 10px (right margin) = **270px**
- **Toplam Yükseklik**: 100px (height) + 20px (top padding) + 20px (bottom padding) + 5px (top border) + 5px (bottom border) + 10px (top margin) + 10px (bottom margin) = **170px**

## 🔧 Box-Sizing Özelliği

CSS'de `box-sizing` özelliği, kutu modelinin boyut hesaplamasını kontrol eder. İki ana değeri vardır:

### `content-box` (Varsayılan)

Padding ve border değerleri, width ve height değerlerine eklenir.

```css
.box {
    box-sizing: content-box;
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    /* Toplam genişlik: 200px + 20px + 20px + 5px + 5px = 250px */
}
```

### `border-box` (Önerilen)

Padding ve border değerleri, width ve height değerlerinin içine dahil edilir.

```css
.box {
    box-sizing: border-box;
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    /* Toplam genişlik: 200px (padding ve border dahil) */
}
```

**💡 İpucu:** Çoğu modern CSS framework'ü ve geliştirici, tüm elementler için `border-box` kullanmayı önerir:

```css
* {
    box-sizing: border-box;
}
```

## 🎨 Kutu Modeli Özellikleri

### Margin (Kenar Boşluğu / Dış Boşluk)

Elementin dışındaki boşluktur. Diğer elementlerle arasındaki mesafeyi belirler.

```css
/* Tek değer - tüm yönler */
margin: 10px;

/* İki değer - üst/alt ve sol/sağ */
margin: 10px 20px;

/* Üç değer - üst, sol/sağ, alt */
margin: 10px 20px 15px;

/* Dört değer - üst, sağ, alt, sol (saat yönü) */
margin: 10px 20px 15px 5px;

/* Yönlere özel */
margin-top: 10px;
margin-right: 20px;
margin-bottom: 15px;
margin-left: 5px;
```

### Padding (Dolgu / İç Boşluk)

İçerik ile kenarlık arasındaki boşluktur.

```css
/* Margin ile aynı kullanım şekli */
padding: 10px;
padding: 10px 20px;
padding: 10px 20px 15px;
padding: 10px 20px 15px 5px;

padding-top: 10px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 5px;
```

### Border (Kenarlık / Çerçeve)

Padding'i çevreleyen görünür çizgidir.

```css
/* Kısa yazım */
border: 2px solid black;

/* Ayrı ayrı */
border-width: 2px;
border-style: solid;
border-color: black;

/* Yönlere özel */
border-top: 2px solid red;
border-right: 3px dashed blue;
border-bottom: 1px dotted green;
border-left: 4px double orange;
```

## ⚠️ Önemli Notlar

1. **Margin Collapse (Margin Çökmesi):** Dikey (üst-alt) margin'ler birbirine yakın elementlerde birleşir (collapse). Yatay (sol-sağ) margin'ler birleşmez.

2. **Negatif Margin:** Margin değerleri negatif olabilir ve elementlerin üst üste binmesine neden olabilir.

3. **Auto Değeri:** Margin için `auto` değeri kullanıldığında, element yatay olarak ortalanır (sadece block elementler için).

```css
.center {
    width: 300px;
    margin: 0 auto; /* Yatay ortalama */
}
```

4. **Inline Elementler:** Inline elementlerde yukarı-aşağı margin ve padding çalışmaz, sadece yatay olarak etkilidir.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

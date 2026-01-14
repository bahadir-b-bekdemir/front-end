# 📄 HTML PARAGRAF VE METİN ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) metin içeriğini yapılandırmak ve biçimlendirmek için kullanılan temel etiketler bulunmaktadır.

## 📋 Paragraf Etiketi

### `<p>...</p>`

Paragraf etiketi, metin içeriğini paragraflar halinde düzenlemek için kullanılır. Her paragraf varsayılan olarak üst ve alt boşluklara sahiptir.

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Paragraf Örneği</title>
</head>
<body>
    <p>Bu bir paragraftır. Paragraf etiketi metin içeriğini düzenli bir şekilde görüntülemek için kullanılır.</p>
    
    <p>Bu ikinci bir paragraftır. Her paragraf yeni bir satırda başlar ve altında boşluk bırakır.</p>
    
    <p>Paragraflar arasında otomatik olarak boşluk bırakılır. Bu, okunabilirliği artırır.</p>
</body>
</html>
```

## 📋 Metin Biçimlendirme Etiketleri

### `<b>...</b>` ve `<strong>...</strong>`

**Kalın yazı** için kullanılır. `<b>` sadece görsel olarak kalın yapar, `<strong>` ise hem görsel hem de anlamsal olarak önemli olduğunu belirtir.

**Kullanım örneği:**
```html
<p>Bu metin <b>kalın</b> görünecektir.</p>
<p>Bu metin <strong>önemli</strong> olduğu için kalın görünecektir.</p>
```

### `<i>...</i>` ve `<em>...</em>`

**İtalik yazı** için kullanılır. `<i>` sadece görsel olarak italik yapar, `<em>` ise hem görsel hem de anlamsal olarak vurgulu olduğunu belirtir.

**Kullanım örneği:**
```html
<p>Bu metin <i>italik</i> görünecektir.</p>
<p>Bu metin <em>vurgulu</em> olduğu için italik görünecektir.</p>
```

### `<u>...</u>`

**Altı çizili yazı** için kullanılır.

**Kullanım örneği:**
```html
<p>Bu metin <u>altı çizili</u> görünecektir.</p>
```

### `<mark>...</mark>`

Metni **vurgulamak** için kullanılır. Genellikle sarı arka plan rengi ile görüntülenir.

**Kullanım örneği:**
```html
<p>Bu metin içinde <mark>önemli bir kısım</mark> vurgulanmıştır.</p>
```

### `<small>...</small>`

Metni **küçük** göstermek için kullanılır.

**Kullanım örneği:**
```html
<p>Normal metin <small>küçük metin</small> normal metin.</p>
```

### `<del>...</del>`

**Silinmiş metin** için kullanılır. Genellikle üzeri çizili olarak görüntülenir.

**Kullanım örneği:**
```html
<p>Eski fiyat: <del>100 TL</del> Yeni fiyat: 80 TL</p>
```

### `<ins>...</ins>`

**Eklenmiş metin** için kullanılır. Genellikle altı çizili olarak görüntülenir.

**Kullanım örneği:**
```html
<p>Bu metin <ins>yeni eklenmiştir</ins>.</p>
```

### `<sub>...</sub>`

**Alt simge** (subscript) için kullanılır.

**Kullanım örneği:**
```html
<p>H<sub>2</sub>O (Su molekülü)</p>
<p>E=mc<sub>2</sub> (Einstein'ın formülü)</p>
```

### `<sup>...</sup>`

**Üst simge** (superscript) için kullanılır.

**Kullanım örneği:**
```html
<p>2<sup>3</sup> = 8</p>
<p>E=mc<sup>2</sup></p>
<p>Birinci<sup>1</sup> İkinci<sup>2</sup></p>
```

## 💡 Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Metin Biçimlendirme Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
        }
    </style>
</head>
<body>
    <h1>Metin Biçimlendirme Örnekleri</h1>
    
    <h2>Paragraflar</h2>
    <p>Bu bir paragraf örneğidir. Paragraflar metin içeriğini düzenli bir şekilde görüntülemek için kullanılır.</p>
    <p>Her paragraf yeni bir satırda başlar ve okunabilirliği artırır.</p>
    
    <h2>Kalın Metin</h2>
    <p>Bu metin <b>kalın</b> görünecektir.</p>
    <p>Bu metin <strong>önemli</strong> olduğu için kalın görünecektir.</p>
    
    <h2>İtalik Metin</h2>
    <p>Bu metin <i>italik</i> görünecektir.</p>
    <p>Bu metin <em>vurgulu</em> olduğu için italik görünecektir.</p>
    
    <h2>Vurgulama</h2>
    <p>Bu metin içinde <mark>önemli bir kısım</mark> vurgulanmıştır.</p>
    
    <h2>Küçük Metin</h2>
    <p>Normal metin <small>küçük metin</small> normal metin.</p>
    
    <h2>Silinmiş ve Eklenmiş Metin</h2>
    <p>Eski fiyat: <del>100 TL</del> Yeni fiyat: <ins>80 TL</ins></p>
    
    <h2>Alt ve Üst Simgeler</h2>
    <p>Su molekülü: H<sub>2</sub>O</p>
    <p>Einstein'ın formülü: E=mc<sup>2</sup></p>
    <p>Matematik: 2<sup>3</sup> = 8</p>
    
    <h2>Kombine Kullanım</h2>
    <p>Bu metin <b><i>hem kalın hem italik</i></b> görünecektir.</p>
    <p>Bu metin <strong><mark>önemli ve vurgulu</mark></strong> görünecektir.</p>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Anlamsal Etiketler**: `<strong>` ve `<em>` etiketleri hem görsel hem de anlamsal önem taşır. **SEO** ve erişilebilirlik açısından tercih edilmelidir.

2. **Paragraf Boşlukları**: Paragraflar arasındaki boşluklar **CSS** ile özelleştirilebilir.

3. **İç İçe Kullanım**: Metin biçimlendirme etiketleri birbirinin içinde kullanılabilir.

4. **Erişilebilirlik**: Ekran okuyucular `<strong>` ve `<em>` etiketlerini farklı şekilde okuyabilir.

## 🎯 İyi Pratikler

- Anlamsal etiketleri (`<strong>`, `<em>`) görsel etiketlere (`<b>`, `<i>`) tercih edin
- Paragrafları içeriği düzenlemek için kullanın
- Metin biçimlendirmeyi aşırı kullanmaktan kaçının
- Erişilebilirlik için anlamsal etiketleri tercih edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🎨 CSS NEDİR?

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları), HTML'e (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) ek olarak metin ve format biçimlendirme alanında fazladan olanaklar sunan bir doküman biçimlendirme dili ve web teknolojisidir.

İnternet sayfaları için genel şablonlar hazırlama olanağı verdiği gibi, bağımsız olarak da sayfaların, alanların, arkaplanların, formların, butonların, input'ların (girişlerin), resimlerin, videoların, seslerin ve dokümanlar gibi dosyaların, metinlerin, tuvallerin vs. gerek stillerini (renk, yazı tipi, boyut vs.), gerek konumlarını, gerekse de özelliklerini değiştirmek için de kullanılabilir.

CSS'in en önemli özelliği kullanımındaki esnekliktir. Genellikle bir web sayfası içerisinde birbiriyle uyumlu birkaç renk, birkaç yazı tipi, birkaç taslak vs. stiller kullanılır. Kullanılan bu stilleri her sayfada ayrı ayrı tekrar belirtmek yerine CSS yardımıyla bir defa tanımlayıp bütün web sayfalarında ortak olarak kullanabiliriz. Bu sayede:

- 💾 Sayfaların hafızadaki boyutunu hatırı sayılır bir oranda küçülecek
- 🔄 Değişik HTML sayfalarında kullanılmasını da sağlayacak
- 📱 Aynı sayfanın değişik aygıtlara göre formatlandırılmasını da kolaylaştıracak
- 🎯 Sunumla yapıyı ayırarak değişiklik yapılmasını da kolaylaştıracaktır

## 📋 CSS Kuralları

CSS kuralları üç parçadan oluşur. Her CSS kuralı bir seçici ve bir tanımlama bölümüne sahiptir. Tanımlama bölümü de bir özellik ve bir değerden meydana gelir.

```css
seçici { özellik: değer; }
```

### 🎯 Seçici

Bir CSS kuralında seçici olarak bir HTML ögesinin ismi, kimliği veya sınıfı kullanılabilir.

**Örnek:** `body`, `div`, `p`, `a`, `span` vs.

### ⚙️ Özellik ve Değer

CSS kurallarında özellik olarak sadece belirli tanımlı maddeler kullanılabilir. Değer olarak ise her özelliğin alabileceği kendi değerleri vardır. Tanımlama bölümünde birden fazla özellik giriliyorsa aralarına `;` (noktalı virgül) koyulmalıdır. Sadece tek bir değer girilecek olur ise sonuna `;` (noktalı virgül) koyulmayabilir ancak değerin sonuna `;` (noktalı virgül) eklemenin hiçbir sakıncası yoktur.

**Örnekler:**

```css
body {
    background-color: black;
}

div {
    font-size: 10px;
    color: blue;
}
```

### 🔗 Çoklu Seçici

Aynı değerleri vereceğimiz birden fazla seçiciyi aralarına `,` (virgül) koyarak tek seferde tanımlayabiliriz.

```css
body, div, p, a, span {
    font-size: 12pt;
    color: black;
}
```

## 🔌 CSS Kodlarının HTML'e Eklenmesi

CSS kodları HTML'in sayfa içeriğinde `head` veya `body` etiketleri içerisine yazılabilir. CSS kodlarının HTML dosyasına eklenmesi dört farklı şekilde yapılabilir.

### 1. 📄 Harici CSS Dosyası

HTML dosyası harici CSS dosyasına / dosyalarına referans verebilir. Bu yöntem en çok tercih edilen ve önerilen yöntemdir.

```html
<link rel="stylesheet" href="dosya.css">
```

### 2. 📝 Inline CSS (Satır İçi CSS)

HTML etiketlerinin içine doğrudan `style` özelliği ile CSS eklenebilir.

```html
<div style="color: red;">...</div>
```

### 3. 📦 Internal CSS (Dahili CSS)

HTML dosyasının `<head>` veya `<body>` bölümüne `<style>` etiketi içerisinde CSS kodları yazılabilir.

```html
<style>
    div {
        color: red;
    }
</style>
```

### 4. ⚡ JavaScript ile CSS Ekleme

JavaScript dili kullanılarak HTML dosyasına dinamik olarak CSS eklenebilir.

```html
<script>
    var islem = document.createElement("style");
    // Modern tarayıcılarda type="text/css" artık gerekli değildir
    islem.innerHTML = "div { color: red; }";
    document.body.appendChild(islem);
</script>
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

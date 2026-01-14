# 🌐 DOM MANİPÜLASYONU

DOM (Document Object Model), HTML belgelerinin yapısını temsil eden bir ağaç yapısıdır. JavaScript ile DOM üzerinde değişiklikler yaparak web sayfalarını dinamik hale getirebiliriz.

## 📄 DOM Nedir?

DOM, HTML belgesinin tüm elemanlarını nesne olarak temsil eder. Her HTML elemanı bir DOM nesnesidir ve JavaScript ile manipüle edilebilir.

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Örneği</title>
</head>
<body>
    <h1 id="baslik">Merhaba Dünya</h1>
    <p class="metin">Bu bir paragraf</p>
</body>
</html>
```

## 🔍 DOM Elemanlarını Seçme

### getElementById()

ID'ye göre tek bir eleman seçer:

```javascript
var baslik = document.getElementById("baslik");
console.log(baslik); // <h1> elementi
```

### getElementsByClassName()

Class adına göre elemanları seçer (dizi döner):

```javascript
var metinler = document.getElementsByClassName("metin");
console.log(metinler); // HTMLCollection (dizi benzeri)
```

### getElementsByTagName()

Etiket adına göre elemanları seçer (dizi döner):

```javascript
var paragraflar = document.getElementsByTagName("p");
console.log(paragraflar); // HTMLCollection
```

### querySelector() - Modern Yöntem

CSS seçici kullanarak tek bir eleman seçer:

```javascript
var baslik = document.querySelector("#baslik");
var metin = document.querySelector(".metin");
var ilkParagraf = document.querySelector("p");
```

### querySelectorAll() - Modern Yöntem

CSS seçici kullanarak tüm elemanları seçer (dizi döner):

```javascript
var tumMetinler = document.querySelectorAll(".metin");
var tumParagraflar = document.querySelectorAll("p");
```

## ✏️ DOM Elemanlarını Değiştirme

### innerHTML - İçerik Değiştirme

```javascript
var baslik = document.getElementById("baslik");
baslik.innerHTML = "Yeni Başlık";

// HTML içeriği ekleme
baslik.innerHTML = "<strong>Kalın Başlık</strong>";
```

### textContent - Metin İçeriği

```javascript
var baslik = document.getElementById("baslik");
baslik.textContent = "Yeni Metin"; // HTML etiketleri eklenmez
```

### innerText - Görünür Metin

```javascript
var baslik = document.getElementById("baslik");
baslik.innerText = "Görünür Metin";
```

## 🎨 Stil Değiştirme

### style Özelliği

```javascript
var baslik = document.getElementById("baslik");

// Tek stil özelliği
baslik.style.color = "red";
baslik.style.fontSize = "24px";
baslik.style.backgroundColor = "yellow";

// CSS özellik adları camelCase olmalı
baslik.style.fontSize = "20px"; // fontSize (font-size değil)
baslik.style.marginTop = "10px"; // marginTop
```

### className - Class Değiştirme

```javascript
var eleman = document.getElementById("baslik");

// Class ekleme
eleman.className = "yeni-class";

// Birden fazla class
eleman.className = "class1 class2 class3";
```

### classList - Modern Class Yönetimi

```javascript
var eleman = document.getElementById("baslik");

// Class ekleme
eleman.classList.add("aktif");
eleman.classList.add("vurgulu");

// Class kaldırma
eleman.classList.remove("aktif");

// Class değiştirme (varsa kaldır, yoksa ekle)
eleman.classList.toggle("aktif");

// Class kontrolü
if (eleman.classList.contains("aktif")) {
    console.log("Aktif class var");
}
```

## ➕ Yeni Eleman Ekleme

### createElement() - Eleman Oluşturma

```javascript
// Yeni paragraf oluştur
var yeniParagraf = document.createElement("p");
yeniParagraf.textContent = "Yeni paragraf metni";
yeniParagraf.className = "yeni-class";

// Body'ye ekle
document.body.appendChild(yeniParagraf);
```

### appendChild() - Alt Eleman Ekleme

```javascript
var container = document.getElementById("container");
var yeniDiv = document.createElement("div");
yeniDiv.textContent = "Yeni div";
container.appendChild(yeniDiv);
```

### insertBefore() - Belirli Konuma Ekleme

```javascript
var container = document.getElementById("container");
var yeniDiv = document.createElement("div");
yeniDiv.textContent = "Yeni div";
var mevcutDiv = document.getElementById("mevcut");
container.insertBefore(yeniDiv, mevcutDiv);
```

## 🗑️ Eleman Silme

### removeChild() - Alt Eleman Silme

```javascript
var container = document.getElementById("container");
var silinecek = document.getElementById("silinecek");
container.removeChild(silinecek);
```

### remove() - Modern Yöntem

```javascript
var silinecek = document.getElementById("silinecek");
silinecek.remove();
```

## 🔍 Özellik (Attribute) İşlemleri

### getAttribute() - Özellik Okuma

```javascript
var link = document.querySelector("a");
var href = link.getAttribute("href");
console.log(href);
```

### setAttribute() - Özellik Ayarlama

```javascript
var link = document.querySelector("a");
link.setAttribute("href", "https://example.com");
link.setAttribute("target", "_blank");
```

### removeAttribute() - Özellik Silme

```javascript
var link = document.querySelector("a");
link.removeAttribute("target");
```

### hasAttribute() - Özellik Kontrolü

```javascript
var link = document.querySelector("a");
if (link.hasAttribute("href")) {
    console.log("href özelliği var");
}
```

## 💡 Pratik Örnekler

### Dinamik Liste Oluşturma

```javascript
var ul = document.createElement("ul");
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

isimler.forEach(function(isim) {
    var li = document.createElement("li");
    li.textContent = isim;
    ul.appendChild(li);
});

document.body.appendChild(ul);
```

### Buton ile İçerik Değiştirme

```html
<button id="degistirBtn">Değiştir</button>
<p id="metin">Orijinal metin</p>

<script>
var btn = document.getElementById("degistirBtn");
var metin = document.getElementById("metin");

btn.addEventListener("click", function() {
    metin.textContent = "Değiştirilmiş metin";
    metin.style.color = "red";
});
</script>
```

### Form Validasyonu

```html
<input type="text" id="isim" placeholder="İsim girin">
<button id="kontrolBtn">Kontrol Et</button>
<p id="sonuc"></p>

<script>
var btn = document.getElementById("kontrolBtn");
var isim = document.getElementById("isim");
var sonuc = document.getElementById("sonuc");

btn.addEventListener("click", function() {
    if (isim.value.length < 3) {
        sonuc.textContent = "İsim en az 3 karakter olmalı";
        sonuc.style.color = "red";
        isim.style.borderColor = "red";
    } else {
        sonuc.textContent = "İsim geçerli";
        sonuc.style.color = "green";
        isim.style.borderColor = "green";
    }
});
</script>
```

### Dinamik Tablo Oluşturma

```javascript
var veriler = [
    {isim: "Bahadır", yas: 25},
    {isim: "Bekdemir", yas: 30},
    {isim: "JavaScript", yas: 28}
];

var table = document.createElement("table");
var thead = document.createElement("thead");
var tbody = document.createElement("tbody");

// Başlık satırı
var tr = document.createElement("tr");
["İsim", "Yaş"].forEach(function(baslik) {
    var th = document.createElement("th");
    th.textContent = baslik;
    tr.appendChild(th);
});
thead.appendChild(tr);

// Veri satırları
veriler.forEach(function(veri) {
    var tr = document.createElement("tr");
    [veri.isim, veri.yas].forEach(function(deger) {
        var td = document.createElement("td");
        td.textContent = deger;
        tr.appendChild(td);
    });
    tbody.appendChild(tr);
});

table.appendChild(thead);
table.appendChild(tbody);
document.body.appendChild(table);
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


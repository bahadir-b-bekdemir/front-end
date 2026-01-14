# 📋 DİZİLER (ARRAYS)

Diziler, birden fazla değeri sıralı bir şekilde saklamak için kullanılan veri yapılarıdır. JavaScript'te diziler dinamik olarak büyüyüp küçülebilir.

## 📦 Dizi Oluşturma

### 🔵 Array Literal (Dizi Değişmez)

```javascript
// Boş dizi
var dizi = [];

// Öğeli dizi
var sayilar = [1, 2, 3, 4, 5];
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];
var karisik = [1, "Bahadır", true, null];
```

### 🔵 new Array()

```javascript
var dizi1 = new Array(); // Boş dizi
var dizi2 = new Array(5); // 5 elemanlı dizi
var dizi3 = new Array(1, 2, 3); // [1, 2, 3]
```

## 🔍 Dizi Elemanlarına Erişim

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

// İndeks ile erişim (0'dan başlar)
console.log(isimler[0]); // "Bahadır"
console.log(isimler[1]); // "Bekdemir"
console.log(isimler[2]); // "JavaScript"

// Son elemana erişim
console.log(isimler[isimler.length - 1]); // "JavaScript"
```

## ✏️ Dizi Elemanlarını Değiştirme

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

// Eleman değiştirme
isimler[0] = "Yeni İsim";
console.log(isimler); // ["Yeni İsim", "Bekdemir", "JavaScript"]

// Yeni eleman ekleme
isimler[3] = "Yeni Eleman";
console.log(isimler); // ["Yeni İsim", "Bekdemir", "JavaScript", "Yeni Eleman"]
```

## 📏 Dizi Uzunluğu

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

console.log(isimler.length); // 3

// Uzunluk değiştirme
isimler.length = 2;
console.log(isimler); // ["Bahadır", "Bekdemir"] (son eleman silindi)
```

## ➕ Diziye Eleman Ekleme

### push() - Sonuna Ekleme

```javascript
var dizi = [1, 2, 3];
dizi.push(4);
console.log(dizi); // [1, 2, 3, 4]

dizi.push(5, 6);
console.log(dizi); // [1, 2, 3, 4, 5, 6]
```

### unshift() - Başına Ekleme

```javascript
var dizi = [2, 3, 4];
dizi.unshift(1);
console.log(dizi); // [1, 2, 3, 4]

dizi.unshift(-1, 0);
console.log(dizi); // [-1, 0, 1, 2, 3, 4]
```

## ➖ Diziden Eleman Çıkarma

### pop() - Sondan Çıkarma

```javascript
var dizi = [1, 2, 3, 4];
var sonEleman = dizi.pop();
console.log(sonEleman); // 4
console.log(dizi); // [1, 2, 3]
```

### shift() - Baştan Çıkarma

```javascript
var dizi = [1, 2, 3, 4];
var ilkEleman = dizi.shift();
console.log(ilkEleman); // 1
console.log(dizi); // [2, 3, 4]
```

### splice() - Belirli Konumdan Çıkarma

```javascript
var dizi = [1, 2, 3, 4, 5];

// İndeks 2'den başlayarak 1 eleman sil
dizi.splice(2, 1);
console.log(dizi); // [1, 2, 4, 5]

// İndeks 1'den başlayarak 2 eleman sil ve yeni elemanlar ekle
dizi.splice(1, 2, "a", "b");
console.log(dizi); // [1, "a", "b", 5]
```

## 🔍 Dizi Arama

### indexOf() - İndeks Bulma

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

var indeks = isimler.indexOf("Bekdemir");
console.log(indeks); // 1

var indeks2 = isimler.indexOf("Bulunamayan");
console.log(indeks2); // -1 (bulunamadı)
```

### includes() - Varlık Kontrolü

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

console.log(isimler.includes("Bahadır")); // true
console.log(isimler.includes("Yok")); // false
```

### find() - Koşula Uyan Eleman

```javascript
var sayilar = [1, 2, 3, 4, 5];

var bulunan = sayilar.find(function(sayi) {
    return sayi > 3;
});
console.log(bulunan); // 4
```

## 🔄 Dizi Dolaşma

### for Döngüsü

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

for (var i = 0; i < isimler.length; i++) {
    console.log(isimler[i]);
}
```

### for...of Döngüsü

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

for (var isim of isimler) {
    console.log(isim);
}
```

### forEach() Metodu

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

isimler.forEach(function(isim, indeks) {
    console.log(indeks + ": " + isim);
});
```

## 🔄 Dizi Dönüşüm Metodları

### map() - Her Elemanı Dönüştürme

```javascript
var sayilar = [1, 2, 3, 4, 5];

var kareler = sayilar.map(function(sayi) {
    return sayi * sayi;
});
console.log(kareler); // [1, 4, 9, 16, 25]

// Arrow function ile
var kareler2 = sayilar.map(x => x * x);
```

### filter() - Filtreleme

```javascript
var sayilar = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

var ciftSayilar = sayilar.filter(function(sayi) {
    return sayi % 2 === 0;
});
console.log(ciftSayilar); // [2, 4, 6, 8, 10]
```

### reduce() - Azaltma

```javascript
var sayilar = [1, 2, 3, 4, 5];

var toplam = sayilar.reduce(function(onceki, simdiki) {
    return onceki + simdiki;
}, 0);
console.log(toplam); // 15
```

## 🔄 Dizi Birleştirme ve Bölme

### concat() - Birleştirme

```javascript
var dizi1 = [1, 2, 3];
var dizi2 = [4, 5, 6];
var dizi3 = dizi1.concat(dizi2);
console.log(dizi3); // [1, 2, 3, 4, 5, 6]
```

### slice() - Bölme

```javascript
var dizi = [1, 2, 3, 4, 5];

var yeniDizi = dizi.slice(1, 3);
console.log(yeniDizi); // [2, 3]
console.log(dizi); // [1, 2, 3, 4, 5] (orijinal değişmedi)
```

### join() - String'e Dönüştürme

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

var metin = isimler.join(", ");
console.log(metin); // "Bahadır, Bekdemir, JavaScript"
```

## 🔄 Dizi Sıralama

### sort() - Sıralama

```javascript
var sayilar = [3, 1, 4, 1, 5, 9, 2, 6];
sayilar.sort();
console.log(sayilar); // [1, 1, 2, 3, 4, 5, 6, 9]

// Özel sıralama
var sayilar2 = [10, 5, 40, 25, 1000, 1];
sayilar2.sort(function(a, b) {
    return a - b; // Artan sıralama
});
console.log(sayilar2); // [1, 5, 10, 25, 40, 1000]
```

### reverse() - Ters Çevirme

```javascript
var dizi = [1, 2, 3, 4, 5];
dizi.reverse();
console.log(dizi); // [5, 4, 3, 2, 1]
```

## 💡 Pratik Örnekler

### Dizi İşlemleri

```javascript
var sayilar = [1, 2, 3, 4, 5];

// Toplam
var toplam = sayilar.reduce((a, b) => a + b, 0);
console.log("Toplam: " + toplam); // 15

// Ortalama
var ortalama = toplam / sayilar.length;
console.log("Ortalama: " + ortalama); // 3

// En büyük
var enBuyuk = Math.max(...sayilar);
console.log("En büyük: " + enBuyuk); // 5

// En küçük
var enKucuk = Math.min(...sayilar);
console.log("En küçük: " + enKucuk); // 1
```

### Kullanıcı Listesi Filtreleme

```javascript
var kullanicilar = [
    {isim: "Bahadır", yas: 25, aktif: true},
    {isim: "Bekdemir", yas: 30, aktif: false},
    {isim: "JavaScript", yas: 20, aktif: true}
];

// Aktif kullanıcılar
var aktifKullanicilar = kullanicilar.filter(k => k.aktif);
console.log(aktifKullanicilar);

// 25 yaşından büyükler
var yasliKullanicilar = kullanicilar.filter(k => k.yas > 25);
console.log(yasliKullanicilar);

// İsim listesi
var isimler = kullanicilar.map(k => k.isim);
console.log(isimler); // ["Bahadır", "Bekdemir", "JavaScript"]
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


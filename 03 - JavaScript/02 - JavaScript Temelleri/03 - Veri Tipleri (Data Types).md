# 📊 VERİ TİPLERİ (DATA TYPES)

JavaScript, dinamik tipli (dynamically typed) bir dildir. Bu, değişkenlerin tipinin çalışma zamanında belirlendiği anlamına gelir. JavaScript'te temel veri tipleri ve bunların kullanımını öğreneceğiz.

## 🔢 Temel Veri Tipleri (Primitive Types)

### 1️⃣ Number (Sayı)

JavaScript'te tüm sayılar (tam sayı ve ondalıklı) `Number` tipindedir:

```javascript
// Tam sayılar
var tamSayi = 10;
var negatifSayi = -5;

// Ondalıklı sayılar
var ondalikSayi = 3.14;
var bilimselNotasyon = 1.5e6; // 1500000

// Özel değerler
var sonsuz = Infinity;
var sayiDegil = NaN; // Not a Number
```

### 2️⃣ String (Metin)

Metin verileri `String` tipinde saklanır. Tek tırnak, çift tırnak veya backtick kullanılabilir:

```javascript
// Tek tırnak
var isim1 = 'Bahadır';

// Çift tırnak
var isim2 = "Bekdemir";

// Template literal (ES6)
var tamIsim = `Bahadır Bekdemir`;
var mesaj = `Merhaba ${tamIsim}!`; // "Merhaba Bahadır Bekdemir!"

// String birleştirme
var ad = "Bahadır";
var soyad = "Bekdemir";
var tamAd = ad + " " + soyad; // "Bahadır Bekdemir"
```

### 3️⃣ Boolean (Mantıksal)

Sadece iki değer alabilir: `true` (doğru) veya `false` (yanlış):

```javascript
var aktif = true;
var pasif = false;
var yasliMi = (yas >= 18); // true veya false
```

### 4️⃣ Undefined (Tanımsız)

Değişken tanımlanmış ancak değer atanmamışsa `undefined` değerini alır:

```javascript
var degisken;
console.log(degisken); // undefined

var x = undefined; // Açıkça undefined atanabilir
```

### 5️⃣ Null (Boş)

`null`, değişkenin bilinçli olarak boş olduğunu belirtir:

```javascript
var kullanici = null; // Boş değer
console.log(kullanici); // null
```

### 6️⃣ Symbol (Sembol) - ES6

Benzersiz (unique) değerler oluşturmak için kullanılır:

```javascript
var id1 = Symbol("id");
var id2 = Symbol("id");
console.log(id1 === id2); // false (farklı semboller)
```

## 🎯 Karmaşık Veri Tipleri (Complex Types)

### 7️⃣ Object (Nesne)

Nesneler, anahtar-değer çiftlerinden oluşan veri yapılarıdır:

```javascript
// Nesne tanımlama
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

// Özelliklere erişim
console.log(kullanici.isim); // "Bahadır"
console.log(kullanici["yas"]); // 25
```

### 8️⃣ Array (Dizi)

Diziler, birden fazla değeri sıralı bir şekilde saklar:

```javascript
// Dizi tanımlama
var sayilar = [1, 2, 3, 4, 5];
var isimler = ["Bahadır", "Bekdemir"];

// Dizi elemanlarına erişim
console.log(sayilar[0]); // 1
console.log(isimler[1]); // "Bekdemir"
```

## 🔍 Veri Tipi Kontrolü

### typeof Operatörü

Değişkenin tipini öğrenmek için `typeof` operatörü kullanılır:

```javascript
typeof 10; // "number"
typeof "Bahadır"; // "string"
typeof true; // "boolean"
typeof undefined; // "undefined"
typeof null; // "object" (JavaScript hatası!)
typeof {}; // "object"
typeof []; // "object"
typeof function(){}; // "function"
```

### Örnek Kullanım

```javascript
var degisken = "Bahadır";
console.log(typeof degisken); // "string"

degisken = 25;
console.log(typeof degisken); // "number"

degisken = true;
console.log(typeof degisken); // "boolean"
```

## 🔄 Tip Dönüşümleri (Type Conversion)

### Otomatik Tip Dönüşümü (Type Coercion)

JavaScript, işlemler sırasında otomatik tip dönüşümü yapar:

```javascript
// String + Number = String
var sonuc = "5" + 3; // "53" (string)

// Number - String = Number
var sonuc2 = "10" - 5; // 5 (number)

// Boolean dönüşümü
var sonuc3 = "5" * true; // 5 (number)
```

### Manuel Tip Dönüşümü

#### String'e Dönüştürme

```javascript
var sayi = 10;
var metin = String(sayi); // "10"
var metin2 = sayi.toString(); // "10"
var metin3 = sayi + ""; // "10"
```

#### Number'a Dönüştürme

```javascript
var metin = "10";
var sayi = Number(metin); // 10
var sayi2 = parseInt(metin); // 10 (tam sayı)
var sayi3 = parseFloat("3.14"); // 3.14 (ondalıklı)
var sayi4 = +metin; // 10 (kısa yazım)
```

#### Boolean'a Dönüştürme

```javascript
var deger = 1;
var bool = Boolean(deger); // true
var bool2 = !!deger; // true (kısa yazım)

// Falsy değerler (false'a dönüşür)
Boolean(0); // false
Boolean(""); // false
Boolean(null); // false
Boolean(undefined); // false
Boolean(NaN); // false
```

## 📋 Truthy ve Falsy Değerler

### Falsy Değerler (false'a dönüşen)

```javascript
// Bu değerler false olarak değerlendirilir
false
0
-0
0n (BigInt)
"" (boş string)
null
undefined
NaN
```

### Truthy Değerler (true'a dönüşen)

```javascript
// Diğer tüm değerler true olarak değerlendirilir
true
1
-1
"0"
"false"
[] (boş dizi)
{} (boş nesne)
function(){} (fonksiyon)
```

## 💡 Örnekler

### Tip Kontrolü ve Dönüşüm

```javascript
// Kullanıcı girişi (her zaman string gelir)
var yasGirisi = "25";
var yas = Number(yasGirisi);

if (typeof yas === "number" && !isNaN(yas)) {
    console.log("Yaş: " + yas);
} else {
    console.log("Geçersiz yaş!");
}
```

### Nesne ve Dizi Kontrolü

```javascript
// Dizi kontrolü
var arr = [1, 2, 3];
console.log(Array.isArray(arr)); // true
console.log(typeof arr); // "object"

// Nesne kontrolü
var obj = {isim: "Bahadır"};
console.log(typeof obj); // "object"
console.log(obj !== null && typeof obj === "object" && !Array.isArray(obj)); // true
```

## ⚠️ Yaygın Hatalar

### null ve undefined Karışıklığı

```javascript
var x;
console.log(x); // undefined (tanımlanmamış)

var y = null;
console.log(y); // null (bilinçli olarak boş)

// Kontrol
if (x === undefined) {
    console.log("x tanımsız");
}

if (y === null) {
    console.log("y boş");
}
```

### NaN Kontrolü

```javascript
var sonuc = "abc" * 5; // NaN

// NaN kontrolü
if (isNaN(sonuc)) {
    console.log("Geçersiz işlem!");
}

// NaN kendisiyle eşit değildir!
console.log(NaN === NaN); // false
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


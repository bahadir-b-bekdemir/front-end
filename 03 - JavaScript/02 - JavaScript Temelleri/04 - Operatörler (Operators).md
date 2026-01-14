# ⚙️ OPERATÖRLER (OPERATORS)

Operatörler, değişkenler ve değerler üzerinde işlem yapmak için kullanılan sembollerdir. JavaScript'te birçok farklı operatör türü bulunmaktadır.

## 🔢 Aritmetik Operatörler

Matematiksel işlemler için kullanılır:

```javascript
var a = 10;
var b = 3;

// Toplama
var toplam = a + b; // 13

// Çıkarma
var fark = a - b; // 7

// Çarpma
var carpim = a * b; // 30

// Bölme
var bolum = a / b; // 3.333...

// Mod (Kalan)
var kalan = a % b; // 1

// Üs alma
var us = a ** b; // 1000 (10^3)

// Artırma
a++; // a = 11
++a; // a = 12

// Azaltma
b--; // b = 2
--b; // b = 1
```

## 🔗 Atama Operatörleri

Değişkenlere değer atamak için kullanılır:

```javascript
var x = 10;

// Basit atama
x = 5;

// Toplama ile atama
x += 5; // x = x + 5 (10)

// Çıkarma ile atama
x -= 3; // x = x - 3 (7)

// Çarpma ile atama
x *= 2; // x = x * 2 (14)

// Bölme ile atama
x /= 2; // x = x / 2 (7)

// Mod ile atama
x %= 3; // x = x % 3 (1)

// Üs ile atama
x **= 2; // x = x ** 2 (1)
```

## 🔀 Karşılaştırma Operatörleri

İki değeri karşılaştırmak için kullanılır (boolean değer döner):

```javascript
var a = 5;
var b = 10;

// Eşit mi?
a == b; // false (değer karşılaştırması)
a === b; // false (değer ve tip karşılaştırması)

// Eşit değil mi?
a != b; // true
a !== b; // true

// Büyüktür
a > b; // false

// Küçüktür
a < b; // true

// Büyük veya eşit
a >= b; // false

// Küçük veya eşit
a <= b; // true
```

### ⚠️ == vs === Farkı

```javascript
// == (Loose Equality) - Tip dönüşümü yapar
5 == "5"; // true
0 == false; // true
null == undefined; // true

// === (Strict Equality) - Tip kontrolü yapar
5 === "5"; // false
0 === false; // false
null === undefined; // false
```

## 🔀 Mantıksal Operatörler

Mantıksal işlemler için kullanılır:

```javascript
var x = 5;
var y = 10;

// VE (AND) - &&
(x < 10 && y > 5); // true (her ikisi de true)

// VEYA (OR) - ||
(x > 10 || y < 5); // false (her ikisi de false)

// DEĞİL (NOT) - !
!(x > 10); // true
```

### 🔍 Kısa Devre Değerlendirme (Short-Circuit)

```javascript
// && operatörü - İlk false değeri döner
var sonuc1 = false && "Merhaba"; // false
var sonuc2 = true && "Merhaba"; // "Merhaba"

// || operatörü - İlk true değeri döner
var sonuc3 = false || "Merhaba"; // "Merhaba"
var sonuc4 = true || "Merhaba"; // true
```

## 🎯 Koşul (Ternary) Operatörü

Kısa if-else yapısı:

```javascript
var yas = 18;
var durum = (yas >= 18) ? "Reşit" : "Reşit değil";
// "Reşit"

// İç içe kullanım
var not = 85;
var harf = (not >= 90) ? "A" : 
           (not >= 80) ? "B" : 
           (not >= 70) ? "C" : "F";
```

## 🔍 Tip Operatörleri

### typeof

Değişkenin tipini öğrenmek için:

```javascript
typeof 10; // "number"
typeof "Bahadır"; // "string"
typeof true; // "boolean"
typeof {}; // "object"
typeof []; // "object"
typeof function(){}; // "function"
```

### instanceof

Nesnenin belirli bir türden olup olmadığını kontrol eder:

```javascript
var arr = [1, 2, 3];
arr instanceof Array; // true

var obj = {};
obj instanceof Object; // true
```

## 🔗 String Operatörleri

### Birleştirme (+)

```javascript
var isim = "Bahadır";
var soyisim = "Bekdemir";
var tamIsim = isim + " " + soyisim; // "Bahadır Bekdemir"

// Template Literal (ES6)
var mesaj = `Merhaba ${isim}!`; // "Merhaba Bahadır!"
```

## 🔢 Bitwise (Bit Düzeyi) Operatörler

Bit seviyesinde işlemler yapar:

```javascript
var a = 5;  // 0101 (binary)
var b = 3;  // 0011 (binary)

// AND
a & b; // 1 (0001)

// OR
a | b; // 7 (0111)

// XOR
a ^ b; // 6 (0110)

// NOT
~a; // -6

// Left shift
a << 1; // 10 (1010)

// Right shift
a >> 1; // 2 (0010)
```

## 📊 Operatör Önceliği (Precedence)

Operatörlerin işlem sırası:

```javascript
// Çarpma, bölme önce yapılır
var sonuc = 2 + 3 * 4; // 14 (3*4=12, 12+2=14)

// Parantez önceliği değiştirir
var sonuc2 = (2 + 3) * 4; // 20 (5*4=20)

// Öncelik sırası (yüksekten düşüğe)
// 1. () (parantez)
// 2. ** (üs)
// 3. *, /, % (çarpma, bölme, mod)
// 4. +, - (toplama, çıkarma)
// 5. <, <=, >, >= (karşılaştırma)
// 6. ==, !=, ===, !== (eşitlik)
// 7. && (VE)
// 8. || (VEYA)
// 9. = (atama)
```

## 💡 Örnekler

### Kullanıcı Yaş Kontrolü

```javascript
var yas = 20;
var durum = (yas >= 18) ? "Reşit" : "Reşit değil";
console.log(durum); // "Reşit"
```

### Matematiksel Hesaplama

```javascript
var fiyat = 100;
var kdv = 0.18;
var kdvliFiyat = fiyat + (fiyat * kdv);
console.log(kdvliFiyat); // 118
```

### Mantıksal Kontrol

```javascript
var kullaniciAdi = "Bahadır";
var sifre = "12345";
var girisYapildi = (kullaniciAdi === "Bahadır" && sifre === "12345");
console.log(girisYapildi); // true
```

### String Birleştirme

```javascript
var ad = "Bahadır";
var soyad = "Bekdemir";
var email = ad.toLowerCase() + "." + soyad.toLowerCase() + "@email.com";
console.log(email); // "bahadır.bekdemir@email.com"
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


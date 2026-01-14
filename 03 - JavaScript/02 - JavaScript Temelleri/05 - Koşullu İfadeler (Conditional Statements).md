# 🔀 KOŞULLU İFADELER (CONDITIONAL STATEMENTS)

Koşullu ifadeler, programın akışını belirli koşullara göre yönlendirmek için kullanılır. JavaScript'te `if`, `else if`, `else` ve `switch` yapıları bulunmaktadır.

## 🎯 if İfadesi

En temel koşullu ifade yapısıdır:

```javascript
var yas = 18;

if (yas >= 18) {
    console.log("Reşit");
}
```

## 🔀 if...else İfadesi

İki seçenekli koşul yapısı:

```javascript
var yas = 15;

if (yas >= 18) {
    console.log("Reşit");
} else {
    console.log("Reşit değil");
}
```

## 🔀 if...else if...else İfadesi

Birden fazla koşul kontrolü:

```javascript
var not = 85;

if (not >= 90) {
    console.log("A");
} else if (not >= 80) {
    console.log("B");
} else if (not >= 70) {
    console.log("C");
} else if (not >= 60) {
    console.log("D");
} else {
    console.log("F");
}
```

## 📋 Çoklu Koşullar

### && (VE) Operatörü

```javascript
var yas = 25;
var ehliyet = true;

if (yas >= 18 && ehliyet) {
    console.log("Araba kullanabilir");
} else {
    console.log("Araba kullanamaz");
}
```

### || (VEYA) Operatörü

```javascript
var hava = "güneşli";
var sıcaklık = 25;

if (hava === "güneşli" || sıcaklık > 20) {
    console.log("Dışarı çıkılabilir");
}
```

### ! (DEĞİL) Operatörü

```javascript
var aktif = false;

if (!aktif) {
    console.log("Kullanıcı pasif");
}
```

## 🔄 switch İfadesi

Çoklu seçim yapısı:

```javascript
var gun = "Pazartesi";

switch (gun) {
    case "Pazartesi":
        console.log("Haftanın ilk günü");
        break;
    case "Salı":
        console.log("Haftanın ikinci günü");
        break;
    case "Çarşamba":
        console.log("Haftanın üçüncü günü");
        break;
    default:
        console.log("Diğer günler");
}
```

### ⚠️ break Kullanımı

`break` kullanılmazsa, bir sonraki case'e de geçer (fall-through):

```javascript
var sayi = 1;

switch (sayi) {
    case 1:
        console.log("Bir");
        // break yok!
    case 2:
        console.log("İki");
        break;
    case 3:
        console.log("Üç");
        break;
}
// Çıktı: "Bir" ve "İki" (fall-through)
```

### Çoklu Case Değerleri

```javascript
var ay = 2;

switch (ay) {
    case 12:
    case 1:
    case 2:
        console.log("Kış");
        break;
    case 3:
    case 4:
    case 5:
        console.log("İlkbahar");
        break;
    case 6:
    case 7:
    case 8:
        console.log("Yaz");
        break;
    case 9:
    case 10:
    case 11:
        console.log("Sonbahar");
        break;
}
```

## 🎯 Ternary (Üçlü) Operatör

Kısa if-else yapısı:

```javascript
var yas = 18;
var durum = (yas >= 18) ? "Reşit" : "Reşit değil";
console.log(durum); // "Reşit"

// İç içe kullanım
var not = 85;
var harf = (not >= 90) ? "A" : 
           (not >= 80) ? "B" : 
           (not >= 70) ? "C" : "F";
console.log(harf); // "B"
```

## 🔍 Truthy ve Falsy Kontrolleri

JavaScript'te bazı değerler otomatik olarak `false` olarak değerlendirilir:

```javascript
var deger = "";

// Falsy değerler: false, 0, "", null, undefined, NaN
if (deger) {
    console.log("Değer var");
} else {
    console.log("Değer yok");
}

// Açık kontrol
if (deger !== null && deger !== undefined) {
    console.log("Değer tanımlı");
}
```

## 💡 Pratik Örnekler

### Kullanıcı Giriş Kontrolü

```javascript
var kullaniciAdi = "Bahadır";
var sifre = "12345";

if (kullaniciAdi === "Bahadır" && sifre === "12345") {
    console.log("Giriş başarılı");
} else {
    console.log("Kullanıcı adı veya şifre hatalı");
}
```

### Yaş Grupları

```javascript
var yas = 25;

if (yas < 13) {
    console.log("Çocuk");
} else if (yas < 20) {
    console.log("Genç");
} else if (yas < 65) {
    console.log("Yetişkin");
} else {
    console.log("Yaşlı");
}
```

### Hava Durumu

```javascript
var hava = "yağmurlu";
var sıcaklık = 15;

if (hava === "güneşli" && sıcaklık > 20) {
    console.log("Plaja gidilebilir");
} else if (hava === "yağmurlu") {
    console.log("Şemsiye alınmalı");
} else if (sıcaklık < 10) {
    console.log("Sıcak giyinilmeli");
} else {
    console.log("Normal kıyafetler yeterli");
}
```

### Not Hesaplama

```javascript
var not = 85;

switch (true) {
    case not >= 90:
        console.log("Mükemmel!");
        break;
    case not >= 80:
        console.log("Çok iyi!");
        break;
    case not >= 70:
        console.log("İyi");
        break;
    case not >= 60:
        console.log("Orta");
        break;
    default:
        console.log("Yetersiz");
}
```

### Dizi Kontrolü

```javascript
var dizi = [1, 2, 3];

if (Array.isArray(dizi) && dizi.length > 0) {
    console.log("Dizi dolu");
} else {
    console.log("Dizi boş veya dizi değil");
}
```

## ⚠️ Yaygın Hatalar

### = vs == vs ===

```javascript
var x = 5;

// HATA! Atama operatörü kullanıldı
if (x = 10) { // x'e 10 atanır ve her zaman true döner
    console.log("Her zaman çalışır");
}

// DOĞRU - Karşılaştırma
if (x == 10) { // Değer karşılaştırması
    console.log("Çalışır");
}

if (x === 10) { // Değer ve tip karşılaştırması (önerilen)
    console.log("Çalışır");
}
```

### Null ve Undefined Kontrolü

```javascript
var deger = null;

// Yanlış kontrol
if (deger == null) { // null ve undefined için true döner
    console.log("Null veya undefined");
}

// Doğru kontrol
if (deger === null) { // Sadece null için true
    console.log("Null");
}

if (deger === undefined) { // Sadece undefined için true
    console.log("Undefined");
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


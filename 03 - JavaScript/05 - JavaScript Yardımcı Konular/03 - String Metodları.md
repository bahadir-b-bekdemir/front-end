# 📝 STRING METODLARI

JavaScript'te string'ler üzerinde işlem yapmak için birçok yerleşik metod bulunmaktadır.

## 🔍 Arama Metodları

### indexOf() - İndeks Bulma

```javascript
var metin = "JavaScript öğreniyorum";

var indeks = metin.indexOf("öğreniyorum");
console.log(indeks); // 12

var bulunamadi = metin.indexOf("Python");
console.log(bulunamadi); // -1 (bulunamadı)
```

### lastIndexOf() - Son İndeks

```javascript
var metin = "JavaScript ve JavaScript";

var sonIndeks = metin.lastIndexOf("JavaScript");
console.log(sonIndeks); // 15
```

### includes() - İçeriyor mu?

```javascript
var metin = "JavaScript öğreniyorum";

console.log(metin.includes("JavaScript")); // true
console.log(metin.includes("Python")); // false
```

### startsWith() - Başlıyor mu?

```javascript
var metin = "JavaScript öğreniyorum";

console.log(metin.startsWith("JavaScript")); // true
console.log(metin.startsWith("Python")); // false
```

### endsWith() - Bitiyor mu?

```javascript
var metin = "JavaScript öğreniyorum";

console.log(metin.endsWith("öğreniyorum")); // true
console.log(metin.endsWith("Python")); // false
```

## ✂️ Bölme ve Birleştirme

### slice() - Parça Alma

```javascript
var metin = "JavaScript";

var parca = metin.slice(0, 4);
console.log(parca); // "Java"

var parca2 = metin.slice(4);
console.log(parca2); // "Script"

var parca3 = metin.slice(-6); // Sondan
console.log(parca3); // "Script"
```

### substring() - Alt String

```javascript
var metin = "JavaScript";

var alt = metin.substring(0, 4);
console.log(alt); // "Java"

var alt2 = metin.substring(4);
console.log(alt2); // "Script"
```

### substr() - Alt String (Deprecated)

```javascript
var metin = "JavaScript";

var alt = metin.substr(0, 4); // İndeks, uzunluk
console.log(alt); // "Java"
```

### split() - Bölme

```javascript
var metin = "Bahadır,Bekdemir,JavaScript";

var parcalar = metin.split(",");
console.log(parcalar); // ["Bahadır", "Bekdemir", "JavaScript"]

var kelimeler = "JavaScript öğreniyorum".split(" ");
console.log(kelimeler); // ["JavaScript", "öğreniyorum"]
```

### concat() - Birleştirme

```javascript
var metin1 = "Merhaba";
var metin2 = "Dünya";

var birlesik = metin1.concat(" ", metin2);
console.log(birlesik); // "Merhaba Dünya"

// + operatörü daha yaygın
var birlesik2 = metin1 + " " + metin2;
```

### join() - Diziyi Birleştirme

```javascript
var kelimeler = ["Merhaba", "Dünya", "JavaScript"];

var metin = kelimeler.join(" ");
console.log(metin); // "Merhaba Dünya JavaScript"

var metin2 = kelimeler.join("-");
console.log(metin2); // "Merhaba-Dünya-JavaScript"
```

## 🔄 Değiştirme Metodları

### replace() - Değiştirme

```javascript
var metin = "JavaScript öğreniyorum";

var yeni = metin.replace("JavaScript", "Python");
console.log(yeni); // "Python öğreniyorum"

// Sadece ilk eşleşmeyi değiştirir
var metin2 = "JavaScript ve JavaScript";
var yeni2 = metin2.replace("JavaScript", "Python");
console.log(yeni2); // "Python ve JavaScript"
```

### replaceAll() - Tümünü Değiştirme

```javascript
var metin = "JavaScript ve JavaScript";

var yeni = metin.replaceAll("JavaScript", "Python");
console.log(yeni); // "Python ve Python"
```

### toUpperCase() - Büyük Harf

```javascript
var metin = "javascript";

var buyuk = metin.toUpperCase();
console.log(buyuk); // "JAVASCRIPT"
```

### toLowerCase() - Küçük Harf

```javascript
var metin = "JAVASCRIPT";

var kucuk = metin.toLowerCase();
console.log(kucuk); // "javascript"
```

### trim() - Boşluk Temizleme

```javascript
var metin = "  JavaScript  ";

var temiz = metin.trim();
console.log(temiz); // "JavaScript"

// trimStart() - Baştan
var bas = metin.trimStart();
console.log(bas); // "JavaScript  "

// trimEnd() - Sondan
var son = metin.trimEnd();
console.log(son); // "  JavaScript"
```

## 📏 Uzunluk ve Karakter

### length - Uzunluk

```javascript
var metin = "JavaScript";

console.log(metin.length); // 10
```

### charAt() - Karakter Alma

```javascript
var metin = "JavaScript";

var karakter = metin.charAt(0);
console.log(karakter); // "J"

// Köşeli parantez notasyonu
var karakter2 = metin[0];
console.log(karakter2); // "J"
```

### charCodeAt() - Karakter Kodu

```javascript
var metin = "JavaScript";

var kod = metin.charCodeAt(0);
console.log(kod); // 74 (J'nin ASCII kodu)
```

## 🔄 Dönüşüm Metodları

### toString() - String'e Dönüştürme

```javascript
var sayi = 123;

var metin = sayi.toString();
console.log(metin); // "123"
console.log(typeof metin); // "string"
```

### String() - String Constructor

```javascript
var sayi = 123;

var metin = String(sayi);
console.log(metin); // "123"
```

## 💡 Pratik Örnekler

### Email Doğrulama

```javascript
function emailGecerliMi(email) {
    return email.includes("@") && 
           email.includes(".") && 
           email.indexOf("@") < email.lastIndexOf(".");
}

console.log(emailGecerliMi("bahadir@email.com")); // true
console.log(emailGecerliMi("gecersiz")); // false
```

### İlk Harfi Büyük Yapma

```javascript
function ilkHarfBuyuk(metin) {
    return metin.charAt(0).toUpperCase() + metin.slice(1).toLowerCase();
}

console.log(ilkHarfBuyuk("javascript")); // "Javascript"
console.log(ilkHarfBuyuk("BAHADIR")); // "Bahadır"
```

### Kelime Sayısı

```javascript
function kelimeSayisi(metin) {
    return metin.trim().split(/\s+/).length;
}

console.log(kelimeSayisi("JavaScript öğreniyorum")); // 2
console.log(kelimeSayisi("  Çok   boşluklu   metin  ")); // 3
```

### URL'den Parametre Çıkarma

```javascript
function urlParametresi(url, parametre) {
    var urlObj = new URL(url);
    return urlObj.searchParams.get(parametre);
}

var url = "https://example.com?isim=Bahadır&yas=25";
console.log(urlParametresi(url, "isim")); // "Bahadır"
console.log(urlParametresi(url, "yas")); // "25"
```

### Metin Ters Çevirme

```javascript
function metinTers(metin) {
    return metin.split("").reverse().join("");
}

console.log(metinTers("JavaScript")); // "tpircSavaJ"
```

### Palindrom Kontrolü

```javascript
function palindromMu(metin) {
    var temiz = metin.toLowerCase().replace(/\s/g, "");
    var ters = temiz.split("").reverse().join("");
    return temiz === ters;
}

console.log(palindromMu("kayak")); // true
console.log(palindromMu("JavaScript")); // false
```

### Metin Kısaltma

```javascript
function metinKisalt(metin, uzunluk) {
    if (metin.length <= uzunluk) {
        return metin;
    }
    return metin.slice(0, uzunluk) + "...";
}

console.log(metinKisalt("JavaScript öğreniyorum", 10)); // "JavaScript..."
```

### Başlık Formatı

```javascript
function baslikFormatla(metin) {
    var kelimeler = metin.toLowerCase().split(" ");
    return kelimeler.map(function(kelime) {
        return kelime.charAt(0).toUpperCase() + kelime.slice(1);
    }).join(" ");
}

console.log(baslikFormatla("javascript öğreniyorum")); // "Javascript Öğreniyorum"
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🔢 DEĞİŞKENLER (VARIABLES)

Değişkenler, verileri saklamak için kullanılan isimlendirilmiş bellek alanlarıdır. JavaScript'te değişkenler, `var`, `let` veya `const` anahtar kelimeleri ile tanımlanır.

## 📦 Değişken Tanımlama

### 🔵 var (ES5 - Eski Yöntem)

`var` anahtar kelimesi, JavaScript'in eski versiyonlarında kullanılan değişken tanımlama yöntemidir:

```javascript
// Değişken tanımlama
var isim = "Bahadır";
var yas = 25;
var aktif = true;

// Değişken değeri değiştirme
var sayi = 10;
sayi = 20; // Değer değiştirildi
```

### 🟢 let (ES6 - Modern Yöntem)

`let` anahtar kelimesi, ES6 ile gelen modern değişken tanımlama yöntemidir:

```javascript
// Değişken tanımlama
let isim = "Bahadır";
let yas = 25;
let aktif = true;

// Değişken değeri değiştirme
let sayi = 10;
sayi = 20; // Değer değiştirildi
```

### 🟡 const (Sabit Değerler)

`const` anahtar kelimesi, değeri değiştirilemeyen sabit değişkenler için kullanılır:

```javascript
// Sabit değişken tanımlama
const PI = 3.14;
const SITE_ADI = "JavaScript Eğitimi";

// Hata! const değişkenlerin değeri değiştirilemez
// PI = 3.14159; // Hata verir
```

## 🔍 var vs let vs const

### 📊 Karşılaştırma Tablosu

| Özellik | var | let | const |
|---------|-----|-----|-------|
| Yeniden tanımlanabilir | ✅ | ❌ | ❌ |
| Değer değiştirilebilir | ✅ | ✅ | ❌ |
| Block scope | ❌ | ✅ | ✅ |
| Function scope | ✅ | ✅ | ✅ |
| Hoisting | ✅ | ⚠️ | ⚠️ |

### 🎯 Scope (Kapsam) Farkları

```javascript
// var - Function scope
function ornek1() {
    if (true) {
        var x = 10;
    }
    console.log(x); // 10 (erişilebilir)
}

// let - Block scope
function ornek2() {
    if (true) {
        let y = 10;
    }
    console.log(y); // Hata! (erişilemez)
}

// const - Block scope
function ornek3() {
    if (true) {
        const z = 10;
    }
    console.log(z); // Hata! (erişilemez)
}
```

## 🔄 Değişken Değer Atama

### 📝 Tekil Atama

```javascript
var isim = "Bahadır";
var yas = 25;
var aktif = true;
```

### 📝 Çoklu Atama

```javascript
// Aynı değeri birden fazla değişkene atama
var x, y, z;
x = y = z = 10;

console.log(x); // 10
console.log(y); // 10
console.log(z); // 10
```

### 📝 Değişken Değiştirme

```javascript
let sayi = 5;
console.log(sayi); // 5

sayi = 10;
console.log(sayi); // 10

sayi = sayi + 5;
console.log(sayi); // 15
```

## 🏷️ Değişken İsimlendirme Kuralları

### ✅ İyi İsimlendirme Örnekleri

```javascript
// Açıklayıcı isimler
var kullaniciAdi = "Bahadır";
var kullaniciYasi = 25;
var aktifKullanici = true;
var toplamUrunSayisi = 100;

// Camel case (önerilen)
var firstName = "Bahadır";
var lastName = "Bekdemir";
var isActive = true;
```

### ❌ Kötü İsimlendirme Örnekleri

```javascript
// Belirsiz isimler
var x = "Bahadır";
var y = 25;
var z = true;

// Kısaltmalar (anlaşılması zor)
var usrNm = "Bahadır";
var usrAg = 25;
```

## 📊 Değişken Türleri

### 🔢 Sayısal Değişkenler

```javascript
var tamSayi = 10;
var ondalikSayi = 3.14;
var negatifSayi = -5;
```

### 📝 Metin (String) Değişkenler

```javascript
var isim = "Bahadır";
var soyisim = 'Bekdemir';
var tamIsim = `Bahadır Bekdemir`; // Template literal
```

### ✅ Boolean Değişkenler

```javascript
var aktif = true;
var pasif = false;
```

### 📦 Dizi (Array) Değişkenler

```javascript
var sayilar = [1, 2, 3, 4, 5];
var isimler = ["Bahadır", "Bekdemir"];
```

### 🎯 Nesne (Object) Değişkenler

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};
```

## 🔄 Değişken Değiştirme Örnekleri

```javascript
// Sayısal işlemler
var sayi = 10;
sayi = sayi + 5; // 15
sayi += 5; // 20 (kısa yazım)
sayi++; // 21 (1 artırma)

// Metin birleştirme
var isim = "Bahadır";
var soyisim = "Bekdemir";
var tamIsim = isim + " " + soyisim; // "Bahadır Bekdemir"
```

## ⚠️ Yaygın Hatalar

### 🚫 Tanımlanmamış Değişken Kullanımı

```javascript
// Hata! Değişken tanımlanmadan kullanılamaz
console.log(degisken); // ReferenceError

// Doğru kullanım
var degisken = "Değer";
console.log(degisken); // "Değer"
```

### 🚫 const Değişken Değer Değiştirme

```javascript
const PI = 3.14;
PI = 3.14159; // TypeError: Assignment to constant variable
```

### 🚫 let/const Yeniden Tanımlama

```javascript
let x = 10;
let x = 20; // SyntaxError: Identifier 'x' has already been declared
```

## 💡 Best Practices (En İyi Uygulamalar)

1. **Modern Syntax Kullanın:** `var` yerine `let` veya `const` kullanın
2. **Açıklayıcı İsimler:** Değişken isimleri ne yaptığını açıklamalı
3. **Camel Case:** Değişken isimleri için camelCase kullanın
4. **const Tercih Edin:** Değeri değişmeyecek değişkenler için `const` kullanın
5. **Başlangıç Değeri:** Değişkenleri tanımlarken başlangıç değeri verin

```javascript
// ✅ İyi örnek
const MAX_SAYI = 100;
let kullaniciSayisi = 0;
const kullaniciAdi = "Bahadır";

// ❌ Kötü örnek
var x = 10;
var y;
var z = null;
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📝 JAVASCRIPT SYNTAX VE KOD YAPISI

JavaScript, belirli kurallar ve yapılara sahip bir programlama dilidir. Bu bölümde JavaScript'in temel syntax (sözdizimi) kurallarını ve kod yapısını öğreneceğiz.

## 🔤 Temel Syntax Kuralları

### 📄 Kod Satırları

JavaScript kodları satır satır yazılır ve her satır genellikle bir komut içerir:

```javascript
// Tek satırlık kod
console.log("Merhaba Dünya");

// Birden fazla satır
var x = 5;
var y = 10;
var toplam = x + y;
```

### 🔢 Noktalı Virgül (Semicolon)

JavaScript'te her komutun sonuna noktalı virgül (`;`) konulabilir. Zorunlu değildir ancak önerilir:

```javascript
// Noktalı virgül ile
var isim = "Bahadır";
console.log(isim);

// Noktalı virgül olmadan (otomatik eklenir)
var soyisim = "Bekdemir"
console.log(soyisim)
```

### 💬 Yorum Satırları

JavaScript'te iki tür yorum satırı vardır:

```javascript
// Tek satırlık yorum

/* 
   Çok satırlık yorum
   Bu şekilde birden fazla satır yorum yapılabilir
*/
```

## 📦 Kod Blokları

Kod blokları, süslü parantezler `{}` ile tanımlanır:

```javascript
// Fonksiyon bloğu
function merhaba() {
    console.log("Merhaba");
    console.log("Dünya");
}

// Koşul bloğu
if (x > 5) {
    console.log("x 5'ten büyük");
}
```

## 🏷️ İsimlendirme Kuralları (Naming Conventions)

### ✅ Geçerli İsimler

- Harf, rakam, alt çizgi (`_`) ve dolar işareti (`$`) içerebilir
- Rakamla başlayamaz
- Büyük/kücük harf duyarlıdır (case-sensitive)

```javascript
// Geçerli isimler
var isim = "Bahadır";
var _soyisim = "Bekdemir";
var $degisken = 10;
var degisken1 = 20;
var Degisken = 30; // farklı bir değişken
```

### ❌ Geçersiz İsimler

```javascript
// Geçersiz isimler
var 1degisken = 10; // Rakamla başlayamaz
var degisken-isim = 20; // Tire içeremez
var var = 30; // Rezerve kelime kullanılamaz
```

## 🔑 Rezerve Kelimeler (Reserved Words)

JavaScript'te özel anlamları olan ve değişken ismi olarak kullanılamayan kelimeler:

```javascript
// Bu kelimeler değişken ismi olarak kullanılamaz
break, case, catch, class, const, continue, debugger, default,
delete, do, else, export, extends, finally, for, function, if,
import, in, instanceof, new, return, super, switch, this, throw,
try, typeof, var, void, while, with, yield
```

## 📐 Girintileme (Indentation)

JavaScript'te girintileme zorunlu değildir ancak kodun okunabilirliği için önemlidir:

```javascript
// İyi girintileme
function ornek() {
    if (x > 5) {
        console.log("x büyük");
        if (x > 10) {
            console.log("x çok büyük");
        }
    }
}

// Kötü girintileme (çalışır ama okunması zor)
function ornek() {
if (x > 5) {
console.log("x büyük");
if (x > 10) {
console.log("x çok büyük");
}
}
}
```

## 🎯 JavaScript Dosyasına Kod Ekleme

### 📄 HTML İçinde Satır İçi (Inline)

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Örneği</title>
</head>
<body>
    <button onclick="alert('Merhaba!')">Tıkla</button>
</body>
</html>
```

### 📄 HTML İçinde Script Etiketi

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Örneği</title>
    <script>
        console.log("Sayfa yüklendi");
    </script>
</head>
<body>
    <h1>Merhaba Dünya</h1>
</body>
</html>
```

### 📄 Harici JavaScript Dosyası

**index.html:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Örneği</title>
    <script src="script.js"></script>
</head>
<body>
    <h1>Merhaba Dünya</h1>
</body>
</html>
```

**script.js:**
```javascript
console.log("Harici dosyadan yüklendi");
```

## 🔍 Case Sensitivity (Büyük/Küçük Harf Duyarlılığı)

JavaScript büyük/küçük harf duyarlıdır:

```javascript
var isim = "Bahadır";
var Isim = "Bekdemir"; // Farklı değişken
var ISIM = "Test"; // Farklı değişken

console.log(isim); // "Bahadır"
console.log(Isim); // "Bekdemir"
console.log(ISIM); // "Test"
```

## 📊 Örnek: Temel Kod Yapısı

```javascript
// Değişken tanımlama
var kullaniciAdi = "Bahadır";
var yas = 25;

// Fonksiyon tanımlama
function kullaniciBilgisi() {
    console.log("Kullanıcı: " + kullaniciAdi);
    console.log("Yaş: " + yas);
}

// Fonksiyon çağırma
kullaniciBilgisi();

// Koşullu ifade
if (yas >= 18) {
    console.log("Reşit");
} else {
    console.log("Reşit değil");
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


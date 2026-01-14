# 🔧 FONKSİYONLAR (FUNCTIONS)

Fonksiyonlar, belirli bir görevi yerine getirmek için yazılan yeniden kullanılabilir kod bloklarıdır. JavaScript'te fonksiyonlar birinci sınıf vatandaşlardır (first-class citizens).

## 📝 Fonksiyon Tanımlama

### 🔵 Function Declaration (Fonksiyon Bildirimi)

```javascript
// Fonksiyon tanımlama
function merhaba() {
    console.log("Merhaba Dünya!");
}

// Fonksiyon çağırma
merhaba(); // "Merhaba Dünya!"
```

### 🔵 Parametreli Fonksiyon

```javascript
function selamla(isim) {
    console.log("Merhaba " + isim + "!");
}

selamla("Bahadır"); // "Merhaba Bahadır!"
```

### 🔵 Çoklu Parametreli Fonksiyon

```javascript
function topla(a, b) {
    return a + b;
}

var sonuc = topla(5, 3);
console.log(sonuc); // 8
```

### 🔵 Return İfadesi

```javascript
function carp(a, b) {
    return a * b;
}

var sonuc = carp(4, 5);
console.log(sonuc); // 20
```

## 📝 Function Expression (Fonksiyon İfadesi)

Fonksiyonu bir değişkene atama:

```javascript
// Anonim fonksiyon
var topla = function(a, b) {
    return a + b;
};

console.log(topla(3, 4)); // 7

// İsimli fonksiyon ifadesi
var carp = function carpma(a, b) {
    return a * b;
};
```

## 📝 Arrow Function (Ok Fonksiyonu) - ES6

Kısa ve modern fonksiyon yazımı:

```javascript
// Tek parametre
var selamla = (isim) => {
    return "Merhaba " + isim;
};

// Tek satır (return otomatik)
var selamla2 = (isim) => "Merhaba " + isim;

// Çoklu parametre
var topla = (a, b) => a + b;

// Parametresiz
var merhaba = () => "Merhaba Dünya!";
```

## 📝 Default Parameters (Varsayılan Parametreler) - ES6

```javascript
function selamla(isim = "Misafir") {
    console.log("Merhaba " + isim);
}

selamla("Bahadır"); // "Merhaba Bahadır"
selamla(); // "Merhaba Misafir"
```

## 📝 Rest Parameters (Kalan Parametreler) - ES6

Sınırsız sayıda parametre almak için:

```javascript
function topla(...sayilar) {
    var toplam = 0;
    for (var sayi of sayilar) {
        toplam += sayi;
    }
    return toplam;
}

console.log(topla(1, 2, 3)); // 6
console.log(topla(1, 2, 3, 4, 5)); // 15
```

## 📝 Arguments Objesi

Fonksiyona gönderilen tüm argümanlara erişim:

```javascript
function topla() {
    var toplam = 0;
    for (var i = 0; i < arguments.length; i++) {
        toplam += arguments[i];
    }
    return toplam;
}

console.log(topla(1, 2, 3)); // 6
```

## 🔄 Fonksiyon Çağırma Yöntemleri

### Normal Çağırma

```javascript
function merhaba() {
    console.log("Merhaba");
}
merhaba();
```

### Method Çağırma

```javascript
var kullanici = {
    isim: "Bahadır",
    selamla: function() {
        console.log("Merhaba " + this.isim);
    }
};
kullanici.selamla(); // "Merhaba Bahadır"
```

### Constructor Çağırma

```javascript
function Kullanici(isim) {
    this.isim = isim;
}
var kullanici = new Kullanici("Bahadır");
```

### call, apply, bind

```javascript
function selamla(soyisim) {
    console.log("Merhaba " + this.isim + " " + soyisim);
}

var kullanici = {isim: "Bahadır"};

// call - Parametreler ayrı ayrı
selamla.call(kullanici, "Bekdemir"); // "Merhaba Bahadır Bekdemir"

// apply - Parametreler dizi olarak
selamla.apply(kullanici, ["Bekdemir"]); // "Merhaba Bahadır Bekdemir"

// bind - Yeni fonksiyon döner
var bagliFonksiyon = selamla.bind(kullanici);
bagliFonksiyon("Bekdemir"); // "Merhaba Bahadır Bekdemir"
```

## 🔄 İç İçe Fonksiyonlar

```javascript
function disFonksiyon() {
    var x = 10;
    
    function icFonksiyon() {
        console.log(x); // 10 (closure)
    }
    
    icFonksiyon();
}

disFonksiyon();
```

## 🔄 Closure (Kapanış)

Fonksiyon, dış kapsamdaki değişkenlere erişebilir:

```javascript
function disFonksiyon() {
    var x = 10;
    
    return function icFonksiyon() {
        console.log(x); // 10
    };
}

var fonksiyon = disFonksiyon();
fonksiyon(); // 10
```

## 🔄 Recursive Functions (Özyinelemeli Fonksiyonlar)

Kendini çağıran fonksiyonlar:

```javascript
function faktoriyel(n) {
    if (n <= 1) {
        return 1;
    }
    return n * faktoriyel(n - 1);
}

console.log(faktoriyel(5)); // 120
```

## 💡 Pratik Örnekler

### Hesap Makinesi Fonksiyonları

```javascript
function topla(a, b) {
    return a + b;
}

function cikar(a, b) {
    return a - b;
}

function carp(a, b) {
    return a * b;
}

function bol(a, b) {
    if (b === 0) {
        return "Sıfıra bölünemez!";
    }
    return a / b;
}

console.log(topla(10, 5)); // 15
console.log(cikar(10, 5)); // 5
console.log(carp(10, 5)); // 50
console.log(bol(10, 5)); // 2
```

### Kullanıcı Bilgisi

```javascript
function kullaniciBilgisi(isim, yas, aktif = true) {
    return {
        isim: isim,
        yas: yas,
        aktif: aktif,
        bilgi: function() {
            return this.isim + " (" + this.yas + " yaşında) - " + 
                   (this.aktif ? "Aktif" : "Pasif");
        }
    };
}

var kullanici = kullaniciBilgisi("Bahadır", 25);
console.log(kullanici.bilgi()); // "Bahadır (25 yaşında) - Aktif"
```

### Dizi İşlemleri

```javascript
function diziTopla(sayilar) {
    var toplam = 0;
    for (var sayi of sayilar) {
        toplam += sayi;
    }
    return toplam;
}

function diziOrtalama(sayilar) {
    if (sayilar.length === 0) return 0;
    return diziTopla(sayilar) / sayilar.length;
}

var sayilar = [1, 2, 3, 4, 5];
console.log(diziTopla(sayilar)); // 15
console.log(diziOrtalama(sayilar)); // 3
```

### Callback Fonksiyonlar

```javascript
function islemYap(sayilar, callback) {
    var sonuc = [];
    for (var sayi of sayilar) {
        sonuc.push(callback(sayi));
    }
    return sonuc;
}

var sayilar = [1, 2, 3, 4, 5];

// Kare alma
var kareler = islemYap(sayilar, function(x) {
    return x * x;
});
console.log(kareler); // [1, 4, 9, 16, 25]

// İki katına çıkarma
var ikiKati = islemYap(sayilar, (x) => x * 2);
console.log(ikiKati); // [2, 4, 6, 8, 10]
```

## ⚠️ Yaygın Hatalar

### Return Kullanmama

```javascript
// HATA - Return yok
function topla(a, b) {
    a + b; // Sonuç döndürülmüyor
}

// DOĞRU
function topla(a, b) {
    return a + b;
}
```

### Hoisting Farkı

```javascript
// Function Declaration - Hoisting var
merhaba(); // Çalışır (hoisting)

function merhaba() {
    console.log("Merhaba");
}

// Function Expression - Hoisting yok
selamla(); // Hata! (hoisting yok)

var selamla = function() {
    console.log("Selamla");
};
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


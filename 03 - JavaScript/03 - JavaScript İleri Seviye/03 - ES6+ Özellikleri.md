# ⚡ ES6+ ÖZELLİKLERİ

ES6 (ECMAScript 2015) ve sonrası, JavaScript'e birçok yeni özellik ekledi. Bu bölümde modern JavaScript özelliklerini öğreneceğiz.

## 🔄 Destructuring (Yapısal Ayrıştırma)

### Dizi Destructuring

```javascript
// Dizi elemanlarını değişkenlere atama
var sayilar = [1, 2, 3];
var [a, b, c] = sayilar;
console.log(a, b, c); // 1 2 3

// Atlama
var [x, , z] = sayilar;
console.log(x, z); // 1 3

// Varsayılan değer
var [ilk, ikinci = 10] = [1];
console.log(ilk, ikinci); // 1 10

// Kalan elemanlar
var [birinci, ...kalan] = [1, 2, 3, 4, 5];
console.log(birinci); // 1
console.log(kalan); // [2, 3, 4, 5]
```

### Nesne Destructuring

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    email: "bahadir@email.com"
};

// Özellikleri değişkenlere atama
var {isim, yas} = kullanici;
console.log(isim, yas); // "Bahadır" 25

// Farklı isimle atama
var {isim: ad, yas: yil} = kullanici;
console.log(ad, yil); // "Bahadır" 25

// Varsayılan değer
var {isim, aktif = true} = kullanici;
console.log(aktif); // true

// İç içe nesneler
var kullanici2 = {
    isim: "Bahadır",
    adres: {
        sehir: "İstanbul",
        ilce: "Kadıköy"
    }
};
var {adres: {sehir}} = kullanici2;
console.log(sehir); // "İstanbul"
```

### Fonksiyon Parametrelerinde Destructuring

```javascript
// Dizi parametresi
function topla([a, b]) {
    return a + b;
}
console.log(topla([5, 3])); // 8

// Nesne parametresi
function kullaniciBilgisi({isim, yas}) {
    return isim + " (" + yas + " yaşında)";
}
var kullanici = {isim: "Bahadır", yas: 25};
console.log(kullaniciBilgisi(kullanici)); // "Bahadır (25 yaşında)"
```

## 🔄 Spread Operator (Yayma Operatörü)

### Dizilerde Spread

```javascript
// Dizi birleştirme
var dizi1 = [1, 2, 3];
var dizi2 = [4, 5, 6];
var birlesik = [...dizi1, ...dizi2];
console.log(birlesik); // [1, 2, 3, 4, 5, 6]

// Dizi kopyalama
var orijinal = [1, 2, 3];
var kopya = [...orijinal];
kopya.push(4);
console.log(orijinal); // [1, 2, 3] (değişmedi)
console.log(kopya); // [1, 2, 3, 4]

// Fonksiyon parametrelerine geçirme
var sayilar = [1, 2, 3];
console.log(Math.max(...sayilar)); // 3
```

### Nesnelerde Spread

```javascript
// Nesne birleştirme
var kullanici = {isim: "Bahadır", yas: 25};
var ekBilgi = {email: "bahadir@email.com", aktif: true};
var tamBilgi = {...kullanici, ...ekBilgi};
console.log(tamBilgi);
// {isim: "Bahadır", yas: 25, email: "bahadir@email.com", aktif: true}

// Nesne kopyalama
var orijinal = {isim: "Bahadır", yas: 25};
var kopya = {...orijinal};
kopya.yas = 26;
console.log(orijinal.yas); // 25 (değişmedi)
console.log(kopya.yas); // 26
```

## 📝 Template Literals (Şablon Değişmezleri)

### Temel Kullanım

```javascript
var isim = "Bahadır";
var yas = 25;

// Eski yöntem
var mesaj = "Merhaba " + isim + ", yaşınız " + yas;

// Template literal
var mesaj2 = `Merhaba ${isim}, yaşınız ${yas}`;
console.log(mesaj2); // "Merhaba Bahadır, yaşınız 25"
```

### Çok Satırlı String

```javascript
// Eski yöntem
var metin = "Satır 1\n" +
            "Satır 2\n" +
            "Satır 3";

// Template literal
var metin2 = `Satır 1
Satır 2
Satır 3`;
```

### İfadeler İçinde

```javascript
var a = 10;
var b = 5;

var sonuc = `${a} + ${b} = ${a + b}`;
console.log(sonuc); // "10 + 5 = 15"
```

## 🔄 Rest Parameters (Kalan Parametreler)

```javascript
// Sınırsız parametre
function topla(...sayilar) {
    return sayilar.reduce((toplam, sayi) => toplam + sayi, 0);
}

console.log(topla(1, 2, 3)); // 6
console.log(topla(1, 2, 3, 4, 5)); // 15
```

## 🔄 Default Parameters (Varsayılan Parametreler)

```javascript
function selamla(isim = "Misafir", yas = 0) {
    return `Merhaba ${isim}, yaşınız ${yas}`;
}

console.log(selamla("Bahadır", 25)); // "Merhaba Bahadır, yaşınız 25"
console.log(selamla()); // "Merhaba Misafir, yaşınız 0"
console.log(selamla("Bahadır")); // "Merhaba Bahadır, yaşınız 0"
```

## 🔄 Arrow Functions (Ok Fonksiyonları)

### Temel Kullanım

```javascript
// Normal fonksiyon
var topla = function(a, b) {
    return a + b;
};

// Arrow function
var topla2 = (a, b) => a + b;

// Tek parametre (parantez opsiyonel)
var kare = x => x * x;

// Parametresiz
var merhaba = () => "Merhaba Dünya";

// Çok satırlı
var carp = (a, b) => {
    var sonuc = a * b;
    return sonuc;
};
```

### this Bağlamı

```javascript
var kullanici = {
    isim: "Bahadır",
    normalFonksiyon: function() {
        console.log(this.isim); // "Bahadır"
    },
    arrowFonksiyon: () => {
        console.log(this.isim); // undefined (this window'u gösterir)
    }
};
```

## 🔄 Enhanced Object Literals

```javascript
var isim = "Bahadır";
var yas = 25;

// Eski yöntem
var kullanici = {
    isim: isim,
    yas: yas,
    selamla: function() {
        return "Merhaba " + this.isim;
    }
};

// ES6 yöntemi
var kullanici2 = {
    isim, // isim: isim kısa yazımı
    yas,  // yas: yas kısa yazımı
    selamla() { // Method kısa yazımı
        return `Merhaba ${this.isim}`;
    }
};
```

## 🔄 for...of Döngüsü

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

// Eski yöntem
for (var i = 0; i < isimler.length; i++) {
    console.log(isimler[i]);
}

// for...of
for (var isim of isimler) {
    console.log(isim);
}

// String'ler için
var metin = "JavaScript";
for (var harf of metin) {
    console.log(harf);
}
```

## 🔄 Array Methods (ES6+)

### find() - Bulma

```javascript
var sayilar = [1, 2, 3, 4, 5];
var bulunan = sayilar.find(x => x > 3);
console.log(bulunan); // 4
```

### findIndex() - İndeks Bulma

```javascript
var sayilar = [1, 2, 3, 4, 5];
var indeks = sayilar.findIndex(x => x > 3);
console.log(indeks); // 3
```

### includes() - İçeriyor mu?

```javascript
var sayilar = [1, 2, 3, 4, 5];
console.log(sayilar.includes(3)); // true
console.log(sayilar.includes(6)); // false
```

## 💡 Pratik Örnekler

### Fonksiyon Parametrelerinde Destructuring

```javascript
function kullaniciEkle({isim, yas, email = "yok"}) {
    console.log(`${isim} (${yas}) - ${email}`);
}

kullaniciEkle({isim: "Bahadır", yas: 25});
// "Bahadır (25) - yok"
```

### Dizi Birleştirme ve Kopyalama

```javascript
var dizi1 = [1, 2, 3];
var dizi2 = [4, 5, 6];
var yeniDizi = [...dizi1, ...dizi2, 7, 8];
console.log(yeniDizi); // [1, 2, 3, 4, 5, 6, 7, 8]
```

### Nesne Güncelleme

```javascript
var kullanici = {isim: "Bahadır", yas: 25};
var guncellenmis = {...kullanici, yas: 26, aktif: true};
console.log(guncellenmis);
// {isim: "Bahadır", yas: 26, aktif: true}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🎯 NESNELER (OBJECTS)

Nesneler, JavaScript'te verileri organize etmek için kullanılan temel veri yapılarıdır. Anahtar-değer (key-value) çiftlerinden oluşurlar.

## 📦 Nesne Oluşturma

### 🔵 Object Literal (Nesne Değişmez)

```javascript
// Boş nesne
var kullanici = {};

// Özellikli nesne
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};
```

### 🔵 new Object()

```javascript
var kullanici = new Object();
kullanici.isim = "Bahadır";
kullanici.yas = 25;
kullanici.aktif = true;
```

### 🔵 Constructor Function

```javascript
function Kullanici(isim, yas) {
    this.isim = isim;
    this.yas = yas;
    this.aktif = true;
}

var kullanici = new Kullanici("Bahadır", 25);
```

## 🔍 Nesne Özelliklerine Erişim

### Nokta Notasyonu

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25
};

console.log(kullanici.isim); // "Bahadır"
console.log(kullanici.yas); // 25
```

### Köşeli Parantez Notasyonu

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25
};

console.log(kullanici["isim"]); // "Bahadır"
console.log(kullanici["yas"]); // 25

// Değişken ile erişim
var ozellik = "isim";
console.log(kullanici[ozellik]); // "Bahadır"
```

## ✏️ Nesne Özelliklerini Değiştirme

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25
};

// Özellik değiştirme
kullanici.yas = 26;
kullanici["isim"] = "Bekdemir";

// Yeni özellik ekleme
kullanici.email = "bahadir@email.com";
kullanici["aktif"] = true;
```

## 🗑️ Nesne Özelliklerini Silme

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

// Özellik silme
delete kullanici.aktif;
delete kullanici["yas"];

console.log(kullanici); // {isim: "Bahadır"}
```

## 🔄 Nesne Metodları

Nesneler içinde fonksiyonlar (metodlar) tanımlanabilir:

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    selamla: function() {
        return "Merhaba " + this.isim;
    },
    yasArtir: function() {
        this.yas++;
    }
};

console.log(kullanici.selamla()); // "Merhaba Bahadır"
kullanici.yasArtir();
console.log(kullanici.yas); // 26
```

## 🔄 this Anahtar Kelimesi

`this`, nesnenin kendisini referans eder:

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    bilgi: function() {
        return this.isim + " (" + this.yas + " yaşında)";
    }
};

console.log(kullanici.bilgi()); // "Bahadır (25 yaşında)"
```

## 🔍 Nesne Dolaşma

### for...in Döngüsü

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

for (var ozellik in kullanici) {
    console.log(ozellik + ": " + kullanici[ozellik]);
}
// Çıktı:
// isim: Bahadır
// yas: 25
// aktif: true
```

### Object.keys()

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

var ozellikler = Object.keys(kullanici);
console.log(ozellikler); // ["isim", "yas", "aktif"]

ozellikler.forEach(function(ozellik) {
    console.log(ozellik + ": " + kullanici[ozellik]);
});
```

### Object.values()

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

var degerler = Object.values(kullanici);
console.log(degerler); // ["Bahadır", 25, true]
```

## 🔄 Nesne Kopyalama

### Shallow Copy (Sığ Kopya)

```javascript
var kullanici1 = {
    isim: "Bahadır",
    yas: 25
};

// Object.assign() ile kopyalama
var kullanici2 = Object.assign({}, kullanici1);

// Spread operator ile (ES6)
var kullanici3 = {...kullanici1};

kullanici2.isim = "Bekdemir";
console.log(kullanici1.isim); // "Bahadır" (değişmedi)
console.log(kullanici2.isim); // "Bekdemir"
```

## 🔄 Nesne Birleştirme

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25
};

var ekBilgi = {
    email: "bahadir@email.com",
    aktif: true
};

// Object.assign() ile birleştirme
var tamBilgi = Object.assign({}, kullanici, ekBilgi);

// Spread operator ile (ES6)
var tamBilgi2 = {...kullanici, ...ekBilgi};

console.log(tamBilgi);
// {isim: "Bahadır", yas: 25, email: "bahadir@email.com", aktif: true}
```

## 🔍 Nesne Kontrolü

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25
};

// Özellik var mı?
console.log("isim" in kullanici); // true
console.log("email" in kullanici); // false

// hasOwnProperty() metodu
console.log(kullanici.hasOwnProperty("isim")); // true
console.log(kullanici.hasOwnProperty("toString")); // false
```

## 💡 Pratik Örnekler

### Kullanıcı Yönetimi

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    email: "bahadir@email.com",
    aktif: true,
    girisYap: function() {
        this.aktif = true;
        console.log(this.isim + " giriş yaptı");
    },
    cikisYap: function() {
        this.aktif = false;
        console.log(this.isim + " çıkış yaptı");
    },
    bilgi: function() {
        return this.isim + " (" + this.yas + ") - " + 
               (this.aktif ? "Aktif" : "Pasif");
    }
};

console.log(kullanici.bilgi()); // "Bahadır (25) - Aktif"
kullanici.cikisYap(); // "Bahadır çıkış yaptı"
console.log(kullanici.bilgi()); // "Bahadır (25) - Pasif"
```

### İç İçe Nesneler

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    adres: {
        sehir: "İstanbul",
        ilce: "Kadıköy",
        sokak: "Bağdat Caddesi"
    },
    telefonlar: [
        {tip: "ev", numara: "0212-123-4567"},
        {tip: "cep", numara: "0532-123-4567"}
    ]
};

console.log(kullanici.adres.sehir); // "İstanbul"
console.log(kullanici.telefonlar[0].numara); // "0212-123-4567"
```

### Nesne Metodları ile Hesaplama

```javascript
var hesap = {
    bakiye: 1000,
    paraYatir: function(miktar) {
        this.bakiye += miktar;
        return "Yeni bakiye: " + this.bakiye;
    },
    paraCek: function(miktar) {
        if (miktar <= this.bakiye) {
            this.bakiye -= miktar;
            return "Yeni bakiye: " + this.bakiye;
        } else {
            return "Yetersiz bakiye!";
        }
    },
    bakiyeGoster: function() {
        return "Mevcut bakiye: " + this.bakiye;
    }
};

console.log(hesap.bakiyeGoster()); // "Mevcut bakiye: 1000"
console.log(hesap.paraYatir(500)); // "Yeni bakiye: 1500"
console.log(hesap.paraCek(200)); // "Yeni bakiye: 1300"
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


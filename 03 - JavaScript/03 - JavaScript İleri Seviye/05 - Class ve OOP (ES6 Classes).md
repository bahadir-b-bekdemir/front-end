# 🏗️ CLASS VE OOP (ES6 CLASSES)

ES6 ile JavaScript'e class (sınıf) yapısı eklendi. Bu, nesne yönelimli programlamayı daha kolay hale getirir.

## 📦 Class Tanımlama

### Temel Class

```javascript
class Kullanici {
    constructor(isim, yas) {
        this.isim = isim;
        this.yas = yas;
    }
    
    selamla() {
        return "Merhaba " + this.isim;
    }
    
    bilgi() {
        return this.isim + " (" + this.yas + " yaşında)";
    }
}

// Kullanım
var kullanici = new Kullanici("Bahadır", 25);
console.log(kullanici.selamla()); // "Merhaba Bahadır"
console.log(kullanici.bilgi()); // "Bahadır (25 yaşında)"
```

## 🔄 Constructor (Yapıcı)

Constructor, class'tan nesne oluşturulduğunda çalışır:

```javascript
class Kullanici {
    constructor(isim, yas, email) {
        this.isim = isim;
        this.yas = yas;
        this.email = email;
        this.aktif = true;
        this.olusturulmaTarihi = new Date();
    }
}

var kullanici = new Kullanici("Bahadır", 25, "bahadir@email.com");
console.log(kullanici.aktif); // true
```

## 🔄 Metodlar

### Instance Metodlar

```javascript
class Kullanici {
    constructor(isim, yas) {
        this.isim = isim;
        this.yas = yas;
    }
    
    selamla() {
        return "Merhaba " + this.isim;
    }
    
    yasArtir() {
        this.yas++;
    }
    
    bilgi() {
        return this.isim + " (" + this.yas + " yaşında)";
    }
}

var kullanici = new Kullanici("Bahadır", 25);
kullanici.yasArtir();
console.log(kullanici.bilgi()); // "Bahadır (26 yaşında)"
```

### Static Metodlar

```javascript
class Matematik {
    static topla(a, b) {
        return a + b;
    }
    
    static carp(a, b) {
        return a * b;
    }
}

// Static metodlar class üzerinden çağrılır
console.log(Matematik.topla(5, 3)); // 8
console.log(Matematik.carp(4, 5)); // 20
```

### Getter ve Setter

```javascript
class Kullanici {
    constructor(isim, yas) {
        this._isim = isim;
        this._yas = yas;
    }
    
    get isim() {
        return this._isim.toUpperCase();
    }
    
    set isim(yeniIsim) {
        if (yeniIsim.length < 3) {
            throw new Error("İsim en az 3 karakter olmalı");
        }
        this._isim = yeniIsim;
    }
    
    get yas() {
        return this._yas;
    }
    
    set yas(yeniYas) {
        if (yeniYas < 0) {
            throw new Error("Yaş negatif olamaz");
        }
        this._yas = yeniYas;
    }
}

var kullanici = new Kullanici("Bahadır", 25);
console.log(kullanici.isim); // "BAHADIR" (getter)
kullanici.yas = 26; // setter
console.log(kullanici.yas); // 26
```

## 🔄 Inheritance (Kalıtım)

### extends - Sınıf Genişletme

```javascript
class Kullanici {
    constructor(isim, yas) {
        this.isim = isim;
        this.yas = yas;
    }
    
    selamla() {
        return "Merhaba " + this.isim;
    }
}

class Admin extends Kullanici {
    constructor(isim, yas, yetki) {
        super(isim, yas); // Üst sınıf constructor'ını çağır
        this.yetki = yetki;
    }
    
    yonetimPaneli() {
        return this.isim + " yönetim paneline erişebilir";
    }
    
    // Metod override (üzerine yazma)
    selamla() {
        return "Merhaba Admin " + this.isim;
    }
}

var admin = new Admin("Bahadır", 25, "tam");
console.log(admin.selamla()); // "Merhaba Admin Bahadır"
console.log(admin.yonetimPaneli()); // "Bahadır yönetim paneline erişebilir"
```

### super - Üst Sınıfa Erişim

```javascript
class Hayvan {
    constructor(isim) {
        this.isim = isim;
    }
    
    konus() {
        return this.isim + " ses çıkarıyor";
    }
}

class Kedi extends Hayvan {
    constructor(isim, renk) {
        super(isim);
        this.renk = renk;
    }
    
    konus() {
        return super.konus() + " - Miyav!";
    }
}

var kedi = new Kedi("Pamuk", "beyaz");
console.log(kedi.konus()); // "Pamuk ses çıkarıyor - Miyav!"
```

## 💡 Pratik Örnekler

### Hesap Yönetimi

```javascript
class Hesap {
    constructor(bakiye = 0) {
        this.bakiye = bakiye;
        this.islemGecmisi = [];
    }
    
    paraYatir(miktar) {
        if (miktar <= 0) {
            throw new Error("Miktar pozitif olmalı");
        }
        this.bakiye += miktar;
        this.islemGecmisi.push({tip: "yatırma", miktar: miktar, tarih: new Date()});
        return this.bakiye;
    }
    
    paraCek(miktar) {
        if (miktar <= 0) {
            throw new Error("Miktar pozitif olmalı");
        }
        if (miktar > this.bakiye) {
            throw new Error("Yetersiz bakiye");
        }
        this.bakiye -= miktar;
        this.islemGecmisi.push({tip: "çekme", miktar: miktar, tarih: new Date()});
        return this.bakiye;
    }
    
    bakiyeGoster() {
        return "Mevcut bakiye: " + this.bakiye;
    }
}

var hesap = new Hesap(1000);
hesap.paraYatir(500);
hesap.paraCek(200);
console.log(hesap.bakiyeGoster()); // "Mevcut bakiye: 1300"
```

### Ürün Yönetimi

```javascript
class Urun {
    constructor(isim, fiyat, stok) {
        this.isim = isim;
        this.fiyat = fiyat;
        this.stok = stok;
    }
    
    stokGuncelle(miktar) {
        this.stok += miktar;
    }
    
    fiyatGuncelle(yeniFiyat) {
        if (yeniFiyat < 0) {
            throw new Error("Fiyat negatif olamaz");
        }
        this.fiyat = yeniFiyat;
    }
    
    bilgi() {
        return this.isim + " - " + this.fiyat + " TL (Stok: " + this.stok + ")";
    }
}

class IndirimliUrun extends Urun {
    constructor(isim, fiyat, stok, indirimOrani) {
        super(isim, fiyat, stok);
        this.indirimOrani = indirimOrani;
    }
    
    get indirimliFiyat() {
        return this.fiyat * (1 - this.indirimOrani / 100);
    }
    
    bilgi() {
        return super.bilgi() + " (İndirimli: " + this.indirimliFiyat.toFixed(2) + " TL)";
    }
}

var urun = new Urun("Laptop", 10000, 5);
var indirimli = new IndirimliUrun("Telefon", 5000, 10, 20);
console.log(urun.bilgi());
console.log(indirimli.bilgi());
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


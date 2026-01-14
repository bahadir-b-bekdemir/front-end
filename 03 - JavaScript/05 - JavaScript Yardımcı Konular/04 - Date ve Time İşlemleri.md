# 📅 DATE VE TIME İŞLEMLERİ

JavaScript'te tarih ve saat işlemleri için `Date` nesnesi kullanılır.

## 📅 Date Oluşturma

### Şu Anki Tarih ve Saat

```javascript
var simdi = new Date();
console.log(simdi); // Şu anki tarih ve saat
```

### Belirli Tarih

```javascript
// Yıl, ay, gün
var tarih1 = new Date(2023, 0, 15); // 15 Ocak 2023
// Not: Ay 0'dan başlar (0=Ocak, 11=Aralık)

// Yıl, ay, gün, saat, dakika, saniye
var tarih2 = new Date(2023, 0, 15, 14, 30, 0); // 15 Ocak 2023, 14:30:00

// String ile
var tarih3 = new Date("2023-01-15");
var tarih4 = new Date("January 15, 2023");

// Timestamp (milisaniye)
var tarih5 = new Date(1673808000000);
```

## 📊 Tarih Bilgilerini Alma

### Get Metodları

```javascript
var tarih = new Date();

// Yıl
console.log(tarih.getFullYear()); // 2023

// Ay (0-11)
console.log(tarih.getMonth()); // 0-11

// Gün (1-31)
console.log(tarih.getDate()); // 1-31

// Haftanın günü (0=Pazar, 6=Cumartesi)
console.log(tarih.getDay()); // 0-6

// Saat (0-23)
console.log(tarih.getHours()); // 0-23

// Dakika (0-59)
console.log(tarih.getMinutes()); // 0-59

// Saniye (0-59)
console.log(tarih.getSeconds()); // 0-59

// Milisaniye (0-999)
console.log(tarih.getMilliseconds()); // 0-999

// Timestamp (milisaniye)
console.log(tarih.getTime()); // 1673808000000
```

### UTC Metodları

```javascript
var tarih = new Date();

console.log(tarih.getUTCFullYear());
console.log(tarih.getUTCMonth());
console.log(tarih.getUTCDate());
console.log(tarih.getUTCHours());
```

## ✏️ Tarih Bilgilerini Değiştirme

### Set Metodları

```javascript
var tarih = new Date();

// Yıl değiştirme
tarih.setFullYear(2024);

// Ay değiştirme
tarih.setMonth(5); // Haziran (0'dan başlar)

// Gün değiştirme
tarih.setDate(20);

// Saat değiştirme
tarih.setHours(15);

// Dakika değiştirme
tarih.setMinutes(30);

// Saniye değiştirme
tarih.setSeconds(0);
```

## 🔄 Tarih Formatlama

### toString() - String'e Dönüştürme

```javascript
var tarih = new Date();

console.log(tarih.toString());
// "Mon Jan 15 2023 14:30:00 GMT+0300"

console.log(tarih.toDateString());
// "Mon Jan 15 2023"

console.log(tarih.toTimeString());
// "14:30:00 GMT+0300"

console.log(tarih.toISOString());
// "2023-01-15T11:30:00.000Z"

console.log(tarih.toLocaleDateString("tr-TR"));
// "15.01.2023"

console.log(tarih.toLocaleTimeString("tr-TR"));
// "14:30:00"
```

### Özel Formatlama

```javascript
function tarihFormatla(tarih) {
    var gun = tarih.getDate();
    var ay = tarih.getMonth() + 1;
    var yil = tarih.getFullYear();
    
    // Tek haneli gün/ay için 0 ekle
    gun = gun < 10 ? "0" + gun : gun;
    ay = ay < 10 ? "0" + ay : ay;
    
    return gun + "." + ay + "." + yil;
}

var tarih = new Date();
console.log(tarihFormatla(tarih)); // "15.01.2023"
```

## ⏱️ Tarih Hesaplamaları

### Tarih Farkı

```javascript
var tarih1 = new Date(2023, 0, 15);
var tarih2 = new Date(2023, 0, 20);

// Gün farkı (milisaniye)
var fark = tarih2.getTime() - tarih1.getTime();

// Gün cinsinden
var gunFarki = fark / (1000 * 60 * 60 * 24);
console.log(gunFarki); // 5
```

### Tarih Ekleme/Çıkarma

```javascript
var tarih = new Date();

// 5 gün ekle
tarih.setDate(tarih.getDate() + 5);

// 1 ay ekle
tarih.setMonth(tarih.getMonth() + 1);

// 1 yıl ekle
tarih.setFullYear(tarih.getFullYear() + 1);

// 2 saat çıkar
tarih.setHours(tarih.getHours() - 2);
```

## 💡 Pratik Örnekler

### Yaş Hesaplama

```javascript
function yasHesapla(dogumTarihi) {
    var bugun = new Date();
    var yas = bugun.getFullYear() - dogumTarihi.getFullYear();
    var ayFarki = bugun.getMonth() - dogumTarihi.getMonth();
    
    if (ayFarki < 0 || (ayFarki === 0 && bugun.getDate() < dogumTarihi.getDate())) {
        yas--;
    }
    
    return yas;
}

var dogumTarihi = new Date(1998, 0, 15);
console.log(yasHesapla(dogumTarihi)); // 25
```

### Tarih Karşılaştırma

```javascript
function tarihKarsilastir(tarih1, tarih2) {
    if (tarih1.getTime() > tarih2.getTime()) {
        return 1; // tarih1 daha büyük
    } else if (tarih1.getTime() < tarih2.getTime()) {
        return -1; // tarih2 daha büyük
    } else {
        return 0; // Eşit
    }
}

var tarih1 = new Date(2023, 0, 15);
var tarih2 = new Date(2023, 0, 20);
console.log(tarihKarsilastir(tarih1, tarih2)); // -1
```

### Zamanlayıcı (Countdown)

```javascript
function geriSayim(hedefTarih) {
    var simdi = new Date().getTime();
    var hedef = new Date(hedefTarih).getTime();
    var fark = hedef - simdi;
    
    if (fark < 0) {
        return "Süre doldu!";
    }
    
    var gun = Math.floor(fark / (1000 * 60 * 60 * 24));
    var saat = Math.floor((fark % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    var dakika = Math.floor((fark % (1000 * 60 * 60)) / (1000 * 60));
    var saniye = Math.floor((fark % (1000 * 60)) / 1000);
    
    return gun + " gün " + saat + " saat " + dakika + " dakika " + saniye + " saniye";
}

var hedef = "2024-01-01";
console.log(geriSayim(hedef));
```

### Haftanın Günü

```javascript
function haftaninGunu(tarih) {
    var gunler = ["Pazar", "Pazartesi", "Salı", "Çarşamba", "Perşembe", "Cuma", "Cumartesi"];
    return gunler[tarih.getDay()];
}

var tarih = new Date();
console.log(haftaninGunu(tarih)); // "Pazartesi"
```

### Ay Adı

```javascript
function ayAdi(tarih) {
    var aylar = ["Ocak", "Şubat", "Mart", "Nisan", "Mayıs", "Haziran",
                 "Temmuz", "Ağustos", "Eylül", "Ekim", "Kasım", "Aralık"];
    return aylar[tarih.getMonth()];
}

var tarih = new Date();
console.log(ayAdi(tarih)); // "Ocak"
```

### Tarih Aralığı

```javascript
function tarihAraligi(baslangic, bitis) {
    var tarihler = [];
    var simdi = new Date(baslangic);
    var bitisTarihi = new Date(bitis);
    
    while (simdi <= bitisTarihi) {
        tarihler.push(new Date(simdi));
        simdi.setDate(simdi.getDate() + 1);
    }
    
    return tarihler;
}

var baslangic = "2023-01-01";
var bitis = "2023-01-05";
var aralik = tarihAraligi(baslangic, bitis);
console.log(aralik.length); // 5
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


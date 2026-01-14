# 🔄 DÖNGÜLER (LOOPS)

Döngüler, belirli bir kod bloğunu tekrar tekrar çalıştırmak için kullanılır. JavaScript'te birkaç farklı döngü türü bulunmaktadır.

## 🔁 for Döngüsü

En yaygın kullanılan döngü türüdür:

```javascript
// Temel for döngüsü
for (var i = 0; i < 5; i++) {
    console.log(i); // 0, 1, 2, 3, 4
}

// Geriye doğru sayma
for (var i = 5; i > 0; i--) {
    console.log(i); // 5, 4, 3, 2, 1
}

// İkişer artırma
for (var i = 0; i < 10; i += 2) {
    console.log(i); // 0, 2, 4, 6, 8
}
```

## 🔁 for...in Döngüsü

Nesnelerin özelliklerini dolaşmak için kullanılır:

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

## 🔁 for...of Döngüsü (ES6)

Diziler ve iterable objeler için kullanılır:

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];

for (var isim of isimler) {
    console.log(isim);
}
// Çıktı:
// Bahadır
// Bekdemir
// JavaScript
```

## 🔁 while Döngüsü

Koşul doğru olduğu sürece çalışır:

```javascript
var i = 0;

while (i < 5) {
    console.log(i); // 0, 1, 2, 3, 4
    i++;
}
```

## 🔁 do...while Döngüsü

En az bir kez çalışır, sonra koşulu kontrol eder:

```javascript
var i = 0;

do {
    console.log(i); // 0, 1, 2, 3, 4
    i++;
} while (i < 5);

// En az bir kez çalışır
var j = 10;
do {
    console.log(j); // 10 (bir kez çalışır)
    j++;
} while (j < 5);
```

## 🛑 Döngü Kontrol İfadeleri

### break

Döngüyü tamamen sonlandırır:

```javascript
for (var i = 0; i < 10; i++) {
    if (i === 5) {
        break; // Döngü burada sonlanır
    }
    console.log(i); // 0, 1, 2, 3, 4
}
```

### continue

Mevcut iterasyonu atlar, döngü devam eder:

```javascript
for (var i = 0; i < 10; i++) {
    if (i === 5) {
        continue; // 5 atlanır
    }
    console.log(i); // 0, 1, 2, 3, 4, 6, 7, 8, 9
}
```

## 💡 Pratik Örnekler

### Dizi İşlemleri

```javascript
var sayilar = [1, 2, 3, 4, 5];
var toplam = 0;

// for döngüsü ile
for (var i = 0; i < sayilar.length; i++) {
    toplam += sayilar[i];
}
console.log("Toplam: " + toplam); // 15

// for...of ile
var toplam2 = 0;
for (var sayi of sayilar) {
    toplam2 += sayi;
}
console.log("Toplam: " + toplam2); // 15
```

### Nesne İşlemleri

```javascript
var kullanicilar = [
    {isim: "Bahadır", yas: 25},
    {isim: "Bekdemir", yas: 30},
    {isim: "JavaScript", yas: 28}
];

// for döngüsü ile
for (var i = 0; i < kullanicilar.length; i++) {
    console.log(kullanicilar[i].isim + " - " + kullanicilar[i].yas);
}

// for...of ile
for (var kullanici of kullanicilar) {
    console.log(kullanici.isim + " - " + kullanici.yas);
}
```

### İç İçe Döngüler

```javascript
// Çarpım tablosu
for (var i = 1; i <= 5; i++) {
    for (var j = 1; j <= 5; j++) {
        console.log(i + " x " + j + " = " + (i * j));
    }
}
```

### Koşullu Döngü

```javascript
var sayilar = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Sadece çift sayıları yazdır
for (var sayi of sayilar) {
    if (sayi % 2 === 0) {
        console.log(sayi); // 2, 4, 6, 8, 10
    }
}
```

### Döngü ile Arama

```javascript
var isimler = ["Bahadır", "Bekdemir", "JavaScript"];
var aranan = "Bekdemir";
var bulundu = false;

for (var i = 0; i < isimler.length; i++) {
    if (isimler[i] === aranan) {
        bulundu = true;
        console.log("Bulundu! İndex: " + i);
        break; // Bulunduğunda döngüden çık
    }
}

if (!bulundu) {
    console.log("Bulunamadı!");
}
```

## ⚠️ Yaygın Hatalar

### Sonsuz Döngü

```javascript
// HATA! Sonsuz döngü
var i = 0;
while (i < 5) {
    console.log(i);
    // i++ unutuldu!
}

// DOĞRU
var i = 0;
while (i < 5) {
    console.log(i);
    i++; // Artırma eklendi
}
```

### Dizi Uzunluğu Değişimi

```javascript
var sayilar = [1, 2, 3, 4, 5];

// Döngü sırasında dizi değiştirilmemeli
for (var i = 0; i < sayilar.length; i++) {
    if (sayilar[i] === 3) {
        sayilar.splice(i, 1); // Dizi değişti, döngü bozulabilir
    }
}

// Güvenli yöntem (geriye doğru)
for (var i = sayilar.length - 1; i >= 0; i--) {
    if (sayilar[i] === 3) {
        sayilar.splice(i, 1);
    }
}
```

### for...in ile Dizi Kullanımı

```javascript
var dizi = [1, 2, 3];

// for...in dizi için önerilmez (indeks döner)
for (var index in dizi) {
    console.log(index); // "0", "1", "2" (string)
}

// for...of kullanılmalı
for (var deger of dizi) {
    console.log(deger); // 1, 2, 3 (number)
}
```

## 🎯 Performans İpuçları

### Dizi Uzunluğunu Önbelleğe Alma

```javascript
var dizi = [1, 2, 3, 4, 5];

// Yavaş (her iterasyonda uzunluk hesaplanır)
for (var i = 0; i < dizi.length; i++) {
    console.log(dizi[i]);
}

// Hızlı (uzunluk önbelleğe alındı)
for (var i = 0, len = dizi.length; i < len; i++) {
    console.log(dizi[i]);
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


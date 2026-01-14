# 📄 JSON İŞLEMLERİ

JSON (JavaScript Object Notation), veri değişimi için kullanılan hafif bir veri formatıdır. JavaScript'te JSON ile çalışmak çok kolaydır.

## 📋 JSON Nedir?

JSON, JavaScript nesne gösterimine benzer bir veri formatıdır:

```json
{
    "isim": "Bahadır",
    "yas": 25,
    "aktif": true,
    "hobiler": ["okuma", "yazma", "kodlama"]
}
```

## 🔄 JSON.stringify() - JavaScript'ten JSON'a

JavaScript nesnesini JSON string'ine dönüştürür:

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true,
    hobiler: ["okuma", "yazma"]
};

var jsonString = JSON.stringify(kullanici);
console.log(jsonString);
// '{"isim":"Bahadır","yas":25,"aktif":true,"hobiler":["okuma","yazma"]}'
```

### İkinci Parametre (Replacer)

Belirli özellikleri dahil etme veya değiştirme:

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    email: "bahadir@email.com"
};

// Sadece belirli özellikleri dahil et
var json1 = JSON.stringify(kullanici, ["isim", "yas"]);
console.log(json1); // '{"isim":"Bahadır","yas":25}'

// Fonksiyon ile filtreleme
var json2 = JSON.stringify(kullanici, function(key, value) {
    if (key === "email") {
        return undefined; // email'i dahil etme
    }
    return value;
});
console.log(json2); // '{"isim":"Bahadır","yas":25}'
```

### Üçüncü Parametre (Indent)

Okunabilirlik için girinti ekleme:

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

var json = JSON.stringify(kullanici, null, 2);
console.log(json);
// {
//   "isim": "Bahadır",
//   "yas": 25,
//   "aktif": true
// }
```

## 🔄 JSON.parse() - JSON'dan JavaScript'e

JSON string'ini JavaScript nesnesine dönüştürür:

```javascript
var jsonString = '{"isim":"Bahadır","yas":25,"aktif":true}';
var kullanici = JSON.parse(jsonString);

console.log(kullanici.isim); // "Bahadır"
console.log(kullanici.yas); // 25
console.log(kullanici.aktif); // true
```

### Reviver Fonksiyonu

Değerleri dönüştürme:

```javascript
var jsonString = '{"isim":"Bahadır","yas":"25","tarih":"2023-01-01"}';

var kullanici = JSON.parse(jsonString, function(key, value) {
    if (key === "yas") {
        return parseInt(value); // String'i number'a çevir
    }
    if (key === "tarih") {
        return new Date(value); // String'i Date'e çevir
    }
    return value;
});

console.log(typeof kullanici.yas); // "number"
console.log(kullanici.tarih instanceof Date); // true
```

## 💡 Pratik Örnekler

### LocalStorage ile JSON

```javascript
// Kaydetme
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};

localStorage.setItem("kullanici", JSON.stringify(kullanici));

// Okuma
var kayitliKullanici = JSON.parse(localStorage.getItem("kullanici"));
console.log(kayitliKullanici);
```

### API Yanıtını İşleme

```javascript
// API'den gelen JSON string
var apiYaniti = '{"kullanicilar":[{"isim":"Bahadır","yas":25},{"isim":"Bekdemir","yas":30}]}';

// Parse et
var veri = JSON.parse(apiYaniti);

// Kullan
veri.kullanicilar.forEach(function(kullanici) {
    console.log(kullanici.isim + " - " + kullanici.yas);
});
```

### Derin Kopyalama

```javascript
var orijinal = {
    isim: "Bahadır",
    yas: 25,
    adres: {
        sehir: "İstanbul",
        ilce: "Kadıköy"
    }
};

// JSON ile derin kopya
var kopya = JSON.parse(JSON.stringify(orijinal));

kopya.adres.sehir = "Ankara";
console.log(orijinal.adres.sehir); // "İstanbul" (değişmedi)
console.log(kopya.adres.sehir); // "Ankara"
```

### Hata Yönetimi

```javascript
function guvenliParse(jsonString) {
    try {
        return JSON.parse(jsonString);
    } catch (hata) {
        console.error("JSON parse hatası:", hata.message);
        return null;
    }
}

var gecersizJson = '{"isim":"Bahadır"'; // Eksik kapanış
var sonuc = guvenliParse(gecersizJson); // null döner
```

### JSON Doğrulama

```javascript
function jsonGecerliMi(str) {
    try {
        JSON.parse(str);
        return true;
    } catch (e) {
        return false;
    }
}

console.log(jsonGecerliMi('{"isim":"Bahadır"}')); // true
console.log(jsonGecerliMi('{isim:"Bahadır"}')); // false
```

### İç İçe Nesneler

```javascript
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    adres: {
        sehir: "İstanbul",
        ilce: "Kadıköy",
        koordinatlar: {
            enlem: 41.0082,
            boylam: 28.9784
        }
    },
    hobiler: ["okuma", "yazma", "kodlama"]
};

var json = JSON.stringify(kullanici, null, 2);
console.log(json);

// Parse
var geriYuklenen = JSON.parse(json);
console.log(geriYuklenen.adres.koordinatlar.enlem); // 41.0082
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


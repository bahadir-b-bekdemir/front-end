# 💾 LOCALSTORAGE VE SESSIONSTORAGE

LocalStorage ve SessionStorage, tarayıcıda veri saklamak için kullanılan Web Storage API'leridir.

## 📦 LocalStorage vs SessionStorage

### LocalStorage
- Veriler tarayıcı kapatılsa bile kalır
- Farklı sekmeler arasında paylaşılır
- Manuel olarak silinene kadar kalır

### SessionStorage
- Sadece sekme açık olduğu sürece kalır
- Sekme kapatıldığında silinir
- Farklı sekmeler arasında paylaşılmaz

## 💾 LocalStorage

### setItem() - Veri Kaydetme

```javascript
// String kaydetme
localStorage.setItem("isim", "Bahadır");
localStorage.setItem("yas", "25");

// Kısa yazım
localStorage.isim = "Bahadır";
localStorage["yas"] = "25";
```

### getItem() - Veri Okuma

```javascript
// Veri okuma
var isim = localStorage.getItem("isim");
console.log(isim); // "Bahadır"

// Kısa yazım
var yas = localStorage.yas;
console.log(yas); // "25"

// Varsayılan değer
var email = localStorage.getItem("email") || "yok";
console.log(email); // "yok"
```

### removeItem() - Veri Silme

```javascript
// Tek bir öğe silme
localStorage.removeItem("isim");

// Kısa yazım
delete localStorage.yas;
```

### clear() - Tüm Verileri Silme

```javascript
// Tüm localStorage verilerini sil
localStorage.clear();
```

### key() - Anahtar Adı

```javascript
// Belirli indeksteki anahtar adı
var ilkAnahtar = localStorage.key(0);
console.log(ilkAnahtar);

// Tüm anahtarları listele
for (var i = 0; i < localStorage.length; i++) {
    var anahtar = localStorage.key(i);
    console.log(anahtar + ": " + localStorage.getItem(anahtar));
}
```

## 💾 SessionStorage

SessionStorage, LocalStorage ile aynı metodlara sahiptir:

```javascript
// Kaydetme
sessionStorage.setItem("isim", "Bahadır");

// Okuma
var isim = sessionStorage.getItem("isim");

// Silme
sessionStorage.removeItem("isim");

// Tümünü silme
sessionStorage.clear();
```

## 🔄 JSON ile Karmaşık Veriler

LocalStorage ve SessionStorage sadece string saklar. Nesneleri saklamak için JSON kullanılır:

```javascript
// Nesne kaydetme
var kullanici = {
    isim: "Bahadır",
    yas: 25,
    aktif: true
};
localStorage.setItem("kullanici", JSON.stringify(kullanici));

// Nesne okuma
var kayitliKullanici = JSON.parse(localStorage.getItem("kullanici"));
console.log(kayitliKullanici.isim); // "Bahadır"
```

## 💡 Pratik Örnekler

### Kullanıcı Tercihleri

```javascript
// Tercihleri kaydet
var tercihler = {
    tema: "koyu",
    dil: "tr",
    bildirimler: true
};
localStorage.setItem("tercihler", JSON.stringify(tercihler));

// Tercihleri yükle
function tercihleriYukle() {
    var kayitli = localStorage.getItem("tercihler");
    if (kayitli) {
        return JSON.parse(kayitli);
    }
    return {
        tema: "açık",
        dil: "tr",
        bildirimler: false
    };
}

var tercihler = tercihleriYukle();
console.log(tercihler.tema); // "koyu" veya varsayılan "açık"
```

### Alışveriş Sepeti

```javascript
// Sepete ekle
function sepeteEkle(urun) {
    var sepet = JSON.parse(localStorage.getItem("sepet") || "[]");
    sepet.push(urun);
    localStorage.setItem("sepet", JSON.stringify(sepet));
}

// Sepeti göster
function sepetiGoster() {
    var sepet = JSON.parse(localStorage.getItem("sepet") || "[]");
    console.log("Sepet:", sepet);
    return sepet;
}

// Sepetten çıkar
function sepettenCikar(urunId) {
    var sepet = JSON.parse(localStorage.getItem("sepet") || "[]");
    sepet = sepet.filter(function(urun) {
        return urun.id !== urunId;
    });
    localStorage.setItem("sepet", JSON.stringify(sepet));
}

// Sepeti temizle
function sepetiTemizle() {
    localStorage.removeItem("sepet");
}

// Kullanım
sepeteEkle({id: 1, isim: "Ürün 1", fiyat: 100});
sepeteEkle({id: 2, isim: "Ürün 2", fiyat: 200});
sepetiGoster();
```

### Form Verilerini Kaydetme

```javascript
// Form verilerini kaydet
function formKaydet(formId) {
    var form = document.getElementById(formId);
    var formData = new FormData(form);
    var veri = {};
    
    for (var [key, value] of formData.entries()) {
        veri[key] = value;
    }
    
    localStorage.setItem("formVerisi", JSON.stringify(veri));
}

// Form verilerini yükle
function formYukle(formId) {
    var kayitli = localStorage.getItem("formVerisi");
    if (kayitli) {
        var veri = JSON.parse(kayitli);
        var form = document.getElementById(formId);
        
        for (var key in veri) {
            var input = form.querySelector("[name='" + key + "']");
            if (input) {
                input.value = veri[key];
            }
        }
    }
}
```

### Ziyaret Sayacı

```javascript
// Ziyaret sayısını artır
function ziyaretSayisiArtir() {
    var sayi = parseInt(localStorage.getItem("ziyaretSayisi") || "0");
    sayi++;
    localStorage.setItem("ziyaretSayisi", sayi.toString());
    return sayi;
}

// Ziyaret sayısını göster
function ziyaretSayisiGoster() {
    var sayi = parseInt(localStorage.getItem("ziyaretSayisi") || "0");
    console.log("Ziyaret sayısı: " + sayi);
    return sayi;
}

// İlk ziyaret kontrolü
function ilkZiyaretMi() {
    return !localStorage.getItem("ziyaretSayisi");
}

if (ilkZiyaretMi()) {
    console.log("Hoş geldiniz! İlk ziyaretiniz.");
} else {
    console.log("Tekrar hoş geldiniz!");
}
ziyaretSayisiArtir();
```

### Storage Event (Farklı Sekmeler)

```javascript
// Storage değişikliklerini dinle
window.addEventListener("storage", function(event) {
    console.log("Anahtar:", event.key);
    console.log("Eski değer:", event.oldValue);
    console.log("Yeni değer:", event.newValue);
    console.log("URL:", event.url);
    
    // Veri güncellemesi
    if (event.key === "kullanici") {
        var yeniKullanici = JSON.parse(event.newValue);
        console.log("Kullanıcı güncellendi:", yeniKullanici);
    }
});
```

### Veri Kontrolü ve Temizleme

```javascript
// Tüm localStorage verilerini listele
function tumVerileriListele() {
    var veriler = {};
    for (var i = 0; i < localStorage.length; i++) {
        var anahtar = localStorage.key(i);
        var deger = localStorage.getItem(anahtar);
        veriler[anahtar] = deger;
    }
    return veriler;
}

// Belirli bir ön ekle başlayanları sil
function onEkIleSil(onEk) {
    var silinecekler = [];
    for (var i = 0; i < localStorage.length; i++) {
        var anahtar = localStorage.key(i);
        if (anahtar.startsWith(onEk)) {
            silinecekler.push(anahtar);
        }
    }
    silinecekler.forEach(function(anahtar) {
        localStorage.removeItem(anahtar);
    });
}

// Kullanım
onEkIleSil("temp_"); // "temp_" ile başlayan tüm verileri sil
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


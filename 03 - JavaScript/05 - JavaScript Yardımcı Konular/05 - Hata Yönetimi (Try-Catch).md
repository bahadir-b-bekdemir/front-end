# ⚠️ HATA YÖNETİMİ (TRY-CATCH)

Hata yönetimi, program çalışırken oluşabilecek hataları yakalayıp kontrol etmek için kullanılır.

## 🔄 Try-Catch-Finally

### Temel Kullanım

```javascript
try {
    // Hata oluşturabilecek kod
    var sonuc = 10 / 0;
    console.log(sonuc);
} catch (hata) {
    // Hata yakalandığında çalışır
    console.error("Hata oluştu:", hata.message);
} finally {
    // Her zaman çalışır (hata olsun ya da olmasın)
    console.log("İşlem tamamlandı");
}
```

### Hata Türleri

```javascript
try {
    // ReferenceError
    console.log(tanimlanmamisDegisken);
    
    // TypeError
    var x = null;
    x.property;
    
    // SyntaxError (parse zamanı yakalanır)
    eval("var x = ;");
    
} catch (hata) {
    console.log("Hata türü:", hata.name);
    console.log("Hata mesajı:", hata.message);
    console.log("Stack trace:", hata.stack);
}
```

## 🚨 Throw - Hata Fırlatma

### Manuel Hata Oluşturma

```javascript
function yasKontrol(yas) {
    if (yas < 0) {
        throw new Error("Yaş negatif olamaz!");
    }
    if (yas > 150) {
        throw new Error("Yaş çok büyük!");
    }
    return "Yaş geçerli: " + yas;
}

try {
    console.log(yasKontrol(-5));
} catch (hata) {
    console.error(hata.message); // "Yaş negatif olamaz!"
}
```

### Özel Hata Sınıfları

```javascript
// Özel hata sınıfı
function GecersizYasHatasi(mesaj) {
    this.name = "GecersizYasHatasi";
    this.message = mesaj;
    this.stack = (new Error()).stack;
}
GecersizYasHatasi.prototype = Object.create(Error.prototype);

function yasKontrol(yas) {
    if (yas < 0) {
        throw new GecersizYasHatasi("Yaş negatif olamaz!");
    }
    return "Yaş geçerli: " + yas;
}

try {
    yasKontrol(-5);
} catch (hata) {
    if (hata instanceof GecersizYasHatasi) {
        console.error("Özel hata:", hata.message);
    } else {
        console.error("Bilinmeyen hata:", hata);
    }
}
```

## 🔄 İç İçe Try-Catch

```javascript
try {
    try {
        throw new Error("İç hata");
    } catch (icHata) {
        console.log("İç hata yakalandı:", icHata.message);
        throw new Error("Dış hataya dönüştürüldü");
    }
} catch (disHata) {
    console.log("Dış hata yakalandı:", disHata.message);
}
```

## 💡 Pratik Örnekler

### JSON Parse Hata Yönetimi

```javascript
function guvenliJsonParse(jsonString) {
    try {
        return JSON.parse(jsonString);
    } catch (hata) {
        console.error("JSON parse hatası:", hata.message);
        return null;
    }
}

var gecersizJson = '{"isim":"Bahadır"'; // Eksik kapanış
var sonuc = guvenliJsonParse(gecersizJson);
console.log(sonuc); // null
```

### API İstek Hata Yönetimi

```javascript
async function apiIstek(url) {
    try {
        var response = await fetch(url);
        
        if (!response.ok) {
            throw new Error(`HTTP ${response.status}: ${response.statusText}`);
        }
        
        var veri = await response.json();
        return veri;
        
    } catch (hata) {
        if (hata.name === "TypeError") {
            console.error("Ağ hatası - bağlantı kurulamadı");
        } else {
            console.error("API hatası:", hata.message);
        }
        throw hata; // Hata'yı yukarı fırlat
    }
}

// Kullanım
apiIstek("https://api.example.com/data")
    .then(veri => console.log(veri))
    .catch(hata => console.error("Hata yakalandı:", hata));
```

### Form Validasyonu

```javascript
function formKontrol(formVerisi) {
    try {
        if (!formVerisi.isim || formVerisi.isim.length < 3) {
            throw new Error("İsim en az 3 karakter olmalı");
        }
        
        if (!formVerisi.email || !formVerisi.email.includes("@")) {
            throw new Error("Geçerli bir email girin");
        }
        
        if (!formVerisi.yas || formVerisi.yas < 18) {
            throw new Error("Yaş en az 18 olmalı");
        }
        
        return {basarili: true, mesaj: "Form geçerli"};
        
    } catch (hata) {
        return {basarili: false, mesaj: hata.message};
    }
}

var form = {
    isim: "Ba",
    email: "gecersiz",
    yas: 15
};

var sonuc = formKontrol(form);
console.log(sonuc); // {basarili: false, mesaj: "İsim en az 3 karakter olmalı"}
```

### Dosya Okuma Hata Yönetimi

```javascript
function dosyaOku(dosyaAdi) {
    try {
        // Dosya okuma işlemi (örnek)
        if (!dosyaAdi) {
            throw new Error("Dosya adı belirtilmedi");
        }
        
        if (!dosyaAdi.endsWith(".txt")) {
            throw new Error("Sadece .txt dosyaları okunabilir");
        }
        
        return "Dosya içeriği";
        
    } catch (hata) {
        console.error("Dosya okuma hatası:", hata.message);
        return null;
    } finally {
        console.log("Dosya işlemi tamamlandı");
    }
}
```

### Zaman Aşımı Hata Yönetimi

```javascript
function zamanAsimiIleIslem(islem, sure) {
    return new Promise(function(resolve, reject) {
        var zamanAsimi = setTimeout(function() {
            reject(new Error("İşlem zaman aşımına uğradı"));
        }, sure);
        
        islem()
            .then(function(sonuc) {
                clearTimeout(zamanAsimi);
                resolve(sonuc);
            })
            .catch(function(hata) {
                clearTimeout(zamanAsimi);
                reject(hata);
            });
    });
}

// Kullanım
zamanAsimiIleIslem(function() {
    return new Promise(function(resolve) {
        setTimeout(resolve, 2000, "İşlem tamamlandı");
    });
}, 1000)
    .then(sonuc => console.log(sonuc))
    .catch(hata => console.error(hata.message)); // "İşlem zaman aşımına uğradı"
```

### Global Hata Yakalama

```javascript
// Global hata yakalama
window.addEventListener("error", function(event) {
    console.error("Global hata:", event.error);
    // Hata loglama servisine gönder
});

// Promise rejection yakalama
window.addEventListener("unhandledrejection", function(event) {
    console.error("Yakalanmamış promise rejection:", event.reason);
    event.preventDefault(); // Varsayılan hata mesajını engelle
});
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


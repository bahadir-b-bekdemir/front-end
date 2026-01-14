# ⏰ TİMERS (SETTIMEOUT, SETINTERVAL)

JavaScript'te zamanlanmış işlemler için `setTimeout` ve `setInterval` kullanılır.

## ⏱️ setTimeout() - Tek Seferlik Gecikme

Belirli bir süre sonra bir kez çalışır:

```javascript
// Temel kullanım
setTimeout(function() {
    console.log("2 saniye sonra çalıştı");
}, 2000);

// Arrow function ile
setTimeout(() => {
    console.log("1 saniye sonra çalıştı");
}, 1000);

// Parametreli fonksiyon
function selamla(isim) {
    console.log("Merhaba " + isim);
}
setTimeout(selamla, 1000, "Bahadır");
```

### setTimeout İptal Etme

```javascript
// Timeout ID'sini sakla
var timeoutId = setTimeout(function() {
    console.log("Bu çalışmayacak");
}, 2000);

// İptal et
clearTimeout(timeoutId);
```

## 🔄 setInterval() - Tekrarlayan İşlem

Belirli aralıklarla tekrar tekrar çalışır:

```javascript
// Her 1 saniyede bir çalış
var intervalId = setInterval(function() {
    console.log("Her saniye çalışıyor");
}, 1000);

// 5 saniye sonra durdur
setTimeout(function() {
    clearInterval(intervalId);
    console.log("Interval durduruldu");
}, 5000);
```

### setInterval İptal Etme

```javascript
var sayac = 0;
var intervalId = setInterval(function() {
    sayac++;
    console.log("Sayaç: " + sayac);
    
    if (sayac >= 5) {
        clearInterval(intervalId);
        console.log("Sayaç durduruldu");
    }
}, 1000);
```

## 💡 Pratik Örnekler

### Geri Sayım (Countdown)

```javascript
function geriSayim(sure) {
    var kalanSure = sure;
    
    var intervalId = setInterval(function() {
        console.log("Kalan süre: " + kalanSure + " saniye");
        kalanSure--;
        
        if (kalanSure < 0) {
            clearInterval(intervalId);
            console.log("Süre doldu!");
        }
    }, 1000);
}

geriSayim(5);
```

### Debounce (Gecikme)

Kullanıcı etkileşimlerini sınırlamak için:

```javascript
function debounce(fonksiyon, bekleme) {
    var timeoutId;
    
    return function() {
        var context = this;
        var args = arguments;
        
        clearTimeout(timeoutId);
        
        timeoutId = setTimeout(function() {
            fonksiyon.apply(context, args);
        }, bekleme);
    };
}

// Kullanım - Arama kutusu
var aramaKutusu = document.getElementById("arama");
var aramaYap = debounce(function() {
    console.log("Arama yapılıyor:", aramaKutusu.value);
}, 500);

aramaKutusu.addEventListener("input", aramaYap);
```

### Throttle (Kısıtlama)

Belirli aralıklarla çalıştırmak için:

```javascript
function throttle(fonksiyon, sure) {
    var sonCalisma = 0;
    
    return function() {
        var simdi = Date.now();
        
        if (simdi - sonCalisma >= sure) {
            fonksiyon.apply(this, arguments);
            sonCalisma = simdi;
        }
    };
}

// Kullanım - Scroll event
var scrollHandler = throttle(function() {
    console.log("Scroll edildi");
}, 1000);

window.addEventListener("scroll", scrollHandler);
```

### Animasyon

```javascript
function animasyon(baslangic, bitis, sure, callback) {
    var fark = bitis - baslangic;
    var adim = fark / (sure / 16); // 60 FPS için
    var mevcut = baslangic;
    
    var intervalId = setInterval(function() {
        mevcut += adim;
        
        if ((adim > 0 && mevcut >= bitis) || (adim < 0 && mevcut <= bitis)) {
            mevcut = bitis;
            clearInterval(intervalId);
        }
        
        callback(mevcut);
    }, 16);
}

// Kullanım
var element = document.getElementById("animasyon");
animasyon(0, 100, 1000, function(deger) {
    element.style.left = deger + "px";
});
```

### Otomatik Kaydetme

```javascript
var otomatikKaydet = setInterval(function() {
    var formVerisi = {
        isim: document.getElementById("isim").value,
        email: document.getElementById("email").value
    };
    
    localStorage.setItem("otomatikKayit", JSON.stringify(formVerisi));
    console.log("Otomatik kaydedildi");
}, 30000); // Her 30 saniyede bir

// Form gönderildiğinde durdur
document.getElementById("form").addEventListener("submit", function() {
    clearInterval(otomatikKaydet);
    localStorage.removeItem("otomatikKayit");
});
```

### Zamanlayıcı (Timer)

```javascript
function zamanlayici(dakika) {
    var saniye = dakika * 60;
    var dakikaGoster = Math.floor(saniye / 60);
    var saniyeGoster = saniye % 60;
    
    var intervalId = setInterval(function() {
        saniye--;
        dakikaGoster = Math.floor(saniye / 60);
        saniyeGoster = saniye % 60;
        
        var format = 
            (dakikaGoster < 10 ? "0" : "") + dakikaGoster + ":" +
            (saniyeGoster < 10 ? "0" : "") + saniyeGoster;
        
        console.log("Kalan süre: " + format);
        
        if (saniye <= 0) {
            clearInterval(intervalId);
            console.log("Süre doldu!");
        }
    }, 1000);
}

zamanlayici(2); // 2 dakika
```

### Polling (Periyodik Kontrol)

```javascript
function durumKontrol() {
    fetch("https://api.example.com/durum")
        .then(response => response.json())
        .then(veri => {
            console.log("Durum:", veri);
            
            if (veri.durum === "tamamlandi") {
                clearInterval(pollingId);
                console.log("İşlem tamamlandı!");
            }
        })
        .catch(hata => {
            console.error("Hata:", hata);
        });
}

// Her 5 saniyede bir kontrol et
var pollingId = setInterval(durumKontrol, 5000);
```

### İlerleme Çubuğu

```javascript
function ilerlemeCubugu(sure) {
    var ilerleme = 0;
    var adim = 100 / (sure / 100); // Her 100ms'de artış
    
    var intervalId = setInterval(function() {
        ilerleme += adim;
        
        if (ilerleme >= 100) {
            ilerleme = 100;
            clearInterval(intervalId);
        }
        
        console.log("İlerleme: %" + Math.round(ilerleme));
        
        // DOM'da güncelle
        var cubuk = document.getElementById("ilerleme");
        if (cubuk) {
            cubuk.style.width = ilerleme + "%";
        }
    }, 100);
}

ilerlemeCubugu(5000); // 5 saniyede tamamlan
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


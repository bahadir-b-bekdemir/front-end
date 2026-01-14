# ⚡ ASENKRON PROGRAMLAMA

JavaScript, tek iş parçacıklı (single-threaded) bir dildir. Asenkron programlama, uzun süren işlemleri bloklamadan çalıştırmak için kullanılır.

## 🔄 Callbacks (Geri Çağrılar)

Callback, bir fonksiyonun başka bir fonksiyona parametre olarak geçirilmesidir:

```javascript
function islemYap(veri, callback) {
    console.log("İşlem başladı: " + veri);
    setTimeout(function() {
        callback("İşlem tamamlandı: " + veri);
    }, 1000);
}

islemYap("Veri 1", function(sonuc) {
    console.log(sonuc);
});
```

### Callback Hell (Cehennem)

Çoklu callback'ler iç içe geçtiğinde okunması zor kod oluşur:

```javascript
// Callback hell örneği
setTimeout(function() {
    console.log("1. işlem");
    setTimeout(function() {
        console.log("2. işlem");
        setTimeout(function() {
            console.log("3. işlem");
        }, 1000);
    }, 1000);
}, 1000);
```

## 🔄 Promises (Vaadler)

Promise, asenkron işlemin başarılı veya başarısız olacağını temsil eder:

### Promise Oluşturma

```javascript
var promise = new Promise(function(resolve, reject) {
    var basarili = true;
    
    if (basarili) {
        resolve("İşlem başarılı!");
    } else {
        reject("İşlem başarısız!");
    }
});

promise
    .then(function(sonuc) {
        console.log(sonuc); // "İşlem başarılı!"
    })
    .catch(function(hata) {
        console.log(hata); // "İşlem başarısız!"
    });
```

### Promise Zincirleme

```javascript
function ilkIslem() {
    return new Promise(function(resolve) {
        setTimeout(function() {
            resolve("İlk işlem tamamlandı");
        }, 1000);
    });
}

function ikinciIslem(veri) {
    return new Promise(function(resolve) {
        setTimeout(function() {
            resolve(veri + " -> İkinci işlem tamamlandı");
        }, 1000);
    });
}

ilkIslem()
    .then(function(sonuc) {
        return ikinciIslem(sonuc);
    })
    .then(function(sonuc) {
        console.log(sonuc);
        // "İlk işlem tamamlandı -> İkinci işlem tamamlandı"
    });
```

### Promise.all() - Tüm Promise'ler

```javascript
var promise1 = Promise.resolve(3);
var promise2 = 42;
var promise3 = new Promise(function(resolve) {
    setTimeout(resolve, 100, "foo");
});

Promise.all([promise1, promise2, promise3])
    .then(function(degerler) {
        console.log(degerler); // [3, 42, "foo"]
    });
```

### Promise.race() - İlk Tamamlanan

```javascript
var promise1 = new Promise(function(resolve) {
    setTimeout(resolve, 500, "Birinci");
});

var promise2 = new Promise(function(resolve) {
    setTimeout(resolve, 100, "İkinci");
});

Promise.race([promise1, promise2])
    .then(function(sonuc) {
        console.log(sonuc); // "İkinci" (daha hızlı)
    });
```

## 🔄 Async/Await (ES2017)

Async/await, Promise'leri daha okunabilir hale getirir:

### Temel Kullanım

```javascript
function islemYap() {
    return new Promise(function(resolve) {
        setTimeout(function() {
            resolve("İşlem tamamlandı");
        }, 1000);
    });
}

// Promise ile
islemYap()
    .then(function(sonuc) {
        console.log(sonuc);
    });

// Async/await ile
async function calistir() {
    var sonuc = await islemYap();
    console.log(sonuc);
}
calistir();
```

### Hata Yönetimi

```javascript
async function islemYap() {
    try {
        var sonuc = await uzunIslem();
        console.log(sonuc);
    } catch (hata) {
        console.error("Hata: " + hata);
    }
}
```

### Birden Fazla Async İşlem

```javascript
async function birdenFazlaIslem() {
    var sonuc1 = await islem1();
    var sonuc2 = await islem2();
    var sonuc3 = await islem3();
    
    return [sonuc1, sonuc2, sonuc3];
}

// Paralel çalıştırma
async function paralelIslem() {
    var [sonuc1, sonuc2, sonuc3] = await Promise.all([
        islem1(),
        islem2(),
        islem3()
    ]);
    
    return [sonuc1, sonuc2, sonuc3];
}
```

## 💡 Pratik Örnekler

### API İsteği (Promise ile)

```javascript
function apiIstek(url) {
    return new Promise(function(resolve, reject) {
        var xhr = new XMLHttpRequest();
        xhr.open("GET", url);
        xhr.onload = function() {
            if (xhr.status === 200) {
                resolve(JSON.parse(xhr.responseText));
            } else {
                reject("Hata: " + xhr.status);
            }
        };
        xhr.onerror = function() {
            reject("Ağ hatası");
        };
        xhr.send();
    });
}

apiIstek("https://api.example.com/data")
    .then(function(veri) {
        console.log(veri);
    })
    .catch(function(hata) {
        console.error(hata);
    });
```

### API İsteği (Async/Await ile)

```javascript
async function veriAl() {
    try {
        var veri = await apiIstek("https://api.example.com/data");
        console.log(veri);
    } catch (hata) {
        console.error(hata);
    }
}
```

### Sıralı İşlemler

```javascript
async function kullaniciIslemleri() {
    try {
        // 1. Kullanıcı bilgisi al
        var kullanici = await kullaniciAl(1);
        console.log("Kullanıcı:", kullanici);
        
        // 2. Kullanıcının gönderilerini al
        var gonderiler = await gonderileriAl(kullanici.id);
        console.log("Gönderiler:", gonderiler);
        
        // 3. Yorumları al
        var yorumlar = await yorumlariAl(gonderiler[0].id);
        console.log("Yorumlar:", yorumlar);
        
    } catch (hata) {
        console.error("Hata oluştu:", hata);
    }
}
```

### Paralel İşlemler

```javascript
async function paralelVeriAl() {
    try {
        var [kullanicilar, gonderiler, yorumlar] = await Promise.all([
            kullaniciAl(1),
            gonderileriAl(1),
            yorumlariAl(1)
        ]);
        
        console.log("Kullanıcılar:", kullanicilar);
        console.log("Gönderiler:", gonderiler);
        console.log("Yorumlar:", yorumlar);
        
    } catch (hata) {
        console.error("Hata:", hata);
    }
}
```

### Timeout ile Promise

```javascript
function zamanAsimi(promise, sure) {
    return Promise.race([
        promise,
        new Promise(function(_, reject) {
            setTimeout(function() {
                reject(new Error("Zaman aşımı!"));
            }, sure);
        })
    ]);
}

var islem = new Promise(function(resolve) {
    setTimeout(resolve, 5000, "İşlem tamamlandı");
});

zamanAsimi(islem, 3000)
    .then(function(sonuc) {
        console.log(sonuc);
    })
    .catch(function(hata) {
        console.error(hata.message); // "Zaman aşımı!"
    });
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


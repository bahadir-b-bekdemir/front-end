# 🌐 AJAX VE FETCH API

AJAX (Asynchronous JavaScript and XML), sayfa yenilemeden sunucu ile iletişim kurmayı sağlar. Fetch API ise modern ve daha kolay bir yöntemdir.

## 🔄 XMLHttpRequest (Eski Yöntem)

### GET İsteği

```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com/data", true);

xhr.onload = function() {
    if (xhr.status === 200) {
        var veri = JSON.parse(xhr.responseText);
        console.log(veri);
    } else {
        console.error("Hata: " + xhr.status);
    }
};

xhr.onerror = function() {
    console.error("Ağ hatası");
};

xhr.send();
```

### POST İsteği

```javascript
var xhr = new XMLHttpRequest();
xhr.open("POST", "https://api.example.com/kaydet", true);
xhr.setRequestHeader("Content-Type", "application/json");

xhr.onload = function() {
    if (xhr.status === 200 || xhr.status === 201) {
        var sonuc = JSON.parse(xhr.responseText);
        console.log("Başarılı:", sonuc);
    }
};

var veri = {
    isim: "Bahadır",
    yas: 25
};

xhr.send(JSON.stringify(veri));
```

## 🔄 Fetch API (Modern Yöntem)

### GET İsteği

```javascript
fetch("https://api.example.com/data")
    .then(function(response) {
        if (!response.ok) {
            throw new Error("HTTP hata: " + response.status);
        }
        return response.json();
    })
    .then(function(veri) {
        console.log(veri);
    })
    .catch(function(hata) {
        console.error("Hata:", hata);
    });
```

### GET İsteği (Async/Await)

```javascript
async function veriAl() {
    try {
        var response = await fetch("https://api.example.com/data");
        
        if (!response.ok) {
            throw new Error("HTTP hata: " + response.status);
        }
        
        var veri = await response.json();
        console.log(veri);
        
    } catch (hata) {
        console.error("Hata:", hata);
    }
}
```

### POST İsteği

```javascript
var veri = {
    isim: "Bahadır",
    yas: 25
};

fetch("https://api.example.com/kaydet", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify(veri)
})
    .then(function(response) {
        return response.json();
    })
    .then(function(sonuc) {
        console.log("Başarılı:", sonuc);
    })
    .catch(function(hata) {
        console.error("Hata:", hata);
    });
```

### POST İsteği (Async/Await)

```javascript
async function veriKaydet() {
    try {
        var veri = {
            isim: "Bahadır",
            yas: 25
        };
        
        var response = await fetch("https://api.example.com/kaydet", {
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify(veri)
        });
        
        if (!response.ok) {
            throw new Error("HTTP hata: " + response.status);
        }
        
        var sonuc = await response.json();
        console.log("Başarılı:", sonuc);
        
    } catch (hata) {
        console.error("Hata:", hata);
    }
}
```

## 🔄 Fetch Seçenekleri

### Headers (Başlıklar)

```javascript
fetch("https://api.example.com/data", {
    headers: {
        "Content-Type": "application/json",
        "Authorization": "Bearer token123",
        "X-Custom-Header": "değer"
    }
});
```

### PUT İsteği

```javascript
var veri = {
    isim: "Bahadır",
    yas: 26
};

fetch("https://api.example.com/kullanici/1", {
    method: "PUT",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify(veri)
})
    .then(response => response.json())
    .then(sonuc => console.log(sonuc));
```

### DELETE İsteği

```javascript
fetch("https://api.example.com/kullanici/1", {
    method: "DELETE"
})
    .then(response => {
        if (response.ok) {
            console.log("Silindi");
        }
    });
```

### Form Data Gönderme

```javascript
var formData = new FormData();
formData.append("isim", "Bahadır");
formData.append("yas", 25);
formData.append("dosya", fileInput.files[0]);

fetch("https://api.example.com/upload", {
    method: "POST",
    body: formData
});
```

## 🔄 Response İşleme

### Farklı Veri Tipleri

```javascript
// JSON
fetch("https://api.example.com/data")
    .then(response => response.json())
    .then(veri => console.log(veri));

// Text
fetch("https://api.example.com/data")
    .then(response => response.text())
    .then(metin => console.log(metin));

// Blob (Binary)
fetch("https://api.example.com/resim.jpg")
    .then(response => response.blob())
    .then(blob => {
        var url = URL.createObjectURL(blob);
        // Resmi göster
    });
```

### Response Durumu

```javascript
fetch("https://api.example.com/data")
    .then(function(response) {
        console.log("Status:", response.status);
        console.log("Status Text:", response.statusText);
        console.log("OK:", response.ok);
        console.log("Headers:", response.headers);
        
        return response.json();
    });
```

## 💡 Pratik Örnekler

### API Wrapper Fonksiyonu

```javascript
async function apiIstek(url, secenekler = {}) {
    try {
        var varsayilanSecenekler = {
            method: "GET",
            headers: {
                "Content-Type": "application/json"
            }
        };
        
        var finalSecenekler = {
            ...varsayilanSecenekler,
            ...secenekler,
            headers: {
                ...varsayilanSecenekler.headers,
                ...secenekler.headers
            }
        };
        
        var response = await fetch(url, finalSecenekler);
        
        if (!response.ok) {
            throw new Error(`HTTP ${response.status}: ${response.statusText}`);
        }
        
        return await response.json();
        
    } catch (hata) {
        console.error("API Hatası:", hata);
        throw hata;
    }
}

// Kullanım
var veri = await apiIstek("https://api.example.com/data");
var sonuc = await apiIstek("https://api.example.com/kaydet", {
    method: "POST",
    body: JSON.stringify({isim: "Bahadır"})
});
```

### Çoklu İstekler

```javascript
async function cokluVeriAl() {
    try {
        var [kullanicilar, gonderiler, yorumlar] = await Promise.all([
            fetch("https://api.example.com/kullanicilar").then(r => r.json()),
            fetch("https://api.example.com/gonderiler").then(r => r.json()),
            fetch("https://api.example.com/yorumlar").then(r => r.json())
        ]);
        
        console.log("Kullanıcılar:", kullanicilar);
        console.log("Gönderiler:", gonderiler);
        console.log("Yorumlar:", yorumlar);
        
    } catch (hata) {
        console.error("Hata:", hata);
    }
}
```

### Hata Yönetimi

```javascript
async function guvenliIstek(url) {
    try {
        var response = await fetch(url);
        
        if (!response.ok) {
            if (response.status === 404) {
                throw new Error("Sayfa bulunamadı");
            } else if (response.status === 500) {
                throw new Error("Sunucu hatası");
            } else {
                throw new Error(`HTTP ${response.status}`);
            }
        }
        
        return await response.json();
        
    } catch (hata) {
        if (hata.name === "TypeError") {
            console.error("Ağ hatası - bağlantı kurulamadı");
        } else {
            console.error("Hata:", hata.message);
        }
        throw hata;
    }
}
```

### Timeout ile Fetch

```javascript
function zamanAsimiIleFetch(url, secenekler = {}, sure = 5000) {
    return Promise.race([
        fetch(url, secenekler),
        new Promise(function(_, reject) {
            setTimeout(function() {
                reject(new Error("İstek zaman aşımına uğradı"));
            }, sure);
        })
    ]);
}

zamanAsimiIleFetch("https://api.example.com/data", {}, 3000)
    .then(response => response.json())
    .then(veri => console.log(veri))
    .catch(hata => console.error(hata));
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


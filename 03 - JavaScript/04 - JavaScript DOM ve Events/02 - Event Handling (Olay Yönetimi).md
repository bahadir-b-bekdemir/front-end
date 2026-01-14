# 🎯 EVENT HANDLING (OLAY YÖNETİMİ)

Event (olay) yönetimi, kullanıcı etkileşimlerine (tıklama, klavye, fare hareketleri vb.) yanıt vermek için kullanılır. JavaScript ile çeşitli event'leri dinleyebilir ve işleyebiliriz.

## 🎯 Event Nedir?

Event'ler, kullanıcının veya tarayıcının gerçekleştirdiği eylemlerdir:
- 🖱️ Fare tıklaması
- ⌨️ Klavye tuşuna basma
- 📄 Sayfa yükleme
- 📝 Form gönderme
- 🖼️ Resim yükleme
- vs.

## 🔧 Event Listener Ekleme

### addEventListener() - Modern Yöntem (Önerilen)

```javascript
var buton = document.getElementById("myButton");

buton.addEventListener("click", function() {
    console.log("Butona tıklandı!");
});
```

### İsimli Fonksiyon ile

```javascript
var buton = document.getElementById("myButton");

function butonaTiklandi() {
    console.log("Butona tıklandı!");
}

buton.addEventListener("click", butonaTiklandi);
```

### HTML İçinde (Inline) - Önerilmez

```html
<button onclick="alert('Tıklandı!')">Tıkla</button>
```

## 🖱️ Mouse Events (Fare Olayları)

### click - Tıklama

```javascript
var buton = document.getElementById("myButton");

buton.addEventListener("click", function() {
    console.log("Tıklandı!");
});
```

### dblclick - Çift Tıklama

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("dblclick", function() {
    console.log("Çift tıklandı!");
});
```

### mousedown - Fare Basıldı

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("mousedown", function() {
    console.log("Fare basıldı!");
});
```

### mouseup - Fare Bırakıldı

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("mouseup", function() {
    console.log("Fare bırakıldı!");
});
```

### mouseover - Fare Üzerine Geldi

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("mouseover", function() {
    console.log("Fare üzerine geldi!");
});
```

### mouseout - Fare Ayrıldı

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("mouseout", function() {
    console.log("Fare ayrıldı!");
});
```

### mousemove - Fare Hareket Etti

```javascript
var eleman = document.getElementById("myElement");

eleman.addEventListener("mousemove", function(event) {
    console.log("X: " + event.clientX + ", Y: " + event.clientY);
});
```

## ⌨️ Keyboard Events (Klavye Olayları)

### keydown - Tuşa Basıldı

```javascript
document.addEventListener("keydown", function(event) {
    console.log("Tuşa basıldı: " + event.key);
    console.log("Kod: " + event.code);
});
```

### keyup - Tuş Bırakıldı

```javascript
document.addEventListener("keyup", function(event) {
    console.log("Tuş bırakıldı: " + event.key);
});
```

### keypress - Tuş Basıldı (Deprecated)

```javascript
document.addEventListener("keypress", function(event) {
    console.log("Tuş: " + event.key);
});
```

### Özel Tuş Kontrolü

```javascript
document.addEventListener("keydown", function(event) {
    if (event.key === "Enter") {
        console.log("Enter tuşuna basıldı!");
    }
    
    if (event.key === "Escape") {
        console.log("Escape tuşuna basıldı!");
    }
    
    // Ctrl + S
    if (event.ctrlKey && event.key === "s") {
        event.preventDefault(); // Varsayılan davranışı engelle
        console.log("Kaydet!");
    }
});
```

## 📄 Form Events (Form Olayları)

### submit - Form Gönderme

```javascript
var form = document.getElementById("myForm");

form.addEventListener("submit", function(event) {
    event.preventDefault(); // Form gönderimini engelle
    
    console.log("Form gönderildi!");
    // Form işlemleri burada yapılır
});
```

### change - Değer Değişti

```javascript
var input = document.getElementById("myInput");

input.addEventListener("change", function() {
    console.log("Değer değişti: " + this.value);
});
```

### input - Anlık Değişiklik

```javascript
var input = document.getElementById("myInput");

input.addEventListener("input", function() {
    console.log("Anlık değer: " + this.value);
});
```

### focus - Odaklandı

```javascript
var input = document.getElementById("myInput");

input.addEventListener("focus", function() {
    console.log("Input odaklandı!");
    this.style.borderColor = "blue";
});
```

### blur - Odak Kaybetti

```javascript
var input = document.getElementById("myInput");

input.addEventListener("blur", function() {
    console.log("Input odak kaybetti!");
    this.style.borderColor = "gray";
});
```

## 📄 Document Events (Belge Olayları)

### DOMContentLoaded - DOM Yüklendi

```javascript
document.addEventListener("DOMContentLoaded", function() {
    console.log("DOM yüklendi!");
    // Sayfa yüklenmeden önce çalışır
});
```

### load - Sayfa Yüklendi

```javascript
window.addEventListener("load", function() {
    console.log("Sayfa tamamen yüklendi!");
    // Tüm kaynaklar (resimler, CSS vb.) yüklendikten sonra çalışır
});
```

### beforeunload - Sayfa Kapatılmadan Önce

```javascript
window.addEventListener("beforeunload", function(event) {
    event.preventDefault();
    event.returnValue = ""; // Tarayıcı uyarısı gösterir
});
```

## 🎯 Event Object (Olay Nesnesi)

Event listener fonksiyonları, event nesnesini parametre olarak alır:

```javascript
var buton = document.getElementById("myButton");

buton.addEventListener("click", function(event) {
    console.log(event.type); // "click"
    console.log(event.target); // Tıklanan eleman
    console.log(event.clientX); // Fare X koordinatı
    console.log(event.clientY); // Fare Y koordinatı
    console.log(event.timeStamp); // Olay zamanı
});
```

## 🛑 Event Propagation (Olay Yayılımı)

### stopPropagation() - Yayılımı Durdur

```javascript
var parent = document.getElementById("parent");
var child = document.getElementById("child");

parent.addEventListener("click", function() {
    console.log("Parent tıklandı");
});

child.addEventListener("click", function(event) {
    event.stopPropagation(); // Parent'a yayılmayı engelle
    console.log("Child tıklandı");
});
```

### preventDefault() - Varsayılan Davranışı Engelle

```javascript
var link = document.querySelector("a");

link.addEventListener("click", function(event) {
    event.preventDefault(); // Link takibini engelle
    console.log("Link tıklandı ama sayfa değişmedi");
});
```

## 🔄 Event Listener Kaldırma

### removeEventListener()

```javascript
var buton = document.getElementById("myButton");

function butonaTiklandi() {
    console.log("Tıklandı!");
}

// Ekle
buton.addEventListener("click", butonaTiklandi);

// Kaldır
buton.removeEventListener("click", butonaTiklandi);
```

## 💡 Pratik Örnekler

### Buton Tıklama Sayacı

```html
<button id="counterBtn">Tıkla</button>
<p id="counter">0</p>

<script>
var btn = document.getElementById("counterBtn");
var counter = document.getElementById("counter");
var sayac = 0;

btn.addEventListener("click", function() {
    sayac++;
    counter.textContent = sayac;
});
</script>
```

### Klavye Kısayolları

```javascript
document.addEventListener("keydown", function(event) {
    // Ctrl + K
    if (event.ctrlKey && event.key === "k") {
        event.preventDefault();
        console.log("Arama açıldı!");
    }
    
    // Escape
    if (event.key === "Escape") {
        console.log("Modal kapatıldı!");
    }
});
```

### Form Validasyonu

```html
<form id="myForm">
    <input type="text" id="isim" placeholder="İsim" required>
    <input type="email" id="email" placeholder="Email" required>
    <button type="submit">Gönder</button>
    <p id="hata"></p>
</form>

<script>
var form = document.getElementById("myForm");
var hata = document.getElementById("hata");

form.addEventListener("submit", function(event) {
    event.preventDefault();
    
    var isim = document.getElementById("isim").value;
    var email = document.getElementById("email").value;
    
    if (isim.length < 3) {
        hata.textContent = "İsim en az 3 karakter olmalı";
        hata.style.color = "red";
        return;
    }
    
    if (!email.includes("@")) {
        hata.textContent = "Geçerli bir email girin";
        hata.style.color = "red";
        return;
    }
    
    hata.textContent = "Form başarıyla gönderildi!";
    hata.style.color = "green";
});
</script>
```

### Sürükle ve Bırak (Drag and Drop)

```html
<div id="dragElement" draggable="true">Sürükle</div>
<div id="dropZone">Bırak</div>

<script>
var dragElement = document.getElementById("dragElement");
var dropZone = document.getElementById("dropZone");

dragElement.addEventListener("dragstart", function(event) {
    event.dataTransfer.setData("text", event.target.id);
});

dropZone.addEventListener("dragover", function(event) {
    event.preventDefault();
});

dropZone.addEventListener("drop", function(event) {
    event.preventDefault();
    var data = event.dataTransfer.getData("text");
    var element = document.getElementById(data);
    dropZone.appendChild(element);
});
</script>
```

### Modal Açma/Kapatma

```html
<button id="openModal">Modal Aç</button>
<div id="modal" style="display: none;">
    <div>
        <h2>Modal Başlık</h2>
        <button id="closeModal">Kapat</button>
    </div>
</div>

<script>
var openBtn = document.getElementById("openModal");
var closeBtn = document.getElementById("closeModal");
var modal = document.getElementById("modal");

openBtn.addEventListener("click", function() {
    modal.style.display = "block";
});

closeBtn.addEventListener("click", function() {
    modal.style.display = "none";
});

// Escape ile kapat
document.addEventListener("keydown", function(event) {
    if (event.key === "Escape") {
        modal.style.display = "none";
    }
});
</script>
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


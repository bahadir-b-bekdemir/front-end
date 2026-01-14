# 📍 HTML5 GEOLOCATION API

**HTML5** ile birlikte `Geolocation API` eklendi. Bu API, kullanıcının konum bilgisini almak için kullanılır.

## 📋 Geolocation API

### `navigator.geolocation`

Geolocation API'ye erişim sağlar.

### `getCurrentPosition()`

Mevcut konumu alır.

### `watchPosition()`

Konum değişikliklerini izler.

### `clearWatch()`

Konum izlemeyi durdurur.

## 💡 Kullanım Örnekleri

### Temel Konum Alma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Geolocation Temel</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        button {
            padding: 10px 20px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        #map {
            width: 100%;
            height: 300px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Geolocation API</h1>
    
    <div class="container">
        <button onclick="getLocation()">Konumumu Al</button>
        <div id="location"></div>
    </div>
    
    <div id="map"></div>
    
    <script>
        function getLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    showPosition,
                    showError
                );
            } else {
                document.getElementById('location').innerHTML = 
                    'Geolocation bu tarayıcıda desteklenmiyor.';
            }
        }
        
        function showPosition(position) {
            const lat = position.coords.latitude;
            const lon = position.coords.longitude;
            const accuracy = position.coords.accuracy;
            
            document.getElementById('location').innerHTML = `
                <h3>Konum Bilgileri</h3>
                <p><strong>Enlem:</strong> ${lat}</p>
                <p><strong>Boylam:</strong> ${lon}</p>
                <p><strong>Doğruluk:</strong> ${accuracy} metre</p>
            `;
            
            // Harita göster (basit)
            showMap(lat, lon);
        }
        
        function showError(error) {
            let message = '';
            switch(error.code) {
                case error.PERMISSION_DENIED:
                    message = 'Kullanıcı konum erişimini reddetti.';
                    break;
                case error.POSITION_UNAVAILABLE:
                    message = 'Konum bilgisi alınamadı.';
                    break;
                case error.TIMEOUT:
                    message = 'Konum isteği zaman aşımına uğradı.';
                    break;
                default:
                    message = 'Bilinmeyen bir hata oluştu.';
                    break;
            }
            document.getElementById('location').innerHTML = 
                `<p style="color: red;">${message}</p>`;
        }
        
        function showMap(lat, lon) {
            // Google Maps embed (basit örnek)
            const mapDiv = document.getElementById('map');
            mapDiv.innerHTML = `
                <iframe 
                    width="100%" 
                    height="300" 
                    frameborder="0" 
                    style="border:0"
                    src="https://www.google.com/maps/embed/v1/place?key=YOUR_API_KEY&q=${lat},${lon}" 
                    allowfullscreen>
                </iframe>
                <p><small>Not: Harita görüntülemek için Google Maps API anahtarı gerekir.</small></p>
            `;
        }
    </script>
</body>
</html>
```

### Konum İzleme

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Konum İzleme</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        button {
            padding: 10px 20px;
            margin: 5px;
            background-color: #27ae60;
            color: white;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        
        button.stop {
            background-color: #e74c3c;
        }
        
        #tracking {
            margin-top: 20px;
        }
        
        .position {
            background-color: white;
            padding: 10px;
            margin: 5px 0;
            border-radius: 3px;
            border-left: 4px solid #3498db;
        }
    </style>
</head>
<body>
    <h1>Konum İzleme</h1>
    
    <div class="container">
        <button onclick="startTracking()">İzlemeyi Başlat</button>
        <button class="stop" onclick="stopTracking()">İzlemeyi Durdur</button>
        <div id="tracking"></div>
    </div>
    
    <script>
        let watchId = null;
        
        function startTracking() {
            if (navigator.geolocation) {
                watchId = navigator.geolocation.watchPosition(
                    updatePosition,
                    showError,
                    {
                        enableHighAccuracy: true,
                        timeout: 5000,
                        maximumAge: 0
                    }
                );
                document.getElementById('tracking').innerHTML = 
                    '<p>İzleme başlatıldı...</p>';
            } else {
                alert('Geolocation bu tarayıcıda desteklenmiyor.');
            }
        }
        
        function stopTracking() {
            if (watchId !== null) {
                navigator.geolocation.clearWatch(watchId);
                watchId = null;
                document.getElementById('tracking').innerHTML += 
                    '<p><strong>İzleme durduruldu.</strong></p>';
            }
        }
        
        function updatePosition(position) {
            const lat = position.coords.latitude;
            const lon = position.coords.longitude;
            const timestamp = new Date(position.timestamp).toLocaleTimeString();
            
            const div = document.createElement('div');
            div.className = 'position';
            div.innerHTML = `
                <strong>${timestamp}</strong><br>
                Enlem: ${lat.toFixed(6)}<br>
                Boylam: ${lon.toFixed(6)}
            `;
            
            document.getElementById('tracking').appendChild(div);
        }
        
        function showError(error) {
            alert('Konum hatası: ' + error.message);
        }
    </script>
</body>
</html>
```

### Mesafe Hesaplama

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Mesafe Hesaplama</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin: 20px 0;
        }
        
        input, button {
            padding: 10px;
            margin: 5px;
            border: 1px solid #ddd;
            border-radius: 3px;
        }
        
        button {
            background-color: #3498db;
            color: white;
            cursor: pointer;
        }
        
        #result {
            margin-top: 20px;
            padding: 15px;
            background-color: white;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>Mesafe Hesaplama</h1>
    
    <div class="container">
        <h2>Hedef Konum</h2>
        <input type="text" id="targetLat" placeholder="Enlem">
        <input type="text" id="targetLon" placeholder="Boylam">
        <button onclick="calculateDistance()">Mesafeyi Hesapla</button>
    </div>
    
    <div id="result"></div>
    
    <script>
        let currentPosition = null;
        
        // Mevcut konumu al
        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition(function(position) {
                currentPosition = {
                    lat: position.coords.latitude,
                    lon: position.coords.longitude
                };
                document.getElementById('result').innerHTML = 
                    `<p>Mevcut konumunuz alındı: ${currentPosition.lat.toFixed(6)}, ${currentPosition.lon.toFixed(6)}</p>`;
            });
        }
        
        function calculateDistance() {
            if (!currentPosition) {
                alert('Önce konumunuz alınmalı!');
                return;
            }
            
            const targetLat = parseFloat(document.getElementById('targetLat').value);
            const targetLon = parseFloat(document.getElementById('targetLon').value);
            
            if (isNaN(targetLat) || isNaN(targetLon)) {
                alert('Lütfen geçerli koordinatlar girin!');
                return;
            }
            
            const distance = getDistance(
                currentPosition.lat,
                currentPosition.lon,
                targetLat,
                targetLon
            );
            
            document.getElementById('result').innerHTML = `
                <h3>Mesafe Sonucu</h3>
                <p><strong>Mevcut Konum:</strong> ${currentPosition.lat.toFixed(6)}, ${currentPosition.lon.toFixed(6)}</p>
                <p><strong>Hedef Konum:</strong> ${targetLat.toFixed(6)}, ${targetLon.toFixed(6)}</p>
                <p><strong>Mesafe:</strong> ${distance.toFixed(2)} km</p>
            `;
        }
        
        // Haversine formülü ile mesafe hesaplama
        function getDistance(lat1, lon1, lat2, lon2) {
            const R = 6371; // Dünya yarıçapı (km)
            const dLat = toRad(lat2 - lat1);
            const dLon = toRad(lon2 - lon1);
            
            const a = Math.sin(dLat / 2) * Math.sin(dLat / 2) +
                      Math.cos(toRad(lat1)) * Math.cos(toRad(lat2)) *
                      Math.sin(dLon / 2) * Math.sin(dLon / 2);
            
            const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
            const distance = R * c;
            
            return distance;
        }
        
        function toRad(degrees) {
            return degrees * (Math.PI / 180);
        }
    </script>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **İzin**: Kullanıcıdan konum erişimi için izin istenir.

2. **Güvenlik**: HTTPS bağlantısı gereklidir (localhost hariç).

3. **Hata Yönetimi**: Hata durumları için uygun mesajlar gösterilmelidir.

4. **Performans**: `watchPosition()` sürekli konum alır, pil tüketir.

5. **Doğruluk**: Konum doğruluğu cihaza ve yönteme bağlıdır.

## 🎯 İyi Pratikler

- Kullanıcıdan izin isteyin
- Hata durumlarını yönetin
- HTTPS kullanın
- Performans için ayarları optimize edin
- Kullanıcıya konum kullanımını açıklayın
- Gizlilik politikası sağlayın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


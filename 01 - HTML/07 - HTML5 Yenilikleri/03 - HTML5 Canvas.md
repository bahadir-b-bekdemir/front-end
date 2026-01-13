# 🎨 HTML5 CANVAS

**HTML5** ile birlikte `<canvas>` etiketi eklendi. Canvas, JavaScript ile çizim yapmak için kullanılan bir alan sağlar.

## 📋 Canvas Etiketi

### `<canvas>...</canvas>`

Çizim alanı oluşturur. JavaScript ile çizim yapılır.

**Temel kullanım:**
```html
<canvas id="myCanvas" width="500" height="300"></canvas>
```

## 📋 Canvas API

Canvas üzerinde çizim yapmak için JavaScript Canvas API kullanılır.

### `getContext('2d')`

2D çizim bağlamı alır.

### Çizim Metodları

- `fillRect()` - Dikdörtgen doldurma
- `strokeRect()` - Dikdörtgen çizme
- `fillText()` - Metin doldurma
- `strokeText()` - Metin çizme
- `beginPath()` - Yol başlatma
- `moveTo()` - Nokta taşıma
- `lineTo()` - Çizgi çizme
- `arc()` - Yay çizme
- `fill()` - Doldurma
- `stroke()` - Çizme

## 💡 Kullanım Örnekleri

### Temel Canvas Çizimi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Canvas</title>
    <style>
        canvas {
            border: 1px solid #ddd;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h2>Temel Canvas Çizimi</h2>
    <canvas id="myCanvas" width="500" height="300"></canvas>
    
    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        
        // Dikdörtgen doldurma
        ctx.fillStyle = '#3498db';
        ctx.fillRect(50, 50, 100, 100);
        
        // Dikdörtgen çizme
        ctx.strokeStyle = '#e74c3c';
        ctx.lineWidth = 3;
        ctx.strokeRect(200, 50, 100, 100);
        
        // Metin
        ctx.fillStyle = '#2c3e50';
        ctx.font = '20px Arial';
        ctx.fillText('Canvas Örneği', 50, 200);
    </script>
</body>
</html>
```

### Çizgiler ve Şekiller

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çizgiler ve Şekiller</title>
    <style>
        canvas {
            border: 1px solid #ddd;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h2>Çizgiler ve Şekiller</h2>
    <canvas id="myCanvas" width="500" height="300"></canvas>
    
    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        
        // Çizgi
        ctx.beginPath();
        ctx.moveTo(50, 50);
        ctx.lineTo(200, 100);
        ctx.strokeStyle = '#3498db';
        ctx.lineWidth = 3;
        ctx.stroke();
        
        // Üçgen
        ctx.beginPath();
        ctx.moveTo(250, 50);
        ctx.lineTo(350, 150);
        ctx.lineTo(150, 150);
        ctx.closePath();
        ctx.fillStyle = '#27ae60';
        ctx.fill();
        
        // Daire
        ctx.beginPath();
        ctx.arc(400, 100, 50, 0, 2 * Math.PI);
        ctx.fillStyle = '#e74c3c';
        ctx.fill();
        
        // Yay
        ctx.beginPath();
        ctx.arc(250, 200, 50, 0, Math.PI);
        ctx.strokeStyle = '#9b59b6';
        ctx.lineWidth = 5;
        ctx.stroke();
    </script>
</body>
</html>
```

### Animasyon

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Canvas Animasyon</title>
    <style>
        canvas {
            border: 1px solid #ddd;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h2>Canvas Animasyon</h2>
    <canvas id="myCanvas" width="500" height="300"></canvas>
    
    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        
        let x = 50;
        let y = 150;
        let dx = 2;
        let dy = 2;
        const radius = 20;
        
        function draw() {
            // Canvas'ı temizle
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // Daire çiz
            ctx.beginPath();
            ctx.arc(x, y, radius, 0, 2 * Math.PI);
            ctx.fillStyle = '#3498db';
            ctx.fill();
            
            // Hareket
            x += dx;
            y += dy;
            
            // Kenarlardan sekme
            if (x + radius > canvas.width || x - radius < 0) {
                dx = -dx;
            }
            if (y + radius > canvas.height || y - radius < 0) {
                dy = -dy;
            }
            
            requestAnimationFrame(draw);
        }
        
        draw();
    </script>
</body>
</html>
```

### Grafik Çizimi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Grafik Çizimi</title>
    <style>
        canvas {
            border: 1px solid #ddd;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h2>Grafik Çizimi</h2>
    <canvas id="myCanvas" width="500" height="300"></canvas>
    
    <script>
        const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        
        // Veri
        const data = [30, 50, 80, 60, 90, 40, 70];
        const barWidth = 50;
        const barSpacing = 20;
        const startX = 50;
        const startY = 250;
        const maxHeight = 200;
        
        // Eksen çiz
        ctx.strokeStyle = '#2c3e50';
        ctx.lineWidth = 2;
        ctx.beginPath();
        ctx.moveTo(startX, startY);
        ctx.lineTo(startX, 50);
        ctx.moveTo(startX, startY);
        ctx.lineTo(450, startY);
        ctx.stroke();
        
        // Çubuklar
        data.forEach((value, index) => {
            const x = startX + (barWidth + barSpacing) * index;
            const height = (value / 100) * maxHeight;
            const y = startY - height;
            
            ctx.fillStyle = `hsl(${index * 50}, 70%, 50%)`;
            ctx.fillRect(x, y, barWidth, height);
            
            // Değer yaz
            ctx.fillStyle = '#2c3e50';
            ctx.font = '12px Arial';
            ctx.fillText(value, x + barWidth / 2 - 10, y - 5);
        });
    </script>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Canvas Örneği</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .canvas-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        
        canvas {
            border: 2px solid #3498db;
            border-radius: 5px;
            margin: 10px;
        }
        
        .example {
            text-align: center;
            margin-bottom: 30px;
        }
    </style>
</head>
<body>
    <h1>Canvas Örnekleri</h1>
    
    <div class="canvas-container">
        <div class="example">
            <h3>Basit Şekiller</h3>
            <canvas id="canvas1" width="300" height="200"></canvas>
        </div>
        
        <div class="example">
            <h3>Grafik</h3>
            <canvas id="canvas2" width="300" height="200"></canvas>
        </div>
        
        <div class="example">
            <h3>Animasyon</h3>
            <canvas id="canvas3" width="300" height="200"></canvas>
        </div>
    </div>
    
    <script>
        // Canvas 1: Basit Şekiller
        const canvas1 = document.getElementById('canvas1');
        const ctx1 = canvas1.getContext('2d');
        
        ctx1.fillStyle = '#3498db';
        ctx1.fillRect(50, 50, 100, 100);
        
        ctx1.strokeStyle = '#e74c3c';
        ctx1.lineWidth = 3;
        ctx1.strokeRect(150, 50, 100, 100);
        
        ctx1.beginPath();
        ctx1.arc(250, 150, 30, 0, 2 * Math.PI);
        ctx1.fillStyle = '#27ae60';
        ctx1.fill();
        
        // Canvas 2: Grafik
        const canvas2 = document.getElementById('canvas2');
        const ctx2 = canvas2.getContext('2d');
        
        const data = [20, 40, 60, 80, 50];
        data.forEach((value, index) => {
            const x = 50 + index * 50;
            const height = value;
            const y = 150 - height;
            
            ctx2.fillStyle = `hsl(${index * 60}, 70%, 50%)`;
            ctx2.fillRect(x, y, 30, height);
        });
        
        // Canvas 3: Animasyon
        const canvas3 = document.getElementById('canvas3');
        const ctx3 = canvas3.getContext('2d');
        
        let angle = 0;
        function animate() {
            ctx3.clearRect(0, 0, canvas3.width, canvas3.height);
            
            const x = 150 + Math.cos(angle) * 50;
            const y = 100 + Math.sin(angle) * 50;
            
            ctx3.beginPath();
            ctx3.arc(x, y, 20, 0, 2 * Math.PI);
            ctx3.fillStyle = '#9b59b6';
            ctx3.fill();
            
            angle += 0.05;
            requestAnimationFrame(animate);
        }
        
        animate();
    </script>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **JavaScript Gerekli**: Canvas çizimi için JavaScript kullanılmalıdır.

2. **getContext**: Canvas üzerinde çizim yapmak için `getContext('2d')` kullanılır.

3. **Boyut**: Canvas boyutu `width` ve `height` özellikleri ile belirlenir.

4. **Performans**: Büyük canvas'lar performans sorunlarına neden olabilir.

5. **Tarayıcı Desteği**: Modern tarayıcılar canvas'ı destekler.

## 🎯 İyi Pratikler

- Canvas boyutunu `width` ve `height` ile belirleyin
- Çizim öncesi `beginPath()` kullanın
- Animasyon için `requestAnimationFrame` kullanın
- Performans için gereksiz çizimlerden kaçının
- Canvas'ı temizlemek için `clearRect()` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


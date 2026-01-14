# 🎵 HTML SES (audio)

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) ses dosyalarını oynatmak için `<audio>` etiketi kullanılır. HTML5 ile gelen bu etiket, tarayıcıda ses oynatmayı sağlar.

## 📋 Ses Etiketi Yapısı

### `<audio>...</audio>`

Ses oynatıcı etiketi. İçinde `<source>` etiketleri veya `src` özelliği ile ses dosyası belirtilir.

**Temel kullanım:**
```html
<audio src="ses.mp3" controls></audio>
```

## 📋 Ses Özellikleri

### `src` Özelliği

Ses dosyasının yolu veya URL'si.

### `controls` Özelliği

Ses kontrollerini (oynat, duraklat, ses seviyesi vb.) gösterir.

### `autoplay` Özelliği

Sesi otomatik olarak oynatır (tarayıcılar genellikle sesli otomatik oynatmayı engeller).

### `loop` Özelliği

Sesi döngüde oynatır.

### `muted` Özelliği

Sesi sessiz başlatır.

### `preload` Özelliği

Ses yükleme davranışını belirler (`none`, `metadata`, `auto`).

## 💡 Kullanım Örnekleri

### Temel Ses Oynatma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Temel Ses Oynatma</title>
</head>
<body>
    <h2>Ses Örneği</h2>
    <audio src="ses.mp3" controls>
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
</body>
</html>
```

### Çoklu Format Desteği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Çoklu Format Desteği</title>
</head>
<body>
    <h2>Çoklu Format Ses</h2>
    <audio controls>
        <source src="ses.mp3" type="audio/mpeg">
        <source src="ses.ogg" type="audio/ogg">
        <source src="ses.wav" type="audio/wav">
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
</body>
</html>
```

### Otomatik Oynatma ve Döngü

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Otomatik Oynatma</title>
</head>
<body>
    <h2>Otomatik Oynatılan Ses</h2>
    <audio src="ses.mp3" autoplay loop>
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
    
    <p>Not: Otomatik oynatma tarayıcılar tarafından genellikle engellenir.</p>
</body>
</html>
```

### Sessiz Başlatma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Sessiz Başlatma</title>
</head>
<body>
    <h2>Sessiz Başlatılan Ses</h2>
    <audio src="ses.mp3" controls muted>
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
    
    <p>Kullanıcı ses seviyesini kendisi ayarlayabilir.</p>
</body>
</html>
```

### Preload Seçenekleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Preload Seçenekleri</title>
</head>
<body>
    <h2>Preload: None</h2>
    <audio src="ses.mp3" controls preload="none">
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
    <p>Ses sadece kullanıcı tıkladığında yüklenecek.</p>
    
    <h2>Preload: Metadata</h2>
    <audio src="ses.mp3" controls preload="metadata">
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
    <p>Sadece metadata (süre, boyut vb.) yüklenecek.</p>
    
    <h2>Preload: Auto</h2>
    <audio src="ses.mp3" controls preload="auto">
        Tarayıcınız ses etiketini desteklemiyor.
    </audio>
    <p>Tüm ses dosyası yüklenecek.</p>
</body>
</html>
```

### Müzik Çalar Örneği

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Müzik Çalar</title>
    <style>
        .player {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 500px;
            margin: 20px auto;
        }
        
        .player h3 {
            margin-top: 0;
            color: #3498db;
        }
        
        .player audio {
            width: 100%;
            margin-top: 15px;
        }
        
        .playlist {
            list-style: none;
            padding: 0;
        }
        
        .playlist li {
            padding: 10px;
            margin: 5px 0;
            background-color: #34495e;
            border-radius: 5px;
            cursor: pointer;
        }
        
        .playlist li:hover {
            background-color: #3498db;
        }
    </style>
</head>
<body>
    <div class="player">
        <h3>Müzik Çalar</h3>
        <audio id="audioPlayer" controls>
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        
        <ul class="playlist">
            <li onclick="playAudio('ses1.mp3')">Şarkı 1</li>
            <li onclick="playAudio('ses2.mp3')">Şarkı 2</li>
            <li onclick="playAudio('ses3.mp3')">Şarkı 3</li>
        </ul>
    </div>
    
    <script>
        function playAudio(src) {
            var audio = document.getElementById('audioPlayer');
            audio.src = src;
            audio.play();
        }
    </script>
</body>
</html>
```

### Podcast Oynatıcı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Podcast Oynatıcı</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .podcast {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
        }
        
        .podcast h2 {
            color: #2c3e50;
            margin-top: 0;
        }
        
        .podcast audio {
            width: 100%;
            margin-top: 15px;
        }
        
        .podcast-info {
            color: #666;
            font-size: 0.9em;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Podcast Bölümleri</h1>
    
    <div class="podcast">
        <h2>Bölüm 1: HTML Temelleri</h2>
        <audio controls preload="metadata">
            <source src="podcast1.mp3" type="audio/mpeg">
            <source src="podcast1.ogg" type="audio/ogg">
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="podcast-info">
            <p>Süre: 25 dakika | Tarih: 15 Ocak 2024</p>
        </div>
    </div>
    
    <div class="podcast">
        <h2>Bölüm 2: CSS Stilleri</h2>
        <audio controls preload="metadata">
            <source src="podcast2.mp3" type="audio/mpeg">
            <source src="podcast2.ogg" type="audio/ogg">
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="podcast-info">
            <p>Süre: 30 dakika | Tarih: 20 Ocak 2024</p>
        </div>
    </div>
    
    <div class="podcast">
        <h2>Bölüm 3: JavaScript Temelleri</h2>
        <audio controls preload="metadata">
            <source src="podcast3.mp3" type="audio/mpeg">
            <source src="podcast3.ogg" type="audio/ogg">
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="podcast-info">
            <p>Süre: 35 dakika | Tarih: 25 Ocak 2024</p>
        </div>
    </div>
</body>
</html>
```

### Kapsamlı Örnek

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kapsamlı Ses Örnekleri</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
        }
        
        .audio-section {
            margin: 30px 0;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }
        
        .audio-section h2 {
            color: #2c3e50;
            margin-top: 0;
        }
        
        audio {
            width: 100%;
            margin-top: 15px;
        }
        
        .info {
            background-color: #e8f4f8;
            padding: 15px;
            border-left: 4px solid #3498db;
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <h1>Ses Kullanım Örnekleri</h1>
    
    <div class="audio-section">
        <h2>Kontrollü Ses</h2>
        <audio src="ses.mp3" controls>
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="info">
            <p>Kullanıcı oynatma, duraklatma ve ses seviyesi kontrollerine sahiptir.</p>
        </div>
    </div>
    
    <div class="audio-section">
        <h2>Çoklu Format Desteği</h2>
        <audio controls>
            <source src="ses.mp3" type="audio/mpeg">
            <source src="ses.ogg" type="audio/ogg">
            <source src="ses.wav" type="audio/wav">
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="info">
            <p>Tarayıcı desteklediği ilk formatı kullanacaktır.</p>
        </div>
    </div>
    
    <div class="audio-section">
        <h2>Preload: None (Performans İçin)</h2>
        <audio src="ses.mp3" controls preload="none">
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="info">
            <p>Ses sadece kullanıcı tıkladığında yüklenecek, sayfa yükleme hızını etkilemeyecek.</p>
        </div>
    </div>
    
    <div class="audio-section">
        <h2>Döngüde Oynatma</h2>
        <audio src="ses.mp3" controls loop>
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="info">
            <p>Ses bitince otomatik olarak başa döner ve tekrar oynar.</p>
        </div>
    </div>
    
    <div class="audio-section">
        <h2>Sessiz Başlatma</h2>
        <audio src="ses.mp3" controls muted>
            Tarayıcınız ses etiketini desteklemiyor.
        </audio>
        <div class="info">
            <p>Ses sessiz başlar, kullanıcı ses seviyesini ayarlayabilir.</p>
        </div>
    </div>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **Ses Formatları**: Yaygın formatlar: **MP3** (en yaygın), **OGG**, **WAV**. Tarayıcı uyumluluğu için çoklu format kullanın.

2. **Autoplay Politikası**: Modern tarayıcılar sesli otomatik oynatmayı engeller. Kullanıcı etkileşimi gereklidir.

3. **Preload**: Performans için `preload="none"` kullanın, sadece kullanıcı tıkladığında yüklensin.

4. **Erişilebilirlik**: Ses içeriği için transkript veya açıklama sağlayın.

5. **Dosya Boyutu**: Ses dosyalarını optimize edin, gereksiz yere büyük dosyalar kullanmayın.

6. **Mobil Uyumluluk**: Mobil cihazlarda otomatik oynatma genellikle çalışmaz.

## 🎯 İyi Pratikler

- Çoklu format desteği sağlayın (MP3, OGG)
- Performans için `preload="none"` kullanın
- Otomatik oynatma kullanmaktan kaçının
- Ses dosyalarını optimize edin
- Erişilebilirlik için transkript sağlayın
- Kullanıcı kontrolü için `controls` özelliğini kullanın
- Mobil uyumluluğu test edin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


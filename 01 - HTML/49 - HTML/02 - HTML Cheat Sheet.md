# 📚 HTML CHEAT SHEET (Hızlı Referans)

Kapsamlı HTML etiketleri, özellikleri ve kullanım örnekleri rehberi.

---

## 📋 TEMEL YAPI

### HTML5 Doküman Yapısı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
</head>
<body>
    <!-- İçerik buraya -->
</body>
</html>
```

### Temel Head Etiketleri

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Sayfa açıklaması">
    <meta name="keywords" content="anahtar, kelimeler">
    <meta name="author" content="Yazar Adı">
    <title>Sayfa Başlığı</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
```

---

## 🏷️ METİN ETİKETLERİ

### Başlıklar

| Etiket | Açıklama | Örnek |
|--------|----------|-------|
| `<h1>` | En büyük başlık (sayfada 1 kez) | `<h1>Ana Başlık</h1>` |
| `<h2>` | İkinci seviye başlık | `<h2>Alt Başlık</h2>` |
| `<h3>` | Üçüncü seviye başlık | `<h3>Alt Alt Başlık</h3>` |
| `<h4>` - `<h6>` | Daha küçük başlıklar | `<h4>Küçük Başlık</h4>` |

### Paragraf ve Metin Formatlama

| Etiket | Açıklama | Örnek |
|--------|----------|-------|
| `<p>` | Paragraf | `<p>Paragraf metni</p>` |
| `<br>` | Satır sonu (self-closing) | `<br>` |
| `<hr>` | Yatay çizgi (self-closing) | `<hr>` |
| `<strong>` | Önemli metin (kalın) | `<strong>Önemli</strong>` |
| `<b>` | Kalın metin (stil) | `<b>Kalın</b>` |
| `<em>` | Vurgulu metin (italik) | `<em>Vurgu</em>` |
| `<i>` | İtalik metin (stil) | `<i>İtalik</i>` |
| `<mark>` | İşaretli metin | `<mark>İşaretli</mark>` |
| `<small>` | Küçük metin | `<small>Küçük</small>` |
| `<del>` | Silinmiş metin | `<del>Silindi</del>` |
| `<ins>` | Eklenmiş metin | `<ins>Eklendi</ins>` |
| `<sub>` | Alt simge | H<sub>2</sub>O |
| `<sup>` | Üst simge | x<sup>2</sup> |
| `<code>` | Kod metni | `<code>kod</code>` |
| `<pre>` | Ön biçimlendirilmiş metin | `<pre>kod bloğu</pre>` |
| `<kbd>` | Klavye tuşu | `<kbd>Ctrl</kbd> + C |
| `<samp>` | Örnek çıktı | `<samp>Çıktı</samp>` |
| `<var>` | Değişken | `<var>x</var>` |
| `<abbr>` | Kısaltma | `<abbr title="HyperText Markup Language">HTML</abbr>` |
| `<cite>` | Alıntı kaynağı | `<cite>Kitap Adı</cite>` |
| `<q>` | Kısa alıntı | `<q>Alıntı metni</q>` |
| `<blockquote>` | Uzun alıntı | `<blockquote>Uzun alıntı</blockquote>` |
| `<address>` | Adres bilgisi | `<address>Adres</address>` |
| `<time>` | Tarih/saat | `<time datetime="2024-01-01">1 Ocak 2024</time>` |

---

## 🔗 BAĞLANTILAR VE GÖRSELLER

### Bağlantılar (Links)

```html
<!-- Dış bağlantı -->
<a href="https://example.com">Link Metni</a>
<a href="https://example.com" target="_blank">Yeni sekmede aç</a>

<!-- Sayfa içi bağlantı -->
<a href="#bölüm-id">Bölüme git</a>
<a href="sayfa.html#bölüm">Sayfa bölümüne git</a>

<!-- E-posta bağlantısı -->
<a href="mailto:email@example.com">E-posta gönder</a>

<!-- Telefon bağlantısı -->
<a href="tel:+905551234567">Telefon ara</a>

<!-- Dosya indirme -->
<a href="dosya.pdf" download>İndir</a>
```

**Özellikler:**
- `href` - Bağlantı adresi
- `target` - Açılma şekli (`_blank`, `_self`, `_parent`, `_top`)
- `download` - İndirme özelliği
- `rel` - İlişki (`nofollow`, `noopener`, `noreferrer`)

### Görseller (Images)

```html
<!-- Temel kullanım -->
<img src="resim.jpg" alt="Açıklama">

<!-- Boyutlandırma -->
<img src="resim.jpg" alt="Açıklama" width="300" height="200">

<!-- Responsive görsel -->
<img src="resim.jpg" alt="Açıklama" style="max-width: 100%; height: auto;">

<!-- Lazy loading -->
<img src="resim.jpg" alt="Açıklama" loading="lazy">

<!-- Picture elementi (responsive) -->
<picture>
    <source media="(min-width: 800px)" srcset="buyuk.jpg">
    <source media="(min-width: 400px)" srcset="orta.jpg">
    <img src="kucuk.jpg" alt="Açıklama">
</picture>
```

**Özellikler:**
- `src` - Görsel kaynağı
- `alt` - Alternatif metin (zorunlu)
- `width` / `height` - Boyutlar
- `loading` - Yükleme şekli (`lazy`, `eager`)
- `srcset` - Responsive görsel seti

---

## 📝 LİSTELER

### Sıralı Liste (Ordered List)

```html
<ol>
    <li>İtem 1</li>
    <li>İtem 2</li>
    <li>İtem 3</li>
</ol>

<!-- Özellikler -->
<ol type="1|A|a|I|i" start="5" reversed>
    <li>İtem</li>
</ol>
```

### Sırasız Liste (Unordered List)

```html
<ul>
    <li>İtem 1</li>
    <li>İtem 2</li>
    <li>İtem 3</li>
</ul>

<!-- İç içe liste -->
<ul>
    <li>Ana İtem
        <ul>
            <li>Alt İtem 1</li>
            <li>Alt İtem 2</li>
        </ul>
    </li>
</ul>
```

### Tanım Listesi (Definition List)

```html
<dl>
    <dt>Terim 1</dt>
    <dd>Açıklama 1</dd>
    <dt>Terim 2</dt>
    <dd>Açıklama 2</dd>
</dl>
```

---

## 📊 TABLOLAR

### Temel Tablo Yapısı

```html
<table>
    <caption>Tablo Başlığı</caption>
    <thead>
        <tr>
            <th>Başlık 1</th>
            <th>Başlık 2</th>
            <th>Başlık 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Veri 1</td>
            <td>Veri 2</td>
            <td>Veri 3</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Toplam</td>
            <td colspan="2">Sonuç</td>
        </tr>
    </tfoot>
</table>
```

### Tablo Birleştirme

```html
<!-- Colspan (sütun birleştirme) -->
<td colspan="2">İki sütun kaplar</td>

<!-- Rowspan (satır birleştirme) -->
<td rowspan="2">İki satır kaplar</td>

<!-- Örnek -->
<table>
    <tr>
        <th rowspan="2">Başlık</th>
        <th colspan="2">Alt Başlıklar</th>
    </tr>
    <tr>
        <th>Alt 1</th>
        <th>Alt 2</th>
    </tr>
</table>
```

**Tablo Özellikleri:**
- `<table>` - Tablo konteyneri
- `<caption>` - Tablo başlığı
- `<thead>` - Başlık bölümü
- `<tbody>` - Gövde bölümü
- `<tfoot>` - Alt bilgi bölümü
- `<tr>` - Satır
- `<th>` - Başlık hücresi
- `<td>` - Veri hücresi
- `colspan` - Sütun birleştirme
- `rowspan` - Satır birleştirme
- `scope` - Erişilebilirlik (`col`, `row`, `colgroup`, `rowgroup`)

---

## 📋 FORMLAR

### Form Yapısı

```html
<form action="/submit" method="POST" enctype="multipart/form-data">
    <!-- Form elemanları -->
    <button type="submit">Gönder</button>
</form>
```

**Form Özellikleri:**
- `action` - Gönderilecek URL
- `method` - HTTP metodu (`GET`, `POST`)
- `enctype` - Kodlama tipi (`application/x-www-form-urlencoded`, `multipart/form-data`)
- `novalidate` - Validasyonu devre dışı bırak
- `autocomplete` - Otomatik tamamlama (`on`, `off`)

### Input Tipleri

| Tip | Açıklama | Örnek |
|-----|----------|-------|
| `text` | Metin girişi | `<input type="text" name="isim">` |
| `email` | E-posta | `<input type="email" name="email">` |
| `password` | Şifre | `<input type="password" name="sifre">` |
| `number` | Sayı | `<input type="number" name="yas" min="1" max="100">` |
| `tel` | Telefon | `<input type="tel" name="telefon">` |
| `url` | URL | `<input type="url" name="website">` |
| `search` | Arama | `<input type="search" name="arama">` |
| `date` | Tarih | `<input type="date" name="tarih">` |
| `time` | Saat | `<input type="time" name="saat">` |
| `datetime-local` | Tarih-Saat | `<input type="datetime-local" name="tarihsaat">` |
| `month` | Ay | `<input type="month" name="ay">` |
| `week` | Hafta | `<input type="week" name="hafta">` |
| `color` | Renk | `<input type="color" name="renk">` |
| `range` | Aralık | `<input type="range" name="ses" min="0" max="100">` |
| `file` | Dosya | `<input type="file" name="dosya" accept="image/*">` |
| `checkbox` | Onay kutusu | `<input type="checkbox" name="onay" value="1">` |
| `radio` | Radyo butonu | `<input type="radio" name="cinsiyet" value="erkek">` |
| `submit` | Gönder | `<input type="submit" value="Gönder">` |
| `reset` | Sıfırla | `<input type="reset" value="Temizle">` |
| `button` | Buton | `<input type="button" value="Tıkla">` |
| `hidden` | Gizli | `<input type="hidden" name="id" value="123">` |

### Form Elemanları

```html
<!-- Label -->
<label for="isim">İsim:</label>
<input type="text" id="isim" name="isim">

<!-- Textarea -->
<label for="mesaj">Mesaj:</label>
<textarea id="mesaj" name="mesaj" rows="4" cols="50"></textarea>

<!-- Select (Dropdown) -->
<label for="sehir">Şehir:</label>
<select id="sehir" name="sehir">
    <option value="">Seçiniz...</option>
    <option value="istanbul">İstanbul</option>
    <option value="ankara" selected>Ankara</option>
    <option value="izmir">İzmir</option>
</select>

<!-- Optgroup -->
<select name="kategori">
    <optgroup label="Meyveler">
        <option value="elma">Elma</option>
        <option value="armut">Armut</option>
    </optgroup>
    <optgroup label="Sebzeler">
        <option value="domates">Domates</option>
        <option value="salatalik">Salatalık</option>
    </optgroup>
</select>

<!-- Datalist (Otomatik tamamlama) -->
<input list="sehirler" name="sehir">
<datalist id="sehirler">
    <option value="İstanbul">
    <option value="Ankara">
    <option value="İzmir">
</datalist>

<!-- Fieldset ve Legend -->
<fieldset>
    <legend>Kişisel Bilgiler</legend>
    <label for="ad">Ad:</label>
    <input type="text" id="ad" name="ad">
</fieldset>

<!-- Button -->
<button type="submit">Gönder</button>
<button type="reset">Temizle</button>
<button type="button">Tıkla</button>
```

### Form Özellikleri ve Validasyon

```html
<!-- Zorunlu alan -->
<input type="text" name="isim" required>

<!-- Placeholder -->
<input type="text" name="isim" placeholder="Adınızı girin">

<!-- Min/Max (sayı, tarih) -->
<input type="number" name="yas" min="18" max="65">
<input type="date" name="tarih" min="2024-01-01" max="2024-12-31">

<!-- Minlength/Maxlength (metin) -->
<input type="text" name="isim" minlength="2" maxlength="50">

<!-- Pattern (regex) -->
<input type="text" name="telefon" pattern="[0-9]{10}">

<!-- Autocomplete -->
<input type="email" name="email" autocomplete="email">
<input type="password" name="sifre" autocomplete="current-password">

<!-- Disabled -->
<input type="text" name="isim" disabled>

<!-- Readonly -->
<input type="text" name="isim" readonly value="Değiştirilemez">

<!-- Autofocus -->
<input type="text" name="isim" autofocus>

<!-- Multiple (select, file) -->
<select name="sehirler" multiple>
    <option value="istanbul">İstanbul</option>
    <option value="ankara">Ankara</option>
</select>
<input type="file" name="dosyalar" multiple>
```

---

## 🎨 HTML5 SEMANTIC ETİKETLER

```html
<!-- Sayfa yapısı -->
<header>
    <h1>Site Başlığı</h1>
    <nav>
        <ul>
            <li><a href="#anasayfa">Ana Sayfa</a></li>
            <li><a href="#hakkimda">Hakkımda</a></li>
        </ul>
    </nav>
</header>

<main>
    <article>
        <header>
            <h2>Makale Başlığı</h2>
            <p>Yazar: <span>Ad Soyad</span></p>
        </header>
        <section>
            <h3>Bölüm 1</h3>
            <p>İçerik...</p>
        </section>
        <section>
            <h3>Bölüm 2</h3>
            <p>İçerik...</p>
        </section>
        <footer>
            <p>Yayın tarihi: <time datetime="2024-01-01">1 Ocak 2024</time></p>
        </footer>
    </article>
    
    <aside>
        <h3>İlgili Bağlantılar</h3>
        <ul>
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
        </ul>
    </aside>
</main>

<footer>
    <p>&copy; 2024 Tüm hakları saklıdır.</p>
</footer>
```

**Semantic Etiketler:**
- `<header>` - Başlık bölümü
- `<nav>` - Navigasyon menüsü
- `<main>` - Ana içerik (sayfada 1 kez)
- `<article>` - Bağımsız içerik (makale, blog yazısı)
- `<section>` - İçerik bölümü
- `<aside>` - Yan içerik (sidebar)
- `<footer>` - Alt bilgi
- `<figure>` - Medya içeriği konteyneri
- `<figcaption>` - Medya açıklaması
- `<mark>` - Vurgulanmış metin
- `<time>` - Tarih/saat
- `<details>` - Açılır/kapanır içerik
- `<summary>` - Details başlığı

---

## 🎬 MEDYA ETİKETLERİ

### Video

```html
<!-- Temel video -->
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Tarayıcınız video oynatmayı desteklemiyor.
</video>

<!-- Otomatik oynatma -->
<video autoplay muted loop>
    <source src="video.mp4" type="video/mp4">
</video>

<!-- Poster (önizleme) -->
<video controls poster="onizleme.jpg">
    <source src="video.mp4" type="video/mp4">
</video>
```

**Video Özellikleri:**
- `controls` - Kontrolleri göster
- `autoplay` - Otomatik oynat
- `muted` - Sessiz
- `loop` - Döngü
- `poster` - Önizleme görseli
- `preload` - Ön yükleme (`none`, `metadata`, `auto`)
- `width` / `height` - Boyutlar

### Ses (Audio)

```html
<!-- Temel ses -->
<audio controls>
    <source src="ses.mp3" type="audio/mpeg">
    <source src="ses.ogg" type="audio/ogg">
    Tarayıcınız ses oynatmayı desteklemiyor.
</audio>

<!-- Otomatik oynatma -->
<audio autoplay loop>
    <source src="ses.mp3" type="audio/mpeg">
</audio>
```

**Ses Özellikleri:**
- `controls` - Kontrolleri göster
- `autoplay` - Otomatik oynat
- `loop` - Döngü
- `muted` - Sessiz
- `preload` - Ön yükleme

### iframe (Gömülü İçerik)

```html
<!-- YouTube video -->
<iframe width="560" height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        frameborder="0" 
        allowfullscreen>
</iframe>

<!-- Harita -->
<iframe src="https://www.google.com/maps/embed?..." 
        width="600" 
        height="450" 
        style="border:0;" 
        allowfullscreen>
</iframe>
```

**iframe Özellikleri:**
- `src` - Kaynak URL
- `width` / `height` - Boyutlar
- `frameborder` - Çerçeve kenarlığı
- `allowfullscreen` - Tam ekran izni
- `sandbox` - Güvenlik kısıtlamaları
- `loading` - Yükleme şekli (`lazy`)

---

## 🔧 GLOBAL ATTRIBUTES (Global Özellikler)

Tüm HTML etiketlerinde kullanılabilen özellikler:

| Özellik | Açıklama | Örnek |
|---------|----------|-------|
| `id` | Benzersiz kimlik | `<div id="container">` |
| `class` | CSS sınıfı | `<div class="box primary">` |
| `style` | Satır içi CSS | `<div style="color: red;">` |
| `title` | Tooltip metni | `<div title="Açıklama">` |
| `lang` | Dil kodu | `<div lang="tr">` |
| `dir` | Yazı yönü | `<div dir="rtl">` |
| `data-*` | Özel veri | `<div data-user="123">` |
| `hidden` | Gizle | `<div hidden>` |
| `tabindex` | Sekme sırası | `<div tabindex="1">` |
| `contenteditable` | Düzenlenebilir | `<div contenteditable>` |
| `draggable` | Sürüklenebilir | `<div draggable="true">` |
| `spellcheck` | Yazım kontrolü | `<input spellcheck="true">` |
| `translate` | Çeviri | `<div translate="no">` |
| `accesskey` | Klavye kısayolu | `<button accesskey="s">` |

---

## 📱 META ETİKETLERİ

### Temel Meta Etiketleri

```html
<!-- Karakter kodlaması -->
<meta charset="UTF-8">

<!-- Viewport (Responsive) -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Sayfa açıklaması -->
<meta name="description" content="Sayfa açıklaması">

<!-- Anahtar kelimeler -->
<meta name="keywords" content="anahtar, kelimeler, liste">

<!-- Yazar -->
<meta name="author" content="Yazar Adı">

<!-- Robots (SEO) -->
<meta name="robots" content="index, follow">
<meta name="robots" content="noindex, nofollow">

<!-- Open Graph (Sosyal medya) -->
<meta property="og:title" content="Sayfa Başlığı">
<meta property="og:description" content="Açıklama">
<meta property="og:image" content="resim.jpg">
<meta property="og:url" content="https://example.com">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="Başlık">
<meta name="twitter:description" content="Açıklama">

<!-- Theme Color -->
<meta name="theme-color" content="#667eea">

<!-- Refresh (Yönlendirme) -->
<meta http-equiv="refresh" content="5;url=https://example.com">
```

---

## 🎯 YORUMLAR

```html
<!-- Tek satır yorum -->
<!-- Bu bir yorumdur -->

<!-- Çok satırlı yorum -->
<!-- 
    Bu çok satırlı
    bir yorumdur
-->

<!-- Koşullu yorumlar (IE için) -->
<!--[if IE]>
    <p>Internet Explorer için içerik</p>
<![endif]-->
```

---

## 🗂️ DİĞER ETİKETLER

### Div ve Span

```html
<!-- Block element -->
<div class="container">
    <p>İçerik</p>
</div>

<!-- Inline element -->
<span class="highlight">Vurgu</span>
```

### Script ve Style

```html
<!-- CSS -->
<style>
    body { color: #333; }
</style>

<!-- JavaScript -->
<script>
    console.log('Merhaba');
</script>

<!-- Harici dosya -->
<link rel="stylesheet" href="style.css">
<script src="script.js"></script>

<!-- Async/Defer -->
<script src="script.js" async></script>
<script src="script.js" defer></script>
```

### Link Etiketleri

```html
<!-- CSS dosyası -->
<link rel="stylesheet" href="style.css">

<!-- Favicon -->
<link rel="icon" href="favicon.ico" type="image/x-icon">

<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="icon.png">

<!-- Canonical URL -->
<link rel="canonical" href="https://example.com/sayfa">

<!-- Alternatif dil -->
<link rel="alternate" hreflang="en" href="https://example.com/en">
```

---

## ⚡ HIZLI İPUÇLARI VE EN İYİ UYGULAMALAR

### ✅ Yapılması Gerekenler

- ✅ Her zaman `<!doctype html>` ile başla
- ✅ `lang` özelliğini kullan (`lang="tr"`)
- ✅ Görsellere `alt` özelliği ekle (erişilebilirlik)
- ✅ Form alanlarına `label` ekle
- ✅ Semantic HTML5 etiketlerini tercih et
- ✅ Meta etiketlerini unutma (viewport, description)
- ✅ Responsive tasarım için viewport meta etiketi kullan
- ✅ Form validasyonu için `required`, `pattern` kullan
- ✅ Tablolarda `scope` özelliği kullan (erişilebilirlik)
- ✅ Bağlantılarda `rel="noopener"` kullan (güvenlik)

### ❌ Yapılmaması Gerekenler

- ❌ `<h1>` etiketini birden fazla kullanma (SEO)
- ❌ Görsellerde `alt` özelliğini unutma
- ❌ Form alanlarını `label` olmadan kullanma
- ❌ `<div>` yerine semantic etiketleri tercih et
- ❌ Inline stilleri aşırı kullanma
- ❌ Eski HTML etiketlerini kullanma (`<font>`, `<center>`)
- ❌ Tabloları layout için kullanma (CSS kullan)

---

## 🔍 HIZLI ARAMA

### Yaygın Kullanımlar

**Başlık hiyerarşisi:**
```html
<h1>Ana Başlık (1 kez)</h1>
<h2>Bölüm Başlığı</h2>
<h3>Alt Bölüm</h3>
```

**Form validasyonu:**
```html
<input type="email" required pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$">
```

**Responsive görsel:**
```html
<img src="resim.jpg" alt="Açıklama" style="max-width: 100%; height: auto;">
```

**Sayfa içi link:**
```html
<a href="#bölüm-id">Bölüme git</a>
<section id="bölüm-id">İçerik</section>
```

---

## 📚 EK KAYNAKLAR

- [MDN Web Docs](https://developer.mozilla.org/tr/docs/Web/HTML)
- [W3Schools HTML](https://www.w3schools.com/html/)
- [HTML Living Standard](https://html.spec.whatwg.org/)

---

**Son Güncelleme:** 2024

---

## ✍️ Yazar

**Bahadır B. Bekdemir**
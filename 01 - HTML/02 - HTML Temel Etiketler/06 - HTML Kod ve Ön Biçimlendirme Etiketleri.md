# 💻 HTML KOD VE ÖN BİÇİMLENDİRME ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) kod, komut ve önceden biçimlendirilmiş metinleri göstermek için kullanılan etiketler bulunmaktadır.

## 📋 Kod Etiketleri

### `<code>...</code>`

Tek satırlık kod parçacıklarını göstermek için kullanılır. Varsayılan olarak monospace (eş aralıklı) font ile görüntülenir.

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Code Örneği</title>
</head>
<body>
    <p>HTML etiketi şu şekilde yazılır: <code>&lt;div&gt;</code></p>
    <p>JavaScript'te değişken tanımlama: <code>var x = 10;</code></p>
    <p>CSS özelliği: <code>color: red;</code></p>
</body>
</html>
```

### `<pre>...</pre>`

Önceden biçimlendirilmiş metinleri göstermek için kullanılır. İçindeki boşluklar, satır sonları ve girintiler korunur. Genellikle kod blokları için kullanılır.

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Pre Örneği</title>
</head>
<body>
    <pre>
        function merhaba() {
            console.log("Merhaba Dünya!");
        }
    </pre>
</body>
</html>
```

### `<kbd>...</kbd>`

Klavye tuşlarını veya kullanıcı girişlerini göstermek için kullanılır.

**Kullanım örneği:**
```html
<p>Sayfayı yenilemek için <kbd>Ctrl</kbd> + <kbd>R</kbd> tuşlarına basın.</p>
<p>Kopyalamak için <kbd>Ctrl</kbd> + <kbd>C</kbd> tuşlarına basın.</p>
```

### `<samp>...</samp>`

Program çıktılarını veya örnek metinleri göstermek için kullanılır.

**Kullanım örneği:**
```html
<p>Program çıktısı: <samp>İşlem başarıyla tamamlandı.</samp></p>
```

### `<var>...</var>`

Değişken isimlerini göstermek için kullanılır. Genellikle italik görüntülenir.

**Kullanım örneği:**
```html
<p>Değişken <var>x</var> değeri 10'dur.</p>
```

## 💡 Kapsamlı Örnekler

### Kod Gösterimi Örnekleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kod Gösterimi Örnekleri</title>
    <style>
        code {
            background-color: #f4f4f4;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: 'Courier New', monospace;
            color: #e74c3c;
        }
        
        pre {
            background-color: #2c3e50;
            color: #ecf0f1;
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
        }
        
        pre code {
            background-color: transparent;
            color: inherit;
            padding: 0;
        }
        
        kbd {
            background-color: #34495e;
            color: #ecf0f1;
            padding: 3px 8px;
            border-radius: 3px;
            font-family: 'Courier New', monospace;
            box-shadow: 0 2px 0 #1a252f;
        }
        
        samp {
            background-color: #27ae60;
            color: white;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: 'Courier New', monospace;
        }
        
        var {
            font-style: italic;
            color: #3498db;
            font-family: 'Courier New', monospace;
        }
    </style>
</head>
<body>
    <h1>Kod ve Ön Biçimlendirme Etiketleri</h1>
    
    <h2>Tek Satırlık Kod (code)</h2>
    <p>HTML etiketi: <code>&lt;div&gt;</code></p>
    <p>JavaScript değişkeni: <code>var isim = "Ahmet";</code></p>
    <p>CSS özelliği: <code>background-color: #3498db;</code></p>
    <p>Python fonksiyonu: <code>print("Merhaba")</code></p>
    
    <h2>Kod Blokları (pre + code)</h2>
    
    <h3>HTML Örneği</h3>
    <pre><code>&lt;!doctype html&gt;
&lt;html lang="tr"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;title&gt;Örnek&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;Merhaba Dünya&lt;/h1&gt;
&lt;/body&gt;
&lt;/html&gt;</code></pre>
    
    <h3>JavaScript Örneği</h3>
    <pre><code>function topla(a, b) {
    return a + b;
}

var sonuc = topla(5, 3);
console.log(sonuc); // 8</code></pre>
    
    <h3>CSS Örneği</h3>
    <pre><code>body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
    background-color: #f4f4f4;
}

h1 {
    color: #2c3e50;
    text-align: center;
}</code></pre>
    
    <h2>Klavye Tuşları (kbd)</h2>
    <p>Sayfayı yenilemek için <kbd>Ctrl</kbd> + <kbd>R</kbd> tuşlarına basın.</p>
    <p>Kopyalamak için <kbd>Ctrl</kbd> + <kbd>C</kbd> tuşlarına basın.</p>
    <p>Yapıştırmak için <kbd>Ctrl</kbd> + <kbd>V</kbd> tuşlarına basın.</p>
    <p>Kaydetmek için <kbd>Ctrl</kbd> + <kbd>S</kbd> tuşlarına basın.</p>
    <p>Geri almak için <kbd>Ctrl</kbd> + <kbd>Z</kbd> tuşlarına basın.</p>
    
    <h2>Program Çıktıları (samp)</h2>
    <p>Konsol çıktısı: <samp>İşlem başarıyla tamamlandı.</samp></p>
    <p>Hata mesajı: <samp>Hata: Dosya bulunamadı.</samp></p>
    <p>Başarı mesajı: <samp>Kayıt başarıyla eklendi.</samp></p>
    
    <h2>Değişkenler (var)</h2>
    <p>Değişken <var>x</var> değeri 10'dur.</p>
    <p>Fonksiyon parametresi: <var>isim</var></p>
    <p>Matematik formülü: <var>a</var> + <var>b</var> = <var>c</var></p>
    
    <h2>Kombine Kullanım</h2>
    <p>
        <code>console.log()</code> fonksiyonu konsola mesaj yazdırır. 
        Örnek: <code>console.log("Merhaba");</code> 
        Çıktı: <samp>Merhaba</samp>
    </p>
    
    <p>
        Değişken <var>sonuc</var> değerini görmek için 
        <kbd>F12</kbd> tuşuna basıp konsolu açın.
    </p>
    
    <pre><code>// Değişken tanımlama
var <var>isim</var> = "Ahmet";
var <var>yas</var> = 25;

// Konsola yazdırma
console.log(<var>isim</var>); // Çıktı: <samp>Ahmet</samp>
console.log(<var>yas</var>);  // Çıktı: <samp>25</samp></code></pre>
</body>
</html>
```

### Syntax Highlighting ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Syntax Highlighting</title>
    <style>
        .code-block {
            background-color: #1e1e1e;
            color: #d4d4d4;
            padding: 20px;
            border-radius: 5px;
            overflow-x: auto;
            font-family: 'Consolas', 'Monaco', monospace;
            line-height: 1.6;
        }
        
        .keyword { color: #569cd6; }
        .string { color: #ce9178; }
        .comment { color: #6a9955; }
        .function { color: #dcdcaa; }
        .number { color: #b5cea8; }
    </style>
</head>
<body>
    <h1>Syntax Highlighting Örneği</h1>
    
    <pre class="code-block"><code><span class="comment">// JavaScript örneği</span>
<span class="keyword">function</span> <span class="function">merhaba</span>(<span class="keyword">var</span> <span class="string">isim</span>) {
    <span class="keyword">return</span> <span class="string">"Merhaba "</span> + <span class="string">isim</span>;
}

<span class="keyword">var</span> <span class="string">mesaj</span> = <span class="function">merhaba</span>(<span class="string">"Dünya"</span>);
<span class="function">console.log</span>(<span class="string">mesaj</span>); <span class="comment">// Çıktı: Merhaba Dünya</span></code></pre>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **code vs pre**: `<code>` tek satırlık kod için, `<pre>` çok satırlı kod blokları için kullanılır.

2. **Özel Karakterler**: HTML'de `<`, `>`, `&` gibi özel karakterler `&lt;`, `&gt;`, `&amp;` şeklinde yazılmalıdır.

3. **Monospace Font**: Kod etiketleri varsayılan olarak monospace font kullanır, ancak **CSS** ile değiştirilebilir.

4. **Boşluklar**: `<pre>` etiketi içindeki boşluklar ve satır sonları korunur.

5. **Erişilebilirlik**: Ekran okuyucular bu etiketleri kod olarak algılar.

## 🎯 İyi Pratikler

- Tek satırlık kod için `<code>` kullanın
- Çok satırlı kod blokları için `<pre><code>` kombinasyonunu kullanın
- Klavye tuşları için `<kbd>` kullanın
- Program çıktıları için `<samp>` kullanın
- Değişken isimleri için `<var>` kullanın
- Özel karakterleri doğru şekilde escape edin (`&lt;`, `&gt;`, `&amp;`)
- Kod bloklarının stilini **CSS** ile özelleştirin
- Uzun kod satırları için `overflow-x: auto` kullanın

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


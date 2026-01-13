# 📖 HTML ALINTI VE ATIF ETİKETLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) alıntılar, atıflar ve kısaltmalar için kullanılan etiketler bulunmaktadır.

## 📋 Alıntı Etiketleri

### `<blockquote>...</blockquote>`

Uzun alıntılar için kullanılır. Genellikle girintili olarak görüntülenir.

**Kullanım örneği:**
```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Blockquote Örneği</title>
</head>
<body>
    <p>Einstein şöyle demiştir:</p>
    <blockquote>
        Hayal gücü bilgiden daha önemlidir. Bilgi sınırlıdır, 
        oysa hayal gücü tüm dünyayı kapsar.
    </blockquote>
</body>
</html>
```

### `<q>...</q>`

Kısa alıntılar için kullanılır. Genellikle tırnak işaretleri ile görüntülenir.

**Kullanım örneği:**
```html
<p>Atatürk şöyle demiştir: <q>Yurtta sulh, cihanda sulh.</q></p>
```

### `<cite>...</cite>`

Eser, kitap, makale gibi kaynakların adını belirtmek için kullanılır. Genellikle italik görüntülenir.

**Kullanım örneği:**
```html
<p>Bu alıntı <cite>Suç ve Ceza</cite> kitabından alınmıştır.</p>
```

### `<abbr>...</abbr>`

Kısaltmalar için kullanılır. `title` özelliği ile açıklama eklenebilir.

**Kullanım örneği:**
```html
<p><abbr title="Hyper Text Markup Language">HTML</abbr> web sayfaları oluşturmak için kullanılır.</p>
<p><abbr title="World Wide Web">WWW</abbr> dünya çapında ağ anlamına gelir.</p>
```

## 💡 Kapsamlı Örnekler

### Alıntı Örnekleri

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Alıntı Örnekleri</title>
    <style>
        blockquote {
            border-left: 4px solid #3498db;
            padding-left: 20px;
            margin: 20px 0;
            font-style: italic;
            color: #555;
        }
        
        q {
            quotes: """ """ "'" "'";
            font-style: italic;
        }
        
        cite {
            font-style: italic;
            color: #7f8c8d;
        }
        
        abbr {
            text-decoration: underline dotted;
            cursor: help;
        }
    </style>
</head>
<body>
    <h1>Alıntı ve Atıf Örnekleri</h1>
    
    <h2>Uzun Alıntı (blockquote)</h2>
    <p>Albert Einstein'ın ünlü sözü:</p>
    <blockquote>
        Hayal gücü bilgiden daha önemlidir. Bilgi sınırlıdır, 
        oysa hayal gücü tüm dünyayı kapsar. Hayal gücü ilerlemenin 
        kaynağıdır ve bilimsel gelişmelerin temelidir.
    </blockquote>
    
    <h2>Kısa Alıntı (q)</h2>
    <p>Atatürk şöyle demiştir: <q>Yurtta sulh, cihanda sulh.</q></p>
    <p>Shakespeare'in ünlü sözü: <q>Olmak ya da olmamak, işte bütün mesele bu.</q></p>
    
    <h2>Kaynak Atfı (cite)</h2>
    <p>Bu alıntı <cite>Suç ve Ceza</cite> kitabından alınmıştır.</p>
    <p>Şu makale <cite>Web Geliştirme Dergisi</cite> dergisinde yayınlanmıştır.</p>
    
    <blockquote cite="https://example.com/kaynak">
        Bu alıntı bir web sitesinden alınmıştır.
    </blockquote>
    <p>Kaynak: <cite>https://example.com/kaynak</cite></p>
    
    <h2>Kısaltmalar (abbr)</h2>
    <p><abbr title="Hyper Text Markup Language">HTML</abbr> web sayfaları oluşturmak için kullanılır.</p>
    <p><abbr title="Cascading Style Sheets">CSS</abbr> web sayfalarının stilini belirler.</p>
    <p><abbr title="JavaScript">JS</abbr> web sayfalarına etkileşim ekler.</p>
    <p><abbr title="World Wide Web">WWW</abbr> dünya çapında ağ anlamına gelir.</p>
    <p><abbr title="Hypertext Transfer Protocol">HTTP</abbr> web'de veri iletişimi için kullanılır.</p>
    <p><abbr title="Hypertext Transfer Protocol Secure">HTTPS</abbr> güvenli web iletişimi sağlar.</p>
</body>
</html>
```

### Kombine Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Kombine Alıntı Örneği</title>
    <style>
        blockquote {
            border-left: 4px solid #e74c3c;
            padding: 15px 20px;
            margin: 20px 0;
            background-color: #f8f9fa;
        }
        
        .author {
            text-align: right;
            margin-top: 10px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <article>
        <h1>Ünlü Sözler</h1>
        
        <section>
            <h2>Bilim İnsanları</h2>
            
            <blockquote cite="https://example.com/einstein">
                <p>Hayal gücü bilgiden daha önemlidir. Bilgi sınırlıdır, 
                oysa hayal gücü tüm dünyayı kapsar.</p>
                <p class="author">— Albert Einstein</p>
            </blockquote>
            
            <blockquote>
                <p>İki şey sonsuzdur: Evren ve insanın aptallığı. 
                Evrenden emin değilim ama.</p>
                <p class="author">— Albert Einstein</p>
            </blockquote>
        </section>
        
        <section>
            <h2>Edebiyat</h2>
            
            <p>Dostoyevski'nin <cite>Suç ve Ceza</cite> kitabından:</p>
            <blockquote>
                <p>İnsan her şeye alışır, bu en kötü şeydir.</p>
            </blockquote>
            
            <p>Shakespeare'in <cite>Hamlet</cite> eserinden:</p>
            <blockquote>
                <q>Olmak ya da olmamak, işte bütün mesele bu.</q>
            </blockquote>
        </section>
        
        <section>
            <h2>Teknoloji Terimleri</h2>
            <p>
                <abbr title="Hyper Text Markup Language">HTML</abbr>, 
                <abbr title="Cascading Style Sheets">CSS</abbr> ve 
                <abbr title="JavaScript">JS</abbr> web geliştirmenin 
                temel teknolojileridir.
            </p>
            <p>
                <abbr title="Application Programming Interface">API</abbr> 
                uygulamalar arası iletişimi sağlar.
            </p>
        </section>
    </article>
</body>
</html>
```

### cite Özelliği ile Kullanım

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>cite Özelliği</title>
</head>
<body>
    <article>
        <h1>Makale Başlığı</h1>
        
        <p>Makale içeriği burada yer alır...</p>
        
        <blockquote cite="https://www.example.com/kaynak">
            Bu alıntı başka bir kaynaktan alınmıştır.
        </blockquote>
        
        <p>
            Daha fazla bilgi için: 
            <cite><a href="https://www.example.com/kaynak">Kaynak</a></cite>
        </p>
        
        <p>
            <q cite="https://www.example.com/alinti">
                Bu kısa alıntı da bir kaynaktan alınmıştır.
            </q>
        </p>
    </article>
</body>
</html>
```

## ⚠️ Önemli Notlar

1. **blockquote vs q**: `<blockquote>` uzun alıntılar için, `<q>` kısa alıntılar için kullanılır.

2. **cite Özelliği**: Hem `<blockquote>` hem de `<q>` etiketlerinde `cite` özelliği ile kaynak URL'si belirtilebilir.

3. **Erişilebilirlik**: `<abbr>` etiketinde `title` özelliği kullanıldığında, fare ile üzerine gelindiğinde açıklama görüntülenir.

4. **Anlamsal HTML**: Bu etiketler anlamsal HTML'in bir parçasıdır ve **SEO** açısından önemlidir.

5. **Stil**: Bu etiketlerin görünümü **CSS** ile özelleştirilebilir.

## 🎯 İyi Pratikler

- Uzun alıntılar için `<blockquote>` kullanın
- Kısa alıntılar için `<q>` kullanın
- Kaynak belirtmek için `<cite>` kullanın
- Kısaltmalar için `<abbr>` ve `title` özelliğini kullanın
- `cite` özelliği ile kaynak URL'si ekleyin
- Anlamsal HTML kullanarak **SEO**'yu iyileştirin

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


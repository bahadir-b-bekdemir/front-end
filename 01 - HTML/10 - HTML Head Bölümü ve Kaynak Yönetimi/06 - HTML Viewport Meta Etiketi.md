# 📱 HTML'İN META TAG'I (ETİKETİ) İÇERİSİNDE VIEWPORT (GÖRÜNÜR ALAN) KULLANIMI

**HTML**'in (Hyper Text Markup Language) (zengin metin işaretleme diline) meta tag'ı (etiketi) içerisinde viewport (görünür alan) değeri kullanarak web sayfasının görünür alanını, kullanıcının kullandığı browser'ın (tarayıcının) görünür alanı olarak tanımlamak mümkündür. Görünür alan, kullanıcının cihazına göre değişiklik gösterebilir. Örneğin; Bir akıllı telefonun görünür alanı farklı, bir tabletin görünür alanı farklı ve bir bilgisayarın görünür alanı farklı olabilir.

Akıllı telefonlardan ve tabletlerden önce, bir web sayfası sadece bilgisayarlar için tasarlanmaktaydı ve static (sabit) tasarımı ve boyutları vardı. Fakat günümüzde artık farklı farklı cihazlardan web sayfaları görüntülenebildiği için bu durum fazlasıyla değişti ve responsive (duyarlı) tasarımlar yaygın hale geldi. Çünkü bir bilgisayar için hazırlanmış olan web sayfası tasarımı, akıllı telefon ve tabletlere sığmayacak kadar büyüktü. Fakat CSS (Cascading Style Sheets) (basamaklı stil şablonları veya basamaklı biçim sayfaları) sayesinde, tüm cihazlarda web sayfaları için sorunsuz ve kusursuz bir görünüm sağlanabilmektedir.

Viewport'un (Görünür alanın) amacı, mobil browser'lardaki (tarayıcılardaki) tasarım düzenini sağlamaktır. Aynı zamanda ölçeklendirme işlemleri de yapılabilmesine olanak sağlar.

Web sayfası tasarımının genişlik ve yükseklik değerini mobil browser'a (tarayıcıya) bildirmek, mobil browser'da da (tarayıcıda da) web sayfasının aynı görünmesini sağlar. Eğer viewport (görünür alan) değeri kullanılmayacak olur ise, küçük ekranlarda kullanılan browser'lar (tarayıcılar), web sayfasını ekrana sığacak şekilde daraltır ve aynı zamanda yazı boyutunu değiştirirler. Bu durum ise son derece kötü bir görüntü sunar. Örneğin; Büyük ekranlı bir cihaz için tasarlanmış bir web sayfası, küçük ekranlı bir cihaz için daraltılacak ve yazılar okunamayacak kadar küçültülecektir. Kullanıcı yazı, resim vb. materyalleri görebilmek için yakınlaştırmak zorunda kalacaktır.

## 📍 Viewport Meta Etiketi Nereye Yerleştirilir?

Viewport meta etiketi **`<head>` bölümüne** yerleştirilmelidir ve **`<meta charset="UTF-8">` etiketinden hemen sonra** gelmelidir.

### ✅ Doğru Yerleşim

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sayfa Başlığı</title>
    <!-- Diğer meta etiketleri ve kaynaklar -->
</head>
<body>
    <!-- İçerik -->
</body>
</html>
```

### ❌ Yanlış Yerleşim

```html
<!-- YANLIŞ: Viewport body içinde -->
<body>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</body>

<!-- YANLIŞ: Viewport charset'ten önce -->
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta charset="UTF-8">
</head>
```

## 📋 Viewport Parametreleri ve Özellikleri

HTML'in (Hyper Text Markup Language) (zengin metin işaretleme diline) meta tag'ı (etiketi) içerisinde viewport (görünür alan) değerinin özellikleri için kullanılan değerler:

| Attribute (Özellik) | Value (Değer) | Description (Tanım) | Standart Value (Standart değer) |
| :------------------ | :------------ | :------------------ | :------------------------------ |
| `width` | `device-width`<br>pixel değer | Genişlik değeridir. Tanımlanan genişlik değerine göre web sayfası browser'da (tarayıcıda) görüntülenir. | `device-width` |
| `height` | `device-height`<br>pixel değer | Yükseklik değeridir. Tanımlanan yükseklik değerine göre web sayfası browser'da (tarayıcıda) görüntülenir. | `device-height` |
| `initial-scale` | `0.1 - 10.0` | Zoom (Yakınlaştırma) seviyesi değeridir. Tanımlanan zoom (yakınlaştırma) seviyesi değerine göre web sayfası ilk yüklendiğinde browser'da (tarayıcıda) görüntülenir. | `1.0` |
| `minimum-scale` | `0.1 - 10.0` | Kullanıcının yapabileceği minimum (en az) zoom (yakınlaştırma) seviyesi değeridir. Tanımlanan minimum (en az) zoom (yakınlaştırma) seviyesi değerine göre kullanıcı web sayfasına zoom (yakınlaştırma) yapabilir. | `0.1` |
| `maximum-scale` | `0.1 - 10.0` | Kullanıcının yapabileceği maximum (en çok) zoom (yakınlaştırma) seviyesi değeridir. Tanımlanan maximum (en çok) zoom (yakınlaştırma) seviyesi değerine göre kullanıcı web sayfasına zoom (yakınlaştırma) yapabilir. | `10.0` |
| `user-scalable` | `yes` veya `no` | Kullanıcının zoom (yakınlaştırma) yapabilme yetkisi değeridir. Tanımlanan değere göre kullanıcı web sayfasına zoom (yakınlaştırma) yapabilir yada yapamaz. | `yes` |
| `target-densitydpi` | `device-dpi`<br>`low-dpi`<br>`medium-dpi`<br>`high-dpi` | DPI (Dots per inch) (inç başına nokta sayısı) değeridir. Tanımlanan değere göre web sayfası kullanıcının browser'ında (tarayıcısında) görüntülenir. | `device-dpi` |

## 💡 Kullanım Örnekleri

### Standart Viewport (Önerilen)

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Sayfa</title>
</head>
<body>
    <h1>Mobil Uyumlu Sayfa</h1>
</body>
</html>
```

### Gelişmiş Viewport Ayarları

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title>Gelişmiş Viewport</title>
</head>
<body>
    <h1>Yakınlaştırma İzinli Sayfa</h1>
</body>
</html>
```

### Sabit Genişlik Viewport

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=1024">
    <title>Sabit Genişlik</title>
</head>
<body>
    <h1>1024px Genişlikte Sayfa</h1>
</body>
</html>
```

### Yakınlaştırma Devre Dışı

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Yakınlaştırma Devre Dışı</title>
</head>
<body>
    <h1>Sabit Yakınlaştırma Seviyesi</h1>
</body>
</html>
```

### Minimum ve Maksimum Yakınlaştırma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=0.5, maximum-scale=3.0">
    <title>Kontrollü Yakınlaştırma</title>
</head>
<body>
    <h1>0.5x - 3.0x Arası Yakınlaştırma</h1>
</body>
</html>
```

## 🔍 Viewport Parametre Detayları

### width Parametresi

```html
<!-- Cihaz genişliğine göre ayarla (ÖNERİLEN) -->
<meta name="viewport" content="width=device-width">

<!-- Sabit genişlik -->
<meta name="viewport" content="width=1024">

<!-- Minimum genişlik -->
<meta name="viewport" content="width=320">
```

### initial-scale Parametresi

```html
<!-- Normal görünüm (100%) -->
<meta name="viewport" content="initial-scale=1.0">

<!-- %50 yakınlaştırma -->
<meta name="viewport" content="initial-scale=0.5">

<!-- %200 yakınlaştırma -->
<meta name="viewport" content="initial-scale=2.0">
```

### user-scalable Parametresi

```html
<!-- Yakınlaştırma izinli (ÖNERİLEN) -->
<meta name="viewport" content="user-scalable=yes">

<!-- Yakınlaştırma devre dışı -->
<meta name="viewport" content="user-scalable=no">
```

### maximum-scale ve minimum-scale

```html
<!-- Maksimum 5x yakınlaştırma -->
<meta name="viewport" content="maximum-scale=5.0">

<!-- Minimum 0.5x yakınlaştırma -->
<meta name="viewport" content="minimum-scale=0.5">

<!-- Her ikisi birlikte -->
<meta name="viewport" content="minimum-scale=0.5, maximum-scale=3.0">
```

## ⚠️ Önemli Notlar

1. **Viewport etiketi olmadan**: Mobil cihazlarda sayfa masaüstü görünümünde gösterilir ve kullanıcı yatay kaydırma yapmak zorunda kalır.

2. **`width=device-width`**: Cihazın ekran genişliğine göre sayfayı ayarlar, responsive tasarım için kritiktir.

3. **`initial-scale=1.0`**: Sayfanın başlangıç yakınlaştırma seviyesini %100 olarak ayarlar.

4. **`user-scalable=no`**: Erişilebilirlik açısından önerilmez, kullanıcıların yakınlaştırma yapmasını engeller.

5. **Viewport etiketi yalnızca bir kez kullanılmalıdır**, birden fazla viewport etiketi kullanıldığında sonuncusu geçerli olur.

6. **`target-densitydpi`**: Bu özellik artık kullanımdan kaldırılmıştır (deprecated) ve modern tarayıcılarda desteklenmemektedir.

## 🎯 İyi Pratikler

- ✅ Her zaman `<meta charset="UTF-8">` etiketinden hemen sonra yerleştirin
- ✅ `width=device-width` kullanın
- ✅ `initial-scale=1.0` ayarlayın
- ✅ `user-scalable=yes` kullanarak erişilebilirliği koruyun
- ✅ Maksimum yakınlaştırmayı çok düşük tutmayın (erişilebilirlik için)
- ❌ `user-scalable=no` kullanmaktan kaçının (erişilebilirlik sorunları yaratır)
- ❌ `target-densitydpi` kullanmaktan kaçının (artık desteklenmiyor)

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

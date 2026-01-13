# 🏗️ HTML'İN MUTLAK ŞARTI VE ANA ETİKETLERİ

Bir **HTML** (Hyper Text Markup Language) (zengin metin işaretleme dili) dokümanında muhakkak olması gereken **tag'lar (etiketler)** vardır. Bu tag'lar (etiketler) büyük harf küçük harf duyarlı değillerdir. Fakat tavsiye edilen **küçük harf** ile yazılmasıdır.

## 📝 Tag (Etiket) Yapısı

Bütün HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) tag'ları (etiketleri) **< (küçük)** ve **> (büyük)** işaretleri arasına yazılır. Bazıları tek olarak kullanılır, bazıları ise açma kapama olarak kullanılırlar.

**Tek olarak kullanım için örnek:**
```html
<br/>
```

**Açma kapatma olarak kullanım için örnek:**
```html
<b>...</b>
```

Dikkat edilmesi gereken yer, bütün başlama kodları **< (küçük)** ve **> (büyük)** işaretleri arasında, bitirme kodları ise **</ (küçük + kesme)** ve **> (büyük)** işaretleri arasında olmalıdır. Bunların eksik yazılması, sayfanın biçimsiz görünmesine neden olur.

## 📋 Ana Etiketler

Bir HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) dokümanında bulunması şart olan ana tag'lar (etiketler) aşağıdaki gibidir.

### `<!doctype>`

Sayfada kullanılan standart doğrultusunda **browser'a (tarayıcıya)** dokümanın yapısı hakkında ön bilgi vermek için kullanılan bir yöntemdir. Örneğin; Dokümanımız eğer **XHTML** (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili) ise bu alanda bildirilir. **Doctype (belge türü tanımı)** tag'ının (etiketinin) kapama tag'ı (etiketi) veya kapatma işareti yoktur ve ayrıca küçük harf büyük harf duyarlılığı da yoktur.

**Tek satırlı olarak kullanım için örnek:**
```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

**İki satırlı olarak kullanım için örnek:**
```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

Burada dokümanımızın **XHTML** (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili) 1.0 versiyonu dikkate alınarak yazıldığı ve kullanılan bu kuralların **link'i (bağlantısı)** verilmiştir. Link'in (bağlantının) kullanılmadığı şeklide vardır.

#### HTML 5 ve Doctype

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 öncesi sürümler **SGML** (Standard Generalized Markup Language) (standart genelleştirilmiş işaretleme dili) kökenli diller olduğu için **DTD** (Document Type Definition) (belge türü tanımı) tanımlarına gereksinim duyardı. Ancak HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 ve daha sonrası sürümler SGML (Standard Generalized Markup Language) (standart genelleştirilmiş işaretleme dili) kökenli olmadığı için buna gerek duymaz.

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5'de bir sürüm numarası yok çünkü, HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 geliştirilirken eğer buraya bir sürüm numarası verilse idi mevcut bütün web siteleri bu kapsam dışında kalacaktı, ama bu şekilde bir tanım ile eski ve yeni tüm dokümanlar aynı kategoriye koyulmuş ve geçmişi de destekleyen bir yapıya kavuşturulmuş oldu.

**HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 kullanım için örnek:**
```html
<!doctype html>
```

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 ile kullanımı çok daha kolay ve kısaltılmıştır. Bu tanımlamadan sonra **browser'lar (tarayıcılar)** bu kurallara göre sayfayı yorumlayacak ve buna göre bir görünümü kullanıcıya sunacaktır. Browser'lar (tarayıcılar) kullanılan doküman tip tanımlamasında **DTD'ye** (Document Type Definition) (belge türü tanımına) göre sayfayı analiz eder.

Güzel bir kodlama, HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) veya **XHTML** (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili) dokümanın onaylanmış halidir. Kodlamamızın doğruluğunu biz yazılımcılar genellikle **http://validator.w3.org** adresinden kontrol ederiz. Ancak bu özelliği bir çok **IDE** (Integrated Development Environment) (tümleşik geliştirme ortamı) içerisinde de bulmamız mümkündür. Örneğin; Adobe Dreamweaver vs. Doğrulama işlemi önemlidir çünkü bizim kodlarımızı doğru yazdığımızı kontrol eder.

Aslında yeni nesil browser'lar (tarayıcılar) bir tanım yapılmasa daha standart modda belgeyi tanımladığı için doctype'ın (belge türü tanımının) pek bir geçerliliği kalmamış olacaktır ama yine de bir tanım yapmak kesinlikle iyidir çünkü Internet Explorer tarzı browser'ların (tarayıcıların) ne yapacağı pek belli olmuyor.

### `<html>...</html>`

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) dokümanlarını çevreleyen kapsayıcı bir tag'dır (etikettir). HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) dokümanının başladığı ve bittiği yerleri belirtir. Her web dokümanında bu sınırlar belirtilir.

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 öncesinde tanımımız olarak `<html xmlns="http://www.w3.org/1999/xhtml" lang="tr" xml:lang="tr">` şeklinde idi. Buradaki **xmlns** değeri bu dokümanın ana çatısının `http://www.w3.org/1999/xhtml` kullandığını gösteriyor. HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 ana çatısı belli olduğu için tekrar tanımlamaya gerek duymuyor ve ayrıca iki adet dil tanımının da gereksiz olduğunu kabul ediyor ve sonuçta HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5'deki tanımımız `<html lang="tr"></html>` şeklinde oluyor.

### `<head>...</head>`

Web sayfasında görüntülenmeyen, ama web sayfası ile ilgili bilgileri veren ve istenirse sayfanın bazı yapısal özelliklerinin belirlenebildiği bölümdür.

### `<meta>`

Sayfanın arama motorları için bilgilerinin tanımlanmasını sağladığı gibi, içeriklerimizin kodlama biçimlerini de belirler. **<meta>** etiketleri **browser'lar (tarayıcılar)** için de bilgileri bulundururlar. Örneğin; Sayfanın karakter kodlaması, içeriğin önbelleğe alınıp alınmayacağı vs.

### `<title>…</title>`

Sayfanın adını / başlığını belirtir. **Browser'da (tarayıcıda)** web sayfasının adı / başlığı olarak görünür. Bazı arama motorlarında web sayfalarının indekslenmesinde kullanılır. Ad / Başlık verilmesi zorunlu değildir, ama her web dokümanına, o dokümanın içeriğine uygun bir ad / başlık vermek son derece önemlidir.

### `<body>…</body>`

Web sayfasının gövdesini belirler. **Client'e (istemciye)** sunulacak her şey bu bölümde yer alır.

## 📄 Örnek HTML Sayfaları

### HTML 4.1 Yapısı

Basit bir HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) sayfası HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 4.1 yapısına göre aşağıdaki şekildedir:

```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="tr" xml:lang="tr">
<head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<title>...</title>
</head>
<body>
</body>
</html>
```

### HTML 5 Yapısı

Basit bir HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) sayfası HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) 5 yapısına göre aşağıdaki şekildedir:

```html
<!doctype html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>...</title>
</head>
<body>
</body>
</html>
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

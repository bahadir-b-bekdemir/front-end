# 🔗 HTML URL ENCODING

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) **URL Encoding** (Uniform Resource Locator Encoding) (nizami kaynak bulucu kodlaması), karakterleri dönüştürmeye verilen isimdir. **URL'ler** (Uniform Resource Locator) (nizami kaynak bulucular) sadece **ASCII** (American Standard Code for Information Interchange) (bilgi değişimi için amerikan standart kodlama sistemi) karakter seti kullanarak internet üzerinden gönderilebilir.

## 📖 Kullanım

URL'ler (Uniform Resource Locator) (nizami kaynak bulucular), ASCII (American Standard Code for Information Interchange) (bilgi değişimi için amerikan standart kodlama sistemi) kümesi dışında karakterler içerdiğinde, URL (Uniform Resource Locator) (nizami kaynak bulucu) geçerli bir ASCII (American Standard Code for Information Interchange) (bilgi değişimi için amerikan standart kodlama sistemi) biçime dönüştürülmelidir. Bu nedenle URL Encoding (Uniform Resource Locator Encoding) (nizami kaynak bulucu kodlaması) hexadecimal (onaltılık) tarafından izlenen bir **% (yüzde)** işareti ile güvenli olmayan ASCII (American Standard Code for Information Interchange) (bilgi değişimi için amerikan standart kodlama sistemi) karakterleri değiştirir.

**Örnek**: URL'ler (Uniform Resource Locator) (nizami kaynak bulucular) boşluk içeremez ve URL (Uniform Resource Locator) (nizami kaynak bulucu) kodlamada normalde bir **+ (artı)** işareti ile veya **%20** ile bir boşluk değeri değiştirilir.

```html
<!-- Boşluk karakteri -->
https://example.com/page name  →  https://example.com/page%20name
https://example.com/page+name

<!-- Özel karakterler -->
https://example.com/search?q=hello&world  →  https://example.com/search?q=hello%26world
```

## 💻 Programlama Dillerinde Kullanım

**Javascript**, **PHP** (Hypertext Preprocessor) (üstün yazı ön işlemcisi) (Personal Home Page) (kişisel ana sayfa), **ASP** (Active Server Pages) (aktif sunucu sayfaları) vs. gibi yazılım dillerinde URL Encoding (Uniform Resource Locator Encoding) (nizami kaynak bulucu kodlaması) kullanılabilecek fonksiyonlar vardır:

- **Javascript**: `encodeURI()` fonksiyonu
- **PHP**: `rawurlencode()` fonksiyonu
- **ASP**: `Server.URLEncode()` fonksiyonu

## 📋 ASCII Karakter Tablosu

<style>
table {
  width: 100%;
  table-layout: fixed;
}
table td:first-child {
  width: 50%;
  min-width: 200px;
}
table td:nth-child(2) {
  width: 50%;
  min-width: 150px;
}
table td:nth-child(3) {
  width: 30%;
  min-width: 100px;
}
</style>

### Özel Karakterler ve Semboller

<div style="width: 100%; max-width: 900px; margin: 0 auto;">

| ASCII Karakter | URL Encoding |
| :------------: | :-----------: |
| space (boşluk) |      %20      |
|       !        |      %21      |
|       "        |      %22      |
|       #        |      %23      |
|       $        |      %24      |
|       %        |      %25      |
|       &        |      %26      |
|       '        |      %27      |
|       (        |      %28      |
|       )        |      %29      |
|       *        |      %2A      |
|       +        |      %2B      |
|       ,        |      %2C      |
|       -        |      %2D      |
|       .        |      %2E      |
|       /        |      %2F      |
|       :        |      %3A      |
|       ;        |      %3B      |
|       <        |      %3C      |
|       =        |      %3D      |
|       >        |      %3E      |
|       ?        |      %3F      |
|       @        |      %40      |
|       [        |      %5B      |
|       \        |      %5C      |
|       ]        |      %5D      |
|       ^        |      %5E      |
|       _        |      %5F      |
|       `        |      %60      |
|       {        |      %7B      |
|       \|       |      %7C      |
|       }        |      %7D      |
|       ~        |      %7E      |

</div>

### Rakamlar

<div style="width: 100%; max-width: 900px; margin: 0 auto;">

| ASCII Karakter | URL Encoding |
| :------------: | :-----------: |
|       0        |      %30      |
|       1        |      %31      |
|       2        |      %32      |
|       3        |      %33      |
|       4        |      %34      |
|       5        |      %35      |
|       6        |      %36      |
|       7        |      %37      |
|       8        |      %38      |
|       9        |      %39      |

</div>

### Büyük Harfler

<div style="width: 100%; max-width: 900px; margin: 0 auto;">

| ASCII Karakter | URL Encoding |
| :------------: | :-----------: |
|       A        |      %41      |
|       B        |      %42      |
|       C        |      %43      |
|       D        |      %44      |
|       E        |      %45      |
|       F        |      %46      |
|       G        |      %47      |
|       H        |      %48      |
|       I        |      %49      |
|       J        |      %4A      |
|       K        |      %4B      |
|       L        |      %4C      |
|       M        |      %4D      |
|       N        |      %4E      |
|       O        |      %4F      |
|       P        |      %50      |
|       Q        |      %51      |
|       R        |      %52      |
|       S        |      %53      |
|       T        |      %54      |
|       U        |      %55      |
|       V        |      %56      |
|       W        |      %57      |
|       X        |      %58      |
|       Y        |      %59      |
|       Z        |      %5A      |

</div>

### Küçük Harfler

<div style="width: 100%; max-width: 900px; margin: 0 auto;">

| ASCII Karakter | URL Encoding |
| :------------: | :-----------: |
|       a        |      %61      |
|       b        |      %62      |
|       c        |      %63      |
|       d        |      %64      |
|       e        |      %65      |
|       f        |      %66      |
|       g        |      %67      |
|       h        |      %68      |
|       i        |      %69      |
|       j        |      %6A      |
|       k        |      %6B      |
|       l        |      %6C      |
|       m        |      %6D      |
|       n        |      %6E      |
|       o        |      %6F      |
|       p        |      %70      |
|       q        |      %71      |
|       r        |      %72      |
|       s        |      %73      |
|       t        |      %74      |
|       u        |      %75      |
|       v        |      %76      |
|       w        |      %77      |
|       x        |      %78      |
|       y        |      %79      |
|       z        |      %7A      |

</div>

## 🎛️ ASCII Aygıt Kontrolü Karakterleri

Ayrıca **ASCII** (American Standard Code for Information Interchange) (bilgi değişimi için amerikan standart kodlama sistemi) aygıt kontrolü karakterleri de mevcuttur. **%00** ile **%1F** arası hexadecimal (onaltılık) değerleri donanım aygıtlarını kontrol etmek için tasarlanmıştır ve herhangi bir URL (Uniform Resource Locator) (nizami kaynak bulucular) içinde hiçbir etkisi olmayacaktır.

<div style="width: 100%; max-width: 900px; margin: 0 auto;">

| ASCII Karakter | Description (Tanım)                      | URL Encoding |
| :------------: | ---------------------------------------- | :-----------: |
|      NUL       | Null Character (Null karakteri)          |      %00      |
|      SOH       | Start Of Header (başlığın başlangıcı)    |      %01      |
|      STX       | Start Of Text (metnin başlangıcı)        |      %02      |
|      ETX       | End Of Text (metin sonu)                 |      %03      |
|      EOT       | End Of Transmission (iletim sonu)        |      %04      |
|      ENQ       | Enquiry (soruşturma)                     |      %05      |
|      ACK       | Acknowledge (kabul etmek)                |      %06      |
|      BEL       | Bell (Ring) (çan (halka))                |      %07      |
|       BS       | Backspace (geri tuşu)                    |      %08      |
|       HT       | Horizontal Tab (yatay sekme)             |      %09      |
|       LF       | Line Feed (satır besleme)                |      %0A      |
|       VT       | Vertical Tab (dikey sekme)               |      %0B      |
|       FF       | Form Feed (form besleme)                 |      %0C      |
|       CR       | Carriage Return (satır başı)             |      %0D      |
|       SO       | Shift Out (kaydırıldı)                   |      %0E      |
|       SI       | Shift In (vardiya)                       |      %0F      |
|      DLE       | Data Link Escape (veri bağlantısı kaçış) |      %10      |
|      DC1       | Device Control 1 (aygıt kontrol 1)       |      %11      |
|      DC2       | Device Control 2 (aygıt kontrol 2)       |      %12      |
|      DC3       | Device Control 3 (aygıt kontrol 3)       |      %13      |
|      DC4       | Device Control 4 (aygıt kontrol 4)       |      %14      |
|      NAK       | Negative Acknowledge (onayı negatif)     |      %15      |
|      SYN       | Synchronize (senkronize etmek)           |      %16      |
|      ETB       | End Transmission Block (son iletim bloğu)|      %17      |
|      CAN       | Cancel (iptal)                           |      %18      |
|       EM       | End Of Medium (ortam sonu)               |      %19      |
|      SUB       | Substitute (vekil)                       |      %1A      |
|      ESC       | Escape (kaçış)                           |      %1B      |
|       FS       | File Separator (dosya ayırıcı)           |      %1C      |
|       GS       | Group Separator (grup ayırıcı)           |      %1D      |
|       RS       | Record Separator (kayıt ayırıcı)         |      %1E      |
|       US       | Unit Separator (birim ayırıcı)           |      %1F      |

</div>

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

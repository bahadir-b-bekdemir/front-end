# 🌐 TARAYICILARDA JAVASCRIPT'IN AKTİF VE PASİF EDİLMESİ

Javascript, hemen hemen tüm browser'lar (tarayıcılar) içerisinde bulunan Javascript Engine (Javascript motoru) sayesinde yorumlayarak çalışmaktadır. Cihaza herhangi bir browser (tarayıcı) yükleneceği zaman, standart olarak web yazılımları için son derece kritik bir önem taşıyan Javascript Engine'de (Javascript motoruda) aktif halde yüklenmektedir.

Ancak bir takım sebeplerden dolayı gerek kullanıcı tarafından gerekse farklı unsurlar tarafından devre dışı bırakılmış ise, içerik ya da sayfanın Javascript taraflı fonksiyonelliği sınırlı olacak veya devre dışı kalacaktır. Ayrıca Javascript eğer browser'da (tarayıcıda) pasif ise, Javascript altyapısını kullanan tüm hazır kütüphanelerde (JQuery, AngularJS, NodeJS, ReactJS, Bootstrap çatısı vs.) pasif olacaktır.

En yaygın olarak kullanılan yedi farklı browser'da (tarayıcıda) Javascript'i aktif veya pasif etmenin yolları aşağıda belirtilmiştir.

## 🌍 Google Chrome

1. Browser (tarayıcı) penceresindeki, sağ üst köşede bulunan 3 yatık çizgi (Google Chrome'u özelleştirin ve kontrol edin) icon'una tıklanır.
2. Açılan menü içerisinden ayarlar seçeneğine tıklanır.
3. Ayarlar alanının tüm detayları sayfaya gelir ve sayfanın en alt kısmında bulunan gelişmiş ayarları göster seçeneğine tıklanır.
4. Gelişmiş ayarlar sayfada açılır ve gizlilik başlığı altında bulunan içerik ayarları butonuna tıklanır.
5. Açılan yeni diyalog penceresi içerisinde bulunan Javascript başlığı altından Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Tüm sitelerin Javascript çalıştırmasına izin ver (önerilen) seçeneği işaretlenir ve bitti butonuna tıklanır.
   - **Javascript Pasif Etmek İçin:** Hiçbir sitenin Javascript çalıştırmasına izin verme seçeneği işaretlenir ve bitti butonuna tıklanır.
6. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🌐 Internet Explorer

1. Browser (tarayıcı) penceresindeki, sağ üst köşede bulunan çark (araçlar) icon'una tıklanır.
2. Açılan menü içerisinden internet seçenekleri seçeneğine tıklanır.
3. Açılan yeni diyalog penceresi içerisinde bulunan güvenlik sekmesine tıklanır.
4. Güvenlik alanı içerisinde bulunan internet icon'u aktif iken pencerenin alt kısmında bulunan özel düzey butonuna tıklanır.
5. Açılan yeni diyalog penceresi içerisinde bulunan komut dosyası başlığı altından etkin komut dosyası ve Java programcıklarının çalıştırılması başlıklarından Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Etkin komut dosyası başlığı altından etkinleştir seçeneği işaretlenir, daha sonra hemen bir alt satırında bulunan Java programcıklarının çalıştırılması başlığı altından etkinleştir seçeneği işaretlenir ve tamam butonuna tıklanır.
   - **Javascript Pasif Etmek İçin:** Etkin komut dosyası başlığı altından devre dışı bırak seçeneği işaretlenir, daha sonra hemen bir alt satırında bulunan Java programcıklarının çalıştırılması başlığı altından devre dışı bırak seçeneği işaretlenir ve tamam butonuna tıklanır.
6. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🌐 Microsoft Edge

1. Windows arama alanına grup ilkesi düzenle yazılarak çıkan sonuca (grup ilkesi düzenle) tıklanır.
2. Açılan pencerenin sağ tarafında bulunan bilgisayar yapılandırması seçeneğine çift tıklanır.
3. Açılan seçenekler içerisinde bulunan yönetim şablonları seçeneğine çift tıklanır.
4. Açılan seçenekler içerisinde bulunan Windows bileşenleri seçeneğine çift tıklanır.
5. Açılan seçenekler içerisinde bulunan Microsoft Edge seçeneğine çift tıklanır.
6. Açılan seçenekler içerisinde bulunan Javascript gibi komut dosyalarını çalıştırmanızı sağlar seçeneğine çift tıklanır.
7. Açılan yeni diyalog penceresi içerisinden Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Etkin seçeneği işaretlenir ve tamam butonuna tıklanarak tüm açık pencereler kapatılır.
   - **Javascript Pasif Etmek İçin:** Devre dışı bırakıldı seçeneği işaretlenir ve tamam butonuna tıklanarak tüm açık pencereler kapatılır.
8. Ayarların browser'da (tarayıcıda) devreye girmesi için eğer açık halde Microsoft Edge penceresi var ise browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🦊 Mozilla Firefox

1. Browser (tarayıcı) penceresindeki, adres çubuğuna `about:config` yazılarak enter (giriş) tuşuna basılır.
2. Açılan sayfa içerisinde bulunan söz veriyorum, dikkatli olacağım! butonuna tıklanır.
3. Açılan sayfanın en üst kısmında bulunan arama alanına `Javascript.enabled` yazılır.
4. Tercih adı Javascript.enabled olan satırdan Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Değer sütunundaki değer false ise, Javascript.enabled olan satıra sağ tıklanarak açılan menüden değiştir seçeneğine tıklanır.
   - **Javascript Pasif Etmek İçin:** Değer sütunundaki değer true ise, Javascript.enabled olan satıra sağ tıklanarak açılan menüden değiştir seçeneğine tıklanır.
5. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🎭 Opera

1. Browser (tarayıcı) penceresindeki, sol üst köşede bulunan menü butonuna tıklanır.
2. Açılan menü içerisinden ayarlar seçeneğine tıklanır.
3. Açılan sayfa içerisinde sol tarafta bulunan web siteleri seçeneğine tıklanır.
4. Açılan sayfa içerisindeki Javascript başlığı altından Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Tüm sitelerin Javascript çalıştırmasına izin ver (önerilen) seçeneği işaretlenir.
   - **Javascript Pasif Etmek İçin:** Hiçbir sitenin Javascript çalıştırmasına izin verme seçeneği işaretlenir.
5. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🍎 Safari

1. Browser (tarayıcı) penceresindeki, sağ üst köşede bulunan çark (genel Safari ayarları menüsünü görüntüle) icon'una tıklanır.
2. Açılan menü içerisinden tercihler seçeneğine tıklanır.
3. Açılan yeni diyalog penceresi içerisinde bulunan güvenlik sekmesine tıklanır.
4. Javascript aktif seçeneği onay kutusundan Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Javascript aktif seçeneğinin yanında bulunan onay kutusu işaretlenir ve diyalog penceresi kapatılır.
   - **Javascript Pasif Etmek İçin:** Javascript aktif seçeneğinin yanında bulunan onay kutusu işareti kaldırılır ve diyalog penceresi kapatılır.
5. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

## 🔍 Yandex Browser

1. Browser (tarayıcı) penceresindeki, sağ üst köşede bulunan 3 yatık çizgi (Yandex Browser ayarları) icon'una tıklanır.
2. Açılan menü içerisinden ayarlar seçeneğine tıklanır.
3. Ayarlar alanının tüm detayları sayfaya gelir ve sayfanın en alt kısmında bulunan gelişmiş ayarları göster seçeneğine tıklanır.
4. Gelişmiş ayarlar sayfada açılır ve kişisel veriler başlığı altında bulunan içerik ayarları butonuna tıklanır.
5. Açılan yeni diyalog penceresi içerisinde bulunan Javascript başlığı altından Javascript aktif ve pasif etme işlemleri yapılır.
   - **Javascript Aktif Etmek İçin:** Tüm sitelerin Javascript çalıştırmasına izin ver (önerilen) seçeneği işaretlenir ve bitti butonuna tıklanır.
   - **Javascript Pasif Etmek İçin:** Hiçbir sitenin Javascript çalıştırmasına izin verme seçeneği işaretlenir ve bitti butonuna tıklanır.
6. Ayarların browser'da (tarayıcıda) devreye girmesi için browser (tarayıcı) kapatılır ve yeniden açılır. Artık yapılmış olan değişiklik browser'da (tarayıcıda) devreye alınmıştır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

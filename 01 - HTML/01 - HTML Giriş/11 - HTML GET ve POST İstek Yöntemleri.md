# 📡 HTML'DE GET VE POST İSTEK YÖNTEMLERİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) **client (istemci)** ve **server (sunucu)** arasında bir istek ve yanıt için yaygın olarak kullanılan iki yöntem vardır. Bunlar **GET** ve **POST** yöntemleridir. GET ve POST yöntemleri tüm diğer yazılım dilleri ile **%100 uyumlu** olarak çalışabilmektedir.

## 📖 GET Yöntemi

İstek verileri belirli bir kaynaktan gönderilir. Bir diğer deyiş ile form verilerini veya manuel olarak belirleyeceğimiz verileri **adres çubuğundan** veri gönderimi anlamına gelmektedir.

**Örnek**: 
```
http://www.siteadi.com?veri1=deger1&veri2=deger2
```

### Özellikler

- Gönderilecek olan istekler **belleğe alınabilir** ve istekler **browser (tarayıcı)** tarafından geçmişte saklanabilir, yer imlerine / sık kullanılanlara kayıt edilebilir.

- Gönderilecek olan istekler için **adres çubuğu** kullanılacağı için **uzunluk kısıtlamalarına** maruz kalabilir. (maksimum 2048 karakter)

- Gönderilecek olan istekler yine **GET metodu** ile alınabilir. (kullanılacak yazılıma göre değişiklik gösterebilir)

- Gönderilecek olan isteklerde **Türkçe karakter** kullanılırsa **URL Encoding**'e (Uniform Resource Locator Encoding) (nizami kaynak bulucu kodlamalarına) maruz kalabilir.

- Gönderilecek olan isteklerde **ileri ve geri butonları** kullanılacak olur ise herhangi bir uyarı olmadan işlem yapılabilir.

- Gönderilecek olan isteklerde **resim, video, ses, doküman** vs. çok parçalı dosya içeriği mevcut olamaz. (`application/x-www-form-urlencoded`)

- Gönderilecek olan isteklerde **GET yöntemi POST yönteminden daha az güvenlidir**.

- Gönderilecek olan isteklerde tüm veriler **herkesin görebileceği şekilde** olduğu için hassas veriler içeriyorsa kullanılmamalıdır.

## 📮 POST Yöntemi

İstek gönderdiğinde veriler belirtilen kaynaktan alınarak işlenir. Bir diğer deyiş ile form verilerini veya manuel olarak belirleyeceğimiz verileri, veri gönderim **tag'ları (etiketleri)** aracılığı ile **kapalı olarak** gönderim anlamına gelmektedir.

**Örnek**: 
```
http://www.siteadi.com
```

### Özellikler

- Gönderilecek olan istekler **asla belleğe alınamazlar** ve istekler **browser (tarayıcı)** tarafından geçmişte asla saklanamazlar, yer imlerine / sık kullanılanlara asla kayıt edilemezler.

- Gönderilecek olan istekler **kapalı olarak** iletileceği için **uzunluk kısıtlamalarına asla maruz kalmazlar**. (maksimum karakter sınırı yok)

- Gönderilecek olan istekler yine **POST metodu** ile alınabilir. (kullanılacak yazılıma göre değişiklik gösterebilir)

- Gönderilecek olan isteklerde **Türkçe karakter** kullanılırsa kapalı veri gönderileceği için **URL Encoding**'e (Uniform Resource Locator Encoding) (nizami kaynak bulucu kodlamalarına) asla maruz kalmazlar.

- Gönderilecek olan isteklerde **ileri ve geri butonları** kullanılacak olur ise muhakkak bir **uyarı** olacaktır ve uyarı sonucuna göre işlem yapılacaktır.

- Gönderilecek olan isteklerde **resim, video, ses, doküman** vs. çok parçalı dosya içeriği mevcut olabilir. (`application/x-www-form-urlencoded` & `multipart/form-data`)

- Gönderilecek olan isteklerde **POST yöntemi GET yönteminden daha çok güvenlidir**.

- Gönderilecek olan isteklerde tüm veriler **görünmeyen kapalı şekilde** olduğu için hassas veriler içeriyorsa muhakkak bu metot kullanılmalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

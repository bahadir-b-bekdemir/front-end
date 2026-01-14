# 🌐 CSS'DE BROWSER'LAR (TARAYICILAR) İÇİN PREFIX (ÖNEK) TANIMLARI

Hazırlanmış olan bir web sayfası içeriğini görüntülemeye yarayan programlara **browser** (tarayıcı) adı verilir. Browser'lar web sayfalarının içeriğini daima **browser visualization engine** (tarayıcı görüntüleme motoru) denilen sistemleri sayesinde kullanıcılara görüntülerler.

Günümüzde, Google Chrome, Microsoft Edge, Mozilla Firefox, Opera, Safari, Yandex Browser vs. browser'lar sıklıkla kullanılmaktadır. **⚠️ Not:** Internet Explorer Haziran 2022'de desteği sonlandırılmıştır ve artık kullanılmamaktadır. Yazılım veya tasarım alanında yenilikler oldukça browser visualization engine'ları da sürekli olarak geliştirici firma tarafından isteklere cevap verebilmesi için güncellenirler. İlgili browser sürümü güncellendiği zaman aslında bu browser'ın visualization engine'ı da güncellenir. Bazen browser'ın görselliğinin de iyileştirme işlemlerinde kullanılır.

## ❓ Prefix (Önek) Nedir?

Hemen hemen her browser'ın geliştirici firması ve browser visualization engine'ları da farklı olduğu için, bazı durumlarda CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) özelliklerine **prefix** (önek) tanımlanmalıdır. İlgili CSS özelliklerinin tüm browser'lar tarafından algılanarak yorumlanabilmesi ve en kusursuz şekilde çalıştırılabilmesi prefix tanımları sağlar.

**⚠️ Önemli Not:** Modern tarayıcılarda (2020'lerden itibaren) çoğu CSS özelliği artık standartlaşmış durumdadır ve prefix'lere ihtiyaç duymaz. Ancak eski tarayıcı desteği gerektiren projelerde veya henüz standartlaşmamış deneysel özelliklerde prefix'ler hala kullanılabilir. Modern geliştirme ortamlarında Autoprefixer gibi araçlar otomatik olarak gerekli prefix'leri ekler.

## 🔖 Browser Prefix Tanımları

En yaygın olarak kullanılan yedi farklı browser'ın ve Microsoft Office programının prefix tanımları aşağıda belirtilmiştir.

| Browser / Program | Prefix | Not |
|-------------------|--------|-----|
| **Internet Explorer** | `-ms-` | ⚠️ Haziran 2022'de desteği sonlandırılmıştır, artık kullanılmamaktadır |
| **Microsoft Edge** | `-webkit-` | Modern Edge (Chromium tabanlı, 2019'dan itibaren) genellikle prefix gerektirmez. Eski Edge (EdgeHTML) `-ms-` kullanırdı |
| **Microsoft Office** | `-mso-` | Office uygulamaları için |
| **Mozilla Firefox** | `-moz-` | Modern Firefox genellikle prefix gerektirmez |
| **Google Chrome** | `-webkit-` | Modern Chrome genellikle prefix gerektirmez |
| **Yandex Browser** | `-webkit-` | Chromium tabanlı, genellikle prefix gerektirmez |
| **Safari** | `-webkit-` | Bazı özellikler için hala gerekebilir |
| **Opera** | `-o-` | Modern Opera (Chromium tabanlı) genellikle prefix gerektirmez |

## 📊 Prefix Sıralaması

CSS özellikleri için prefix tanımlarının, W3C (World Wide Web Consortium - Dünya Çapında Ağ Konsorsiyumu) tarafından belirtilmiş en doğru sıralaması aşağıdaki şekildedir. Fakat istenirse farklı sıralama ile de kullanılması mümkündür.

1. `-webkit-`
2. `-moz-`
3. `-o-`
4. `-ms-`
5. `-mso-` (Gerekli ise)
6. Standart kodlama

### 💡 Örnek Kullanım

**⚠️ Önemli Not:** Aşağıdaki örnek, prefix kullanımını göstermek içindir. `transform` özelliği artık modern tarayıcılarda prefix gerektirmez. Bu örnek, henüz standartlaşmamış veya eski tarayıcı desteği gerektiren özellikler için prefix kullanımını göstermektedir.

```css
/* Örnek: backdrop-filter (bazı tarayıcılarda hala prefix gerektirebilir) */
.example {
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
}

/* Eski tarayıcı desteği gerektiren projeler için örnek */
.legacy-transform {
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    transform: rotate(45deg);
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

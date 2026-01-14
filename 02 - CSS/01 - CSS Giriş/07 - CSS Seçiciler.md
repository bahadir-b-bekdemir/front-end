# 🎯 CSS SEÇİCİLERİ

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) herhangi bir HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) sayfası içerisindeki tüm elemanlara / elementlere erişmekte kullanılan birçok seçici türü bulunmaktadır. Bu sayede istenilen bir veya daha fazla HTML elemanı / elementini seçerek kolaylıkla biçimlendirme işlemleri yapılabilir.

## 📋 Temel Seçiciler

Tüm CSS seçici türleri aşağıda listelenmektedir.

| Seçici Adı | Karakter | Açıklama |
|------------|----------|----------|
| **Genel (Evrensel) Seçici** | `*` | Tüm HTML elementlerini seçer. |
| **Element (Tür) Seçicileri** | `Element` | Belirtilecek olan HTML elementini seçer. |
| **ID (Benzersiz Kimlik) Seçicileri** | `#ElementinIDsi` | Belirtilecek olan ID değeri ile eşleşen HTML elementini seçer. |
| **Class (Sınıf) Seçicileri** | `.ElementinSınıfı` | Belirtilecek olan class (sınıf) değeri ile eşleşen HTML elementini seçer. |
| **Child (Çocuk) Seçiciler** | `Element > Element` | Belirtilecek olan HTML elementinin, belirtilecek olan child (çocuk) elementini seçer. |
| **Descendant (Torun - Soy) Seçiciler** | `Element Element` | Belirtilecek olan HTML elementinin, belirtilecek olan descendant (torun - soy) elementini seçer. |
| **Genel Sibling (Kardeş) Seçiciler** | `Element ~ Element` | Belirtilecek olan HTML elementinin, belirtilecek olan sibling (kardeş) elementini seçer. |
| **Bitişik Sibling (Kardeş) Seçiciler** | `Element + Element` | Belirtilecek olan HTML elementinin, belirtilecek olan bitişik sibling (kardeş) elementini seçer. |
| **Multiple (Çoklu) Seçici** | `Element, Element` | Belirtilecek olan iki veya daha fazla HTML elementini seçer. |
| **Attribute (Özellik) Seçiciler** | `Element[Özellik Adı]` | Belirtilecek olan özelliğe sahip HTML elementini seçer. |

### 💡 Örnekler

```css
/* Genel Seçici - Sayfadaki tüm elementlerin margin ve padding değerlerini sıfırlar */
* {
    margin: 0;
    padding: 0;
}

/* Element Seçici - Tüm paragraf elementlerinin metin rengini mavi yapar */
p {
    color: blue;
}

/* ID Seçici - ID'si "header" olan elementin arka plan rengini siyah yapar */
#header {
    background-color: black;
}

/* Class Seçici - Class'ı "container" olan tüm elementlerin genişliğini %100 yapar */
.container {
    width: 100%;
}

/* Child Seçici - div elementinin doğrudan çocuğu olan p elementlerinin font boyutunu 14px yapar */
div > p {
    font-size: 14px;
}

/* Descendant Seçici - div içindeki tüm p elementlerinin (torun dahil) satır yüksekliğini 1.5 yapar */
div p {
    line-height: 1.5;
}

/* Sibling Seçici - h1'den sonra gelen tüm kardeş p elementlerinin üst margin'ini 20px yapar */
h1 ~ p {
    margin-top: 20px;
}

/* Bitişik Sibling Seçici - h1'den hemen sonra gelen bitişik p elementinin font kalınlığını bold yapar */
h1 + p {
    font-weight: bold;
}

/* Çoklu Seçici - h1, h2 ve h3 elementlerinin metin rengini kırmızı yapar */
h1, h2, h3 {
    color: red;
}

/* Attribute Seçici - type özelliği "text" olan input elementlerinin kenarlığını gri yapar */
input[type="text"] {
    border: 1px solid gray;
}
```

## 🔍 Attribute (Özellik) Seçici Filtreleri

CSS Attribute (Özellik) seçicileri için kullanılmakta olan filtreler aşağıda listelenmektedir.

| Filtre Adı | Desen (Pattern) | Açıklama |
|------------|------------------|----------|
| **Tam Değer Filtresi** | `[Özellik Adı="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değere sahip, aynı zamanda tam olarak eşleşen HTML elementini seçer. |
| **İçeren Tam Değer Filtresi** | `[Özellik Adı~="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değer içeriğine sahip, aynı zamanda tam olarak eşleşen HTML elementini seçer. |
| **İçeren Değer Filtresi** | `[Özellik Adı*="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değer içeriğine sahip HTML elementini seçer. |
| **Başlayan Değer Filtresi** | `[Özellik Adı^="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değer başlangıcına sahip HTML elementini seçer. |
| **Tireli veya Tiresiz Başlayan Değer Filtresi** | `[Özellik Adı|="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değer başlangıcına sahip (tireli veya tiresiz) HTML elementini seçer. |
| **Biten Değer Filtresi** | `[Özellik Adı$="Değer"]` | Belirtilecek olan özelliğe ve belirtilecek olan değer bitişine sahip HTML elementini seçer. |

### 💡 Örnekler

```css
/* Tam Değer Filtresi - type özelliği tam olarak "text" olan input elementlerinin kenarlığını mavi yapar */
input[type="text"] {
    border: 1px solid blue;
}

/* İçeren Tam Değer Filtresi - class özelliğinde "container" kelimesini içeren (boşlukla ayrılmış) div elementlerinin padding'ini 20px yapar */
div[class~="container"] {
    padding: 20px;
}

/* İçeren Değer Filtresi - href özelliğinde "example" kelimesini içeren (herhangi bir yerde) linklerin rengini kırmızı yapar */
a[href*="example"] {
    color: red;
}

/* Başlayan Değer Filtresi - href özelliği "https" ile başlayan linklerin alt çizgisini kaldırır */
a[href^="https"] {
    text-decoration: none;
}

/* Tireli veya Tiresiz Başlayan Değer Filtresi - lang özelliği "tr" veya "tr-" ile başlayan div elementlerinin yönünü soldan sağa yapar */
div[lang|="tr"] {
    direction: ltr;
}

/* Biten Değer Filtresi - src özelliği ".jpg" ile biten resimlerin kenarlığını siyah yapar */
img[src$=".jpg"] {
    border: 2px solid black;
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

# 🎭 CSS SEÇİCİLERİNDE PSEUDO CLASSES (SAHTE SINIFLAR)

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) seçicilerinde kullanılan birçok pseudo class (sahte sınıf) türü bulunmaktadır. Bu sayede istenilen bir veya daha fazla HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elemanı / elementini üzerinde biçimlendirme işlemleri yapılabilir.

## 🔗 Link Durumları

Link elementlerinin farklı durumlarını hedeflemek için kullanılan pseudo class'lar.

| Pseudo Class | Açıklama |
|--------------|----------|
| `:link` | Daha önce hiç açılmamış link'in rengini tanımlar. |
| `:visited` | Daha önce açılmış link'in rengini tanımlar. |
| `:hover` | Belirtilen HTML elementinin mouse (fare) üzerine geldiğinde stil tanımlar. Mouse üzerinden ayrıldığında stil normale döner. |
| `:active` | Belirtilen HTML elementi aktif olduğunda (tıklandığında) stil tanımlar. |
| `:any-link` | Doküman içerisinde bulunan HTML'in link elementinin URL değeri boş değil ise stil tanımlar. |

### 💡 Örnekler

```css
/* Link - Henüz ziyaret edilmemiş linklerin rengini mavi yapar */
a:link {
    color: blue;
}

/* Visited - Ziyaret edilmiş linklerin rengini mor yapar */
a:visited {
    color: purple;
}

/* Hover - Mouse üzerine gelindiğinde linkin rengini kırmızı yapar */
a:hover {
    color: red;
}

/* Active - Link tıklandığında arka plan rengini sarı yapar */
a:active {
    background-color: yellow;
}

/* Any-link - URL'si olan tüm linklerin alt çizgisini kaldırır */
a:any-link {
    text-decoration: none;
}
```

## 📝 Form Durumları

Form elementlerinin farklı durumlarını hedeflemek için kullanılan pseudo class'lar.

| Pseudo Class | Açıklama |
|--------------|----------|
| `:focus` | Belirtilen HTML elementine odaklanıldığında stil tanımlar. Odağından çıkıldığında stil normale döner. |
| `:checked` | Belirtilen HTML elementi seçildiğinde (checkbox, radio) stil tanımlar. Seçimi kaldırıldığında stil normale döner. |
| `:disabled` | Belirtilen HTML elementi etkin olmadığında stil tanımlar. |
| `:enabled` | Belirtilen HTML elementi etkin olduğunda stil tanımlar. |
| `:read-only` | Belirtilen HTML elementi sadece okunabilir olduğunda stil tanımlar. |
| `:read-write` | Belirtilen HTML elementi okunabilir ve yazılabilir olduğunda stil tanımlar. |
| `:required` | Belirtilen HTML elementine bilgi girişi zorunlu olduğunda stil tanımlar. |
| `:optional` | Belirtilen HTML elementi bilgi girişi opsiyonel olduğunda stil tanımlar. |
| `:valid` | Belirtilen HTML elementi bilgi girişi geçerli bir değer olduğunda stil tanımlar. Geçersiz olduğunda stil normale döner. |
| `:invalid` | Belirtilen HTML elementi bilgi girişi geçersiz bir değer olduğunda stil tanımlar. Geçerli olduğunda stil normale döner. |
| `:in-range` | Belirtilen HTML elementi bilgi girişi belirtilen aralıklar dahilinde bir değer olduğunda stil tanımlar. Aralık dışında olduğunda stil normale döner. |
| `:out-of-range` | Belirtilen HTML elementi bilgi girişi belirtilen aralıklar dışında bir değer olduğunda stil tanımlar. Aralık dahilinde olduğunda stil normale döner. |

### 💡 Örnekler

```css
/* Focus - Input'a odaklanıldığında kenarlığını mavi yapar */
input:focus {
    border: 2px solid blue;
}

/* Checked - Seçili checkbox'ların arka plan rengini yeşil yapar */
input[type="checkbox"]:checked {
    background-color: green;
}

/* Disabled - Devre dışı input'ların arka plan rengini gri yapar */
input:disabled {
    background-color: gray;
}

/* Enabled - Etkin input'ların arka plan rengini beyaz yapar */
input:enabled {
    background-color: white;
}

/* Required - Zorunlu input'ların kenarlığını kırmızı yapar */
input:required {
    border: 2px solid red;
}

/* Valid - Geçerli değer girildiğinde kenarlığı yeşil yapar */
input:valid {
    border: 2px solid green;
}

/* Invalid - Geçersiz değer girildiğinde kenarlığı kırmızı yapar */
input:invalid {
    border: 2px solid red;
}
```

## 🏗️ Yapısal Seçiciler

HTML yapısına göre elementleri seçmek için kullanılan pseudo class'lar.

| Pseudo Class | Açıklama |
|--------------|----------|
| `:root` | HTML belgesinin kök (html) elementine stil tanımlar. |
| `:empty` | Belirtilen HTML elementinin içeriği tamamen boş ise stil tanımlar. |
| `:not()` | Belirtilen HTML elementi hariç diğer tüm HTML elementlerine stil tanımlar. |
| `:lang()` | Belirtilen HTML elementinin lang (dil) özelliğine göre stil tanımlar. |
| `:target` | Belirtilen HTML elementine çapa türündeki link'lerle bağlanmış olan ve tıklandığında hedeflenmiş olan elemente stil tanımlar. |

### 💡 Örnekler

```css
/* Root - HTML kök elementinin font boyutunu 16px yapar */
:root {
    font-size: 16px;
}

/* Empty - İçeriği boş olan div'lerin arka plan rengini açık gri yapar */
div:empty {
    background-color: lightgray;
}

/* Not - Paragraf olmayan tüm elementlerin font ağırlığını normal yapar */
:not(p) {
    font-weight: normal;
}

/* Lang - Türkçe dil özelliğine sahip elementlerin yönünü soldan sağa yapar */
:lang(tr) {
    direction: ltr;
}

/* Target - Hedeflenen bölümün arka plan rengini sarı yapar */
section:target {
    background-color: yellow;
}
```

## 👶 Child Seçiciler

Elementlerin çocuk ve kardeş ilişkilerine göre seçim yapmak için kullanılan pseudo class'lar.

| Pseudo Class | Açıklama |
|--------------|----------|
| `:first-child` | Belirtilen HTML elementi baz alınarak, üst elementine göre bitişik ilk child (çocuk) durumundaki elemente stil tanımlar. |
| `:last-child` | Belirtilen HTML elementi baz alınarak, üst elementine göre bitişik son child (çocuk) durumundaki elemente stil tanımlar. |
| `:first-of-type` | Belirtilen HTML elementi baz alınarak, üst elementine göre ilk child (çocuk) durumundaki elemente stil tanımlar. |
| `:last-of-type` | Belirtilen HTML elementi baz alınarak, üst elementine göre son child (çocuk) durumundaki elemente stil tanımlar. |
| `:only-child` | Belirtilen HTML elementi baz alınarak, üst elementine göre bitişik tek child (çocuk) durumundaki elemente stil tanımlar. |
| `:only-of-type` | Belirtilen HTML elementi baz alınarak, üst elementine göre kardeş element türleri de eşleşen tek child (çocuk) durumundaki elemente stil tanımlar. |
| `:nth-child()` | Belirtilen HTML elementi baz alınarak, üst elementine göre kardeş element türlerine bakılmaksızın ilk child'dan başlanarak sıra numarasına göre stil tanımlar. |
| `:nth-last-child()` | Belirtilen HTML elementi baz alınarak, üst elementine göre kardeş element türlerine bakılmaksızın son child'dan başlanarak sıra numarasına göre stil tanımlar. |
| `:nth-of-type()` | Belirtilen HTML elementi baz alınarak, üst elementine göre kardeş element türleri de eşleşen ilk child'dan başlanarak sıra numarasına göre stil tanımlar. |
| `:nth-last-of-type()` | Belirtilen HTML elementi baz alınarak, üst elementine göre kardeş element türleri de eşleşen son child'dan başlanarak sıra numarasına göre stil tanımlar. |

### 💡 Örnekler

```css
/* First-child - İlk çocuk elementin font boyutunu 20px yapar */
li:first-child {
    font-size: 20px;
}

/* Last-child - Son çocuk elementin margin-bottom'unu 0 yapar */
li:last-child {
    margin-bottom: 0;
}

/* First-of-type - İlk paragraf elementinin font ağırlığını bold yapar */
p:first-of-type {
    font-weight: bold;
}

/* Only-child - Tek çocuk olan div'in genişliğini %100 yapar */
div:only-child {
    width: 100%;
}

/* Nth-child - Her 2. çocuk elementin arka plan rengini açık mavi yapar (2n = çift sayılar) */
li:nth-child(2n) {
    background-color: lightblue;
}

/* Nth-child - 3. çocuk elementin rengini kırmızı yapar */
li:nth-child(3) {
    color: red;
}

/* Nth-of-type - Her 3. paragraf elementinin font stilini italic yapar */
p:nth-of-type(3n) {
    font-style: italic;
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

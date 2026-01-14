# 🎨 CSS SEÇİCİLERİNDE PSEUDO ELEMENTS (SAHTE ELEMENTLER)

CSS (Cascading Style Sheets - Basamaklı Stil Şablonları) seçicilerinde kullanılan birçok pseudo element (sahte element) türü bulunmaktadır. Bu sayede istenilen bir veya daha fazla HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elemanı / elementini üzerinde biçimlendirme işlemleri yapılabilir.

**⚠️ Önemli Not:** Pseudo element'ler CSS'de `::` (çift iki nokta) ile yazılır. Eski tarayıcı uyumluluğu için `:` (tek iki nokta) da kabul edilir, ancak modern CSS standartlarına göre `::` kullanılması önerilir.

## 📝 Metin İçeriği Pseudo Element'leri

Metin içeriğinin belirli kısımlarını hedeflemek için kullanılan pseudo element'ler.

| Pseudo Element | Açıklama |
|----------------|----------|
| `::first-letter` | Belirtilen HTML elementinin ilk karakterine stil tanımlar. |
| `::first-line` | Belirtilen HTML elementinin ilk satırına stil tanımlar. |
| `::selection` | Belirtilen HTML elementinin kullanıcı tarafından seçilen kısmına stil tanımlar. |

### 💡 Örnekler

```css
/* First-letter - Paragrafın ilk harfini büyük ve kırmızı yapar */
p::first-letter {
    font-size: 2em;
    color: red;
    font-weight: bold;
}

/* First-line - Paragrafın ilk satırını italik ve mavi yapar */
p::first-line {
    font-style: italic;
    color: blue;
}

/* Selection - Seçilen metnin arka plan rengini sarı, metin rengini siyah yapar */
::selection {
    background-color: yellow;
    color: black;
}
```

## ➕ İçerik Ekleme Pseudo Element'leri

HTML elementlerinin öncesine veya sonrasına içerik eklemek için kullanılan pseudo element'ler.

| Pseudo Element | Açıklama |
|----------------|----------|
| `::before` | Belirtilen HTML elementinin öncesine içerik atayarak stil tanımlar. `content` özelliği zorunludur. |
| `::after` | Belirtilen HTML elementinin sonrasına içerik atayarak stil tanımlar. `content` özelliği zorunludur. |

### 💡 Örnekler

```css
/* Before - Linklerin önüne ok işareti ekler */
a::before {
    content: "→ ";
    color: blue;
}

/* After - Linklerin sonuna ok işareti ekler */
a::after {
    content: " ←";
    color: blue;
}

/* Before - Özel ikon ekleme */
.button::before {
    content: "★ ";
    color: gold;
}

/* After - Açıklama ekleme */
.tooltip::after {
    content: " (Bilgi)";
    font-size: 0.8em;
    color: gray;
}
```

## 📋 Form ve Liste Pseudo Element'leri

Form elementleri ve listeler için özel pseudo element'ler.

| Pseudo Element | Açıklama |
|----------------|----------|
| `::placeholder` | Input ve textarea elementlerinin placeholder (yer tutucu) metnine stil tanımlar. |
| `::marker` | Liste elementlerinin (li) marker (işaretleyici) kısmına stil tanımlar. |

### 💡 Örnekler

```css
/* Placeholder - Input placeholder metninin rengini açık gri yapar */
input::placeholder {
    color: lightgray;
    font-style: italic;
}

/* Marker - Liste işaretleyicilerinin rengini mavi yapar */
li::marker {
    color: blue;
    font-weight: bold;
}
```

## 🎭 Diğer Pseudo Element'ler

Diğer özel durumlar için kullanılan pseudo element'ler.

| Pseudo Element | Açıklama |
|----------------|----------|
| `::backdrop` | Fullscreen API veya dialog elementleri için arka plan katmanına stil tanımlar. |

### 💡 Örnekler

```css
/* Backdrop - Fullscreen modda arka planı bulanıklaştırır */
video::backdrop {
    background-color: rgba(0, 0, 0, 0.8);
    backdrop-filter: blur(5px);
}
```

## 🔄 Pseudo Class ve Pseudo Element Kombinasyonu

Pseudo class'lar ve pseudo element'ler birlikte kullanılabilir.

### 💡 Örnekler

```css
/* Hover durumunda linkin sonuna özel içerik ekler */
a:hover::after {
    content: " (Tıklayın)";
    color: green;
}

/* İlk paragrafın ilk harfini özel stillendirir */
p:first-child::first-letter {
    font-size: 3em;
    float: left;
    line-height: 1;
    margin-right: 5px;
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

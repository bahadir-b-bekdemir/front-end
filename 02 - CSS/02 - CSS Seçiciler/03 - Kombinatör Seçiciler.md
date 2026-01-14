# 🔗 CSS KOMBİNATÖR SEÇİCİLER

CSS'de (Cascading Style Sheets - Basamaklı Stil Şablonları) kombinatör seçiciler, HTML (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) elementleri arasındaki ilişkilere göre seçim yapmak için kullanılır. Bu seçiciler, elementlerin hiyerarşik yapısını ve kardeş ilişkilerini kullanarak hedefleme yapar.

## 👶 Child (Çocuk) Seçici

Bir elementin doğrudan çocuk elementlerini seçer. Sadece bir seviye aşağıdaki elementleri hedefler.

### Sözdizimi

```css
parent > child {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* div elementinin doğrudan çocuğu olan p elementlerini seçer */
div > p {
    color: blue;
}

/* ul elementinin doğrudan çocuğu olan li elementlerini seçer */
ul > li {
    list-style: none;
}

/* nav elementinin doğrudan çocuğu olan a elementlerini seçer */
nav > a {
    text-decoration: none;
    padding: 10px;
}
```

### 📝 HTML Örneği

```html
<div>
    <p>Bu seçilir (doğrudan çocuk)</p>
    <section>
        <p>Bu seçilmez (torun)</p>
    </section>
</div>
```

## 🌳 Descendant (Torun - Soy) Seçici

Bir elementin tüm torun (soy) elementlerini seçer. Kaç seviye aşağıda olursa olsun tüm eşleşen elementleri hedefler.

### Sözdizimi

```css
ancestor descendant {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* div içindeki tüm p elementlerini seçer (torun dahil) */
div p {
    color: blue;
}

/* nav içindeki tüm a elementlerini seçer */
nav a {
    color: white;
}

/* article içindeki tüm h2 elementlerini seçer */
article h2 {
    font-size: 24px;
}
```

### 📝 HTML Örneği

```html
<div>
    <p>Bu seçilir</p>
    <section>
        <p>Bu da seçilir (torun)</p>
        <article>
            <p>Bu da seçilir (torunun torunu)</p>
        </article>
    </section>
</div>
```

## 👥 Adjacent Sibling (Bitişik Kardeş) Seçici

Bir elementin hemen ardından gelen bitişik kardeş elementini seçer.

### Sözdizimi

```css
element + sibling {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* h1'den hemen sonra gelen p elementini seçer */
h1 + p {
    font-size: 18px;
    margin-top: 10px;
}

/* div'den hemen sonra gelen section elementini seçer */
div + section {
    margin-top: 20px;
}

/* li'den hemen sonra gelen li elementini seçer */
li + li {
    border-top: 1px solid gray;
}
```

### 📝 HTML Örneği

```html
<h1>Başlık</h1>
<p>Bu seçilir (hemen sonraki kardeş)</p>
<p>Bu seçilmez</p>

<div>İçerik</div>
<section>Bu seçilir</section>
<section>Bu seçilmez</section>
```

## 👨‍👩‍👧‍👦 General Sibling (Genel Kardeş) Seçici

Bir elementin ardından gelen tüm kardeş elementlerini seçer.

### Sözdizimi

```css
element ~ sibling {
    /* Stil tanımları */
}
```

### 💡 Örnekler

```css
/* h1'den sonra gelen tüm p elementlerini seçer */
h1 ~ p {
    color: gray;
}

/* div'den sonra gelen tüm section elementlerini seçer */
div ~ section {
    margin-top: 20px;
}

/* .active class'ından sonra gelen tüm .item elementlerini seçer */
.active ~ .item {
    opacity: 0.5;
}
```

### 📝 HTML Örneği

```html
<h1>Başlık</h1>
<p>Bu seçilir</p>
<div>İçerik</div>
<p>Bu da seçilir</p>
<p>Bu da seçilir</p>
```

## 🎯 Kombinatör Seçicilerin Karşılaştırması

| Seçici | Sembol | Açıklama | Seviye |
|--------|--------|----------|--------|
| Child | `>` | Doğrudan çocuk | 1 seviye |
| Descendant | ` ` (boşluk) | Tüm torunlar | Tüm seviyeler |
| Adjacent Sibling | `+` | Hemen sonraki kardeş | 1 kardeş |
| General Sibling | `~` | Tüm sonraki kardeşler | Tüm kardeşler |

## 💡 Pratik Örnekler

### Menü Yapısı

```css
/* Ana menü öğeleri */
nav > ul > li {
    display: inline-block;
    margin: 0 10px;
}

/* Alt menü öğeleri */
nav ul ul li {
    display: block;
    padding: 5px;
}

/* Menü öğeleri arası ayırıcı */
li + li {
    border-left: 1px solid gray;
    padding-left: 10px;
}
```

### İçerik Yapısı

```css
/* Başlıktan sonraki ilk paragraf */
h1 + p {
    font-size: 1.2em;
    font-weight: bold;
}

/* Başlıktan sonraki tüm paragraflar */
h1 ~ p {
    line-height: 1.6;
    margin-bottom: 15px;
}

/* Article içindeki tüm başlıklar */
article h2 {
    color: #333;
    border-bottom: 2px solid #333;
}
```

### Form Yapısı

```css
/* Label'dan sonraki input */
label + input {
    margin-top: 5px;
}

/* Form grubundaki tüm input'lar */
.form-group input {
    width: 100%;
    padding: 10px;
}

/* Checkbox'tan sonraki label */
input[type="checkbox"] + label {
    margin-left: 5px;
}
```

## ⚠️ Önemli Notlar

1. **Child vs Descendant**: Child seçici (`>`) sadece doğrudan çocukları seçer, descendant seçici (` `) tüm torunları seçer.

2. **Adjacent vs General Sibling**: Adjacent sibling (`+`) sadece hemen sonraki kardeşi seçer, general sibling (`~`) tüm sonraki kardeşleri seçer.

3. **Performans**: Child seçici (`>`) descendant seçiciye göre daha hızlıdır çünkü sadece bir seviye kontrol eder.

4. **Okunabilirlik**: Karmaşık kombinatör seçiciler yerine, mümkün olduğunca class seçiciler kullanılmalıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


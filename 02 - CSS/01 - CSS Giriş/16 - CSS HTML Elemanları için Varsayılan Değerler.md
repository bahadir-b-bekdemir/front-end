# 📋 CSS'DE HTML ELEMANLARI İÇİN VARSAYILAN DEĞERLER

HTML'de (Hyper Text Markup Language - Zengin Metin İşaretleme Dili) kullanılmakta olan tüm elementlerin varsayılan biçimlendirme değerleri bulunur. Bu değerler, tarayıcılar tarafından otomatik olarak uygulanır ve CSS ile değiştirilebilir.

**⚠️ Önemli Not:** Bu varsayılan değerler tarayıcıdan tarayıcıya küçük farklılıklar gösterebilir. Modern web geliştirmede, bu varsayılan değerleri sıfırlamak için CSS Reset veya Normalize CSS kullanımı yaygındır.

---

## 🔗 Link Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `a:link` | `color: (internal value);`<br>`text-decoration: underline;`<br>`cursor: auto;` |
| `a:visited` | `color: (internal value);`<br>`text-decoration: underline;`<br>`cursor: auto;` |
| `a:link:active` | `color: (internal value);` |
| `a:visited:active` | `color: (internal value);` |

---

## 📝 Metin ve Formatlama Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `b` | `font-weight: bold;` |
| `strong` | `font-weight: bold;` |
| `i` | `font-style: italic;` |
| `em` | `font-style: italic;` |
| `cite` | `font-style: italic;` |
| `dfn` | `font-style: italic;` |
| `var` | `font-style: italic;` |
| `u` | `text-decoration: underline;` |
| `ins` | `text-decoration: underline;` |
| `s` | `text-decoration: line-through;` |
| `del` | `text-decoration: line-through;` |
| `strike` | `text-decoration: line-through;` |
| `small` | `font-size: smaller;` |
| `sub` | `vertical-align: sub;`<br>`font-size: smaller;` |
| `sup` | `vertical-align: super;`<br>`font-size: smaller;` |
| `mark` | `background-color: yellow;`<br>`color: black;` |
| `code` | `font-family: monospace;` |
| `kbd` | `font-family: monospace;` |
| `samp` | `font-family: monospace;` |
| `pre` | `display: block;`<br>`font-family: monospace;`<br>`white-space: pre;`<br>`margin: 1em 0;` |
| `abbr` | Değer yok |
| `bdi` | Değer yok |
| `bdo` | `unicode-bidi: bidi-override;` |
| `q` | `display: inline;`<br>`q::before { content: open-quote; }`<br>`q::after { content: close-quote; }` |

---

## 📄 Başlık Elementleri (Headings)

| Element | Varsayılan Değer |
|---------|------------------|
| `h1` | `display: block;`<br>`font-size: 2em;`<br>`margin-top: 0.67em;`<br>`margin-bottom: 0.67em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |
| `h2` | `display: block;`<br>`font-size: 1.5em;`<br>`margin-top: 0.83em;`<br>`margin-bottom: 0.83em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |
| `h3` | `display: block;`<br>`font-size: 1.17em;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |
| `h4` | `display: block;`<br>`margin-top: 1.33em;`<br>`margin-bottom: 1.33em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |
| `h5` | `display: block;`<br>`font-size: 0.83em;`<br>`margin-top: 1.67em;`<br>`margin-bottom: 1.67em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |
| `h6` | `display: block;`<br>`font-size: 0.67em;`<br>`margin-top: 2.33em;`<br>`margin-bottom: 2.33em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`font-weight: bold;` |

---

## 📦 Blok Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `div` | `display: block;` |
| `p` | `display: block;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;` |
| `blockquote` | `display: block;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 40px;`<br>`margin-right: 40px;` |
| `address` | `display: block;`<br>`font-style: italic;` |
| `article` | `display: block;` |
| `aside` | `display: block;` |
| `section` | `display: block;` |
| `header` | `display: block;` |
| `footer` | `display: block;` |
| `nav` | `display: block;` |
| `main` | Değer yok |
| `details` | `display: block;` |
| `summary` | `display: block;` |
| `hr` | `display: block;`<br>`margin-top: 0.5em;`<br>`margin-bottom: 0.5em;`<br>`margin-left: auto;`<br>`margin-right: auto;`<br>`border-style: inset;`<br>`border-width: 1px;` |

---

## 📋 Liste Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `ul` | `display: block;`<br>`list-style-type: disc;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`padding-left: 40px;` |
| `ol` | `display: block;`<br>`list-style-type: decimal;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`padding-left: 40px;` |
| `li` | `display: list-item;` |
| `dl` | `display: block;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;` |
| `dt` | `display: block;` |
| `dd` | `display: block;`<br>`margin-left: 40px;` |
| `menu` | `display: block;`<br>`list-style-type: disc;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 0;`<br>`margin-right: 0;`<br>`padding-left: 40px;` |

---

## 📊 Tablo Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `table` | `display: table;`<br>`border-collapse: separate;`<br>`border-spacing: 2px;`<br>`border-color: gray;` |
| `thead` | `display: table-header-group;`<br>`vertical-align: middle;`<br>`border-color: inherit;` |
| `tbody` | `display: table-row-group;`<br>`vertical-align: middle;`<br>`border-color: inherit;` |
| `tfoot` | `display: table-footer-group;`<br>`vertical-align: middle;`<br>`border-color: inherit;` |
| `tr` | `display: table-row;`<br>`vertical-align: inherit;`<br>`border-color: inherit;` |
| `th` | `display: table-cell;`<br>`vertical-align: inherit;`<br>`font-weight: bold;`<br>`text-align: center;` |
| `td` | `display: table-cell;`<br>`vertical-align: inherit;` |
| `caption` | `display: table-caption;`<br>`text-align: center;` |
| `col` | `display: table-column;` |
| `colgroup` | `display: table-column-group;` |

---

## 📝 Form Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `form` | `display: block;`<br>`margin-top: 0em;` |
| `fieldset` | `display: block;`<br>`margin-left: 2px;`<br>`margin-right: 2px;`<br>`padding-top: 0.35em;`<br>`padding-bottom: 0.625em;`<br>`padding-left: 0.75em;`<br>`padding-right: 0.75em;`<br>`border: 2px groove (internal value);` |
| `legend` | `display: block;`<br>`padding-left: 2px;`<br>`padding-right: 2px;`<br>`border: none;` |
| `label` | `cursor: default;` |
| `input` | Değer yok |
| `button` | Değer yok |
| `select` | Değer yok |
| `textarea` | Değer yok |
| `output` | `display: inline;` |
| `optgroup` | Değer yok |
| `option` | Değer yok |
| `datalist` | `display: none;` |
| `meter` | Değer yok |
| `progress` | Değer yok |

---

## 🖼️ Medya ve Görsel Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `img` | `display: inline-block;` |
| `picture` | Değer yok |
| `audio` | Değer yok |
| `video` | Değer yok |
| `canvas` | Değer yok |
| `embed:focus` | `outline: none;` |
| `iframe:focus` | `outline: none;` |
| `iframe[seamless]` | `display: block;` |
| `object:focus` | `outline: none;` |
| `figure` | `display: block;`<br>`margin-top: 1em;`<br>`margin-bottom: 1em;`<br>`margin-left: 40px;`<br>`margin-right: 40px;` |
| `figcaption` | `display: block;` |
| `map` | `display: inline;` |
| `area` | `display: none;` |
| `source` | Değer yok |
| `track` | Değer yok |

---

## 🏗️ Yapısal Elementler

| Element | Varsayılan Değer |
|---------|------------------|
| `html` | `display: block;` |
| `html:focus` | `outline: none;` |
| `body` | `display: block;`<br>`margin: 8px;` |
| `body:focus` | `outline: none;` |
| `head` | `display: none;` |
| `span` | Değer yok |
| `br` | Değer yok |
| `wbr` | Değer yok |

---

## 🔧 Meta ve Script Elementleri

| Element | Varsayılan Değer |
|---------|------------------|
| `base` | Değer yok |
| `link` | `display: none;` |
| `meta` | Değer yok |
| `script` | `display: none;` |
| `style` | `display: none;` |
| `noscript` | Değer yok |
| `title` | `display: none;` |
| `param` | `display: none;` |
| `menuitem` | Değer yok |
| `dialog` | Değer yok |

---

## 🌐 Diğer Elementler

| Element | Varsayılan Değer |
|---------|------------------|
| `time` | Değer yok |
| `ruby` | Değer yok |
| `rt` | `line-height: normal;` |
| `rp` | Değer yok |

---

## 💡 CSS Reset ve Normalize

Modern web geliştirmede, tarayıcıların varsayılan stillerini sıfırlamak veya normalize etmek için CSS Reset veya Normalize CSS kullanımı yaygındır.

### CSS Reset Örneği

```css
/* Basit CSS Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Link stillerini sıfırla */
a {
    text-decoration: none;
    color: inherit;
}

/* Liste stillerini sıfırla */
ul, ol {
    list-style: none;
}
```

### Normalize CSS

Normalize CSS, tarayıcılar arası tutarlılık sağlamak için varsayılan stilleri normalize eder (sıfırlamaz).

**Popüler Kütüphaneler:**
- **Normalize.css** - Tarayıcılar arası tutarlılık
- **Reset CSS** - Tüm stilleri sıfırlar
- **Modern CSS Reset** - Modern yaklaşım

---

## 🎯 Önemli Notlar

1. **Tarayıcı Farklılıkları:** Varsayılan değerler tarayıcıdan tarayıcıya farklılık gösterebilir. Özellikle margin ve padding değerleri.

2. **CSS Reset:** Modern projelerde CSS Reset veya Normalize CSS kullanımı önerilir.

3. **Box-Sizing:** Varsayılan olarak `box-sizing: content-box` kullanılır. Modern projelerde `border-box` kullanımı önerilir:

```css
* {
    box-sizing: border-box;
}
```

4. **Display Değerleri:** 
   - Blok elementler: `display: block`
   - Inline elementler: `display: inline`
   - Liste elementleri: `display: list-item`
   - Tablo elementleri: `display: table`, `table-cell`, vb.

5. **Margin Collapse:** Dikey margin'ler birleşir (collapse), yatay margin'ler birleşmez.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

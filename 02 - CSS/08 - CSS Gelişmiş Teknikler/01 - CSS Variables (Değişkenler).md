# 🎨 CSS VARIABLES (DEĞİŞKENLER)

CSS Custom Properties (Özel Özellikler) veya CSS Variables (Değişkenler), CSS'de değişken tanımlamak ve kullanmak için kullanılan modern bir özelliktir.

## 📋 CSS Variables Nedir?

CSS Variables, değerleri tek bir yerde tanımlayıp birden fazla yerde kullanmanızı sağlar. Bu sayede kod tekrarını azaltır ve bakımı kolaylaştırır.

## 🎯 Değişken Tanımlama

CSS değişkenleri `--` (çift tire) ile başlar ve genellikle `:root` içinde tanımlanır.

```css
:root {
    --primary-color: #0066cc;
    --secondary-color: #ff6600;
    --font-size-base: 16px;
    --spacing-unit: 8px;
}
```

## 💡 Değişken Kullanma

Değişkenler `var()` fonksiyonu ile kullanılır.

```css
.button {
    background-color: var(--primary-color);
    font-size: var(--font-size-base);
    padding: var(--spacing-unit);
}
```

## 🔄 Fallback Değerler

Değişken tanımlı değilse, fallback (yedek) değer kullanılabilir.

```css
.element {
    color: var(--text-color, #333);  /* --text-color yoksa #333 kullan */
    margin: var(--spacing, 10px 20px);  /* --spacing yoksa 10px 20px kullan */
}
```

## 📐 Kapsam (Scope)

CSS değişkenleri kapsam (scope) içinde çalışır.

```css
:root {
    --global-color: blue;
}

.container {
    --local-color: red;  /* Sadece .container içinde geçerli */
}

.item {
    color: var(--global-color);  /* blue */
    background: var(--local-color);  /* red - sadece .container içinde */
}
```

## 🎨 Pratik Örnekler

### Tema Renkleri

```css
:root {
    --primary: #0066cc;
    --secondary: #ff6600;
    --success: #28a745;
    --danger: #dc3545;
    --warning: #ffc107;
    --info: #17a2b8;
}

.button-primary {
    background-color: var(--primary);
}

.button-success {
    background-color: var(--success);
}
```

### Spacing Sistemi

```css
:root {
    --spacing-xs: 4px;
    --spacing-sm: 8px;
    --spacing-md: 16px;
    --spacing-lg: 24px;
    --spacing-xl: 32px;
}

.card {
    padding: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
}
```

### Responsive Font Sizes

```css
:root {
    --font-size-base: 16px;
    --font-size-sm: 14px;
    --font-size-lg: 18px;
    --font-size-xl: 24px;
}

@media (max-width: 768px) {
    :root {
        --font-size-base: 14px;
    }
}

body {
    font-size: var(--font-size-base);
}
```

### Dark Mode

```css
:root {
    --bg-color: #ffffff;
    --text-color: #333333;
    --border-color: #cccccc;
}

[data-theme="dark"] {
    --bg-color: #1a1a1a;
    --text-color: #ffffff;
    --border-color: #444444;
}

body {
    background-color: var(--bg-color);
    color: var(--text-color);
    border-color: var(--border-color);
}
```

## 🔧 JavaScript ile Değişken Değiştirme

CSS değişkenleri JavaScript ile dinamik olarak değiştirilebilir.

```javascript
// Değişken değerini değiştir
document.documentElement.style.setProperty('--primary-color', '#ff0000');

// Değişken değerini oku
const primaryColor = getComputedStyle(document.documentElement)
    .getPropertyValue('--primary-color');
```

## ⚠️ Önemli Notlar

1. **Kapsam**: Değişkenler tanımlandıkları kapsamda geçerlidir.

2. **Kalıtım**: Değişkenler kalıtılır (inherit).

3. **Fallback**: Her zaman fallback değer sağlayın.

4. **Browser Support**: Modern tarayıcılarda desteklenir.

5. **Case Sensitive**: Değişken isimleri büyük/küçük harf duyarlıdır.

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


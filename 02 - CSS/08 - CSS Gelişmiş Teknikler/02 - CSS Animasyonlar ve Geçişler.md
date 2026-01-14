# 🎬 CSS ANİMASYONLAR VE GEÇİŞLER

CSS'de animasyonlar ve geçişler, HTML elementlerinin görsel değişimlerini yumuşak ve akıcı bir şekilde gerçekleştirmek için kullanılır.

## 🔄 `transition` (Geçiş)

Element özelliklerindeki değişiklikleri yumuşak bir şekilde geçiş yapar.

### Temel Kullanım

```css
.element {
    transition: property duration timing-function delay;
}
```

### Özellikler

- `transition-property` - Hangi özellik geçiş yapacak
- `transition-duration` - Geçiş süresi
- `transition-timing-function` - Geçiş hız eğrisi
- `transition-delay` - Geçiş gecikmesi

### 💡 Örnekler

```css
/* Basit geçiş */
.button {
    background-color: blue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: red;
}

/* Çoklu özellik */
.card {
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

/* Tüm özellikler */
.element {
    transition: all 0.3s ease;
}
```

## 🎯 Timing Functions (Hız Eğrileri)

Geçişin nasıl ilerleyeceğini belirler.

```css
.element {
    transition-timing-function: ease;        /* Varsayılan */
    transition-timing-function: linear;      /* Sabit hız */
    transition-timing-function: ease-in;      /* Yavaş başla */
    transition-timing-function: ease-out;     /* Yavaş bitir */
    transition-timing-function: ease-in-out; /* Yavaş başla ve bitir */
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1); /* Özel eğri */
}
```

## 🎬 `@keyframes` (Animasyon Kareleri)

Animasyonun adımlarını tanımlar.

```css
@keyframes slideIn {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

/* Veya yüzde kullanarak */
@keyframes fadeIn {
    0% {
        opacity: 0;
    }
    50% {
        opacity: 0.5;
    }
    100% {
        opacity: 1;
    }
}
```

## 🎭 `animation` (Animasyon)

`@keyframes` ile tanımlanan animasyonları uygular.

### Özellikler

- `animation-name` - Animasyon adı
- `animation-duration` - Animasyon süresi
- `animation-timing-function` - Hız eğrisi
- `animation-delay` - Gecikme
- `animation-iteration-count` - Tekrar sayısı
- `animation-direction` - Yön
- `animation-fill-mode` - Doldurma modu
- `animation-play-state` - Oynatma durumu

### 💡 Örnekler

```css
.element {
    animation: slideIn 0.5s ease-in-out;
}

/* Detaylı kullanım */
.element {
    animation-name: slideIn;
    animation-duration: 0.5s;
    animation-timing-function: ease-in-out;
    animation-delay: 0.2s;
    animation-iteration-count: 3;
    animation-direction: alternate;
    animation-fill-mode: forwards;
}

/* Kısa yazım */
.element {
    animation: slideIn 0.5s ease-in-out 0.2s 3 alternate forwards;
}
```

## 💡 Pratik Örnekler

### Hover Efekti

```css
.button {
    background-color: blue;
    transition: background-color 0.3s ease, transform 0.2s ease;
}

.button:hover {
    background-color: darkblue;
    transform: translateY(-2px);
}
```

### Fade In Animasyonu

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.element {
    animation: fadeIn 1s ease-in;
}
```

### Slide In Animasyonu

```css
@keyframes slideInFromLeft {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

.slide-in {
    animation: slideInFromLeft 0.5s ease-out;
}
```

### Loading Spinner

```css
@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

.spinner {
    animation: spin 1s linear infinite;
}
```

### Pulse Efekti

```css
@keyframes pulse {
    0%, 100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.1);
    }
}

.pulse {
    animation: pulse 2s ease-in-out infinite;
}
```

## ⚠️ Önemli Notlar

1. **Performans**: `transform` ve `opacity` animasyonları en performanslıdır.

2. **Will-Change**: Performans için `will-change` özelliği kullanılabilir.

```css
.element {
    will-change: transform;
}
```

3. **GPU Hızlandırma**: `transform` ve `opacity` GPU'da işlenir.

4. **Animasyon Kontrolü**: JavaScript ile animasyonlar kontrol edilebilir.

```javascript
element.style.animationPlayState = 'paused';
```

5. **Erişilebilirlik**: `prefers-reduced-motion` medya sorgusu ile animasyonları azaltabilirsiniz.

```css
@media (prefers-reduced-motion: reduce) {
    * {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


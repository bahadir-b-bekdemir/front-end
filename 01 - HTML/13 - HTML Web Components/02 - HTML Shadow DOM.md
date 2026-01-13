# 🎭 HTML SHADOW DOM

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Shadow DOM, öğelerin iç yapısını ve stillerini kapsüller.

## 📋 Shadow DOM Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Encapsulation | Stil ve yapı kapsülleme |
| Isolation | Dış etkilerden izolasyon |
| Scoped styles | Kapsamlı stiller |

## 💡 Kullanım Örnekleri

### Temel Shadow DOM

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Shadow DOM</title>
</head>
<body>
    <div id="host"></div>
    
    <script>
        const host = document.getElementById('host');
        const shadow = host.attachShadow({mode: 'open'});
        
        shadow.innerHTML = `
            <style>
                p {
                    color: blue;
                    font-weight: bold;
                }
            </style>
            <p>Shadow DOM içeriği</p>
        `;
    </script>
</body>
</html>
```

### Shadow DOM Mode'ları

```html
<body>
    <div id="open-shadow"></div>
    <div id="closed-shadow"></div>
    
    <script>
        // Open mode - Dışarıdan erişilebilir
        const openHost = document.getElementById('open-shadow');
        const openShadow = openHost.attachShadow({mode: 'open'});
        openShadow.innerHTML = '<p>Open Shadow DOM</p>';
        
        // Closed mode - Dışarıdan erişilemez
        const closedHost = document.getElementById('closed-shadow');
        const closedShadow = closedHost.attachShadow({mode: 'closed'});
        closedShadow.innerHTML = '<p>Closed Shadow DOM</p>';
        
        // Open mode erişimi
        console.log(openHost.shadowRoot); // ShadowRoot
        
        // Closed mode erişimi
        console.log(closedHost.shadowRoot); // null
    </script>
</body>
```

### Shadow DOM ile Custom Element

```html
<body>
    <shadow-button>Tıkla</shadow-button>
    
    <script>
        class ShadowButton extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({mode: 'open'});
                
                shadow.innerHTML = `
                    <style>
                        button {
                            background: #007bff;
                            color: white;
                            border: none;
                            padding: 10px 20px;
                            border-radius: 5px;
                            cursor: pointer;
                        }
                        button:hover {
                            background: #0056b3;
                        }
                    </style>
                    <button>
                        <slot></slot>
                    </button>
                `;
            }
        }
        
        customElements.define('shadow-button', ShadowButton);
    </script>
</body>
```

### Slot Kullanımı

```html
<body>
    <user-profile>
        <span slot="name">Ahmet Yılmaz</span>
        <span slot="email">ahmet@example.com</span>
    </user-profile>
    
    <script>
        class UserProfile extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({mode: 'open'});
                
                shadow.innerHTML = `
                    <style>
                        .profile {
                            border: 1px solid #ccc;
                            padding: 20px;
                        }
                    </style>
                    <div class="profile">
                        <h3><slot name="name"></slot></h3>
                        <p><slot name="email"></slot></p>
                    </div>
                `;
            }
        }
        
        customElements.define('user-profile', UserProfile);
    </script>
</body>
```

### Stil Kapsülleme

```html
<body>
    <style>
        p {
            color: red;
        }
    </style>
    
    <p>Normal paragraf (kırmızı)</p>
    <div id="shadow-host"></div>
    
    <script>
        const host = document.getElementById('shadow-host');
        const shadow = host.attachShadow({mode: 'open'});
        
        shadow.innerHTML = `
            <style>
                p {
                    color: blue;
                }
            </style>
            <p>Shadow DOM paragrafı (mavi - dış stil etkilemez)</p>
        `;
    </script>
</body>
```

## 🎯 Önemli Notlar

- Shadow DOM stil ve yapı kapsülleme sağlar
- `mode: 'open'` dışarıdan erişilebilir
- `mode: 'closed'` dışarıdan erişilemez
- `<slot>` ile içerik projection yapılır
- Shadow DOM içindeki stiller dışarıyı etkilemez

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 🎰 HTML SLOTS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) `<slot>` etiketi, Shadow DOM içinde içerik projection için kullanılır.

## 📋 Slot Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| İçerik projection | Dış içeriği Shadow DOM'a aktarır |
| Named slots | İsimlendirilmiş slotlar |
| Default slot | Varsayılan slot |

## 💡 Kullanım Örnekleri

### Temel Slot

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Slots</title>
</head>
<body>
    <custom-button>Tıkla</custom-button>
    
    <script>
        class CustomButton extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({mode: 'open'});
                shadow.innerHTML = `
                    <style>
                        button {
                            padding: 10px 20px;
                            background: blue;
                            color: white;
                        }
                    </style>
                    <button><slot></slot></button>
                `;
            }
        }
        customElements.define('custom-button', CustomButton);
    </script>
</body>
</html>
```

### Named Slots

```html
<body>
    <user-card>
        <span slot="name">Ahmet Yılmaz</span>
        <span slot="email">ahmet@example.com</span>
    </user-card>
    
    <script>
        class UserCard extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({mode: 'open'});
                shadow.innerHTML = `
                    <div>
                        <h3><slot name="name"></slot></h3>
                        <p><slot name="email"></slot></p>
                    </div>
                `;
            }
        }
        customElements.define('user-card', UserCard);
    </script>
</body>
```

## 🎯 Önemli Notlar

- `<slot>` Shadow DOM içinde kullanılır
- Named slots `slot="name"` ile eşleştirilir
- Default slot tüm içeriği gösterir
- Slot fallback içerik içerebilir

## ✍️ Yazar

**Bahadır B. Bekdemir**


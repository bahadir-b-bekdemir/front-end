# 🧩 HTML CUSTOM ELEMENTS

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Custom Elements, özel HTML etiketleri oluşturmayı sağlar.

## 📋 Custom Elements Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Özel etiketler | Kendi HTML etiketleriniz |
| Yaşam döngüsü | Lifecycle callbacks |
| Encapsulation | Kapsülleme |

## 💡 Kullanım Örnekleri

### Temel Custom Element

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Custom Elements</title>
</head>
<body>
    <my-button>Tıkla</my-button>
    
    <script>
        class MyButton extends HTMLElement {
            constructor() {
                super();
                this.addEventListener('click', this.handleClick);
            }
            
            handleClick() {
                alert('Butona tıklandı!');
            }
        }
        
        customElements.define('my-button', MyButton);
    </script>
</body>
</html>
```

### Shadow DOM ile Custom Element

```html
<body>
    <custom-card title="Başlık" content="İçerik"></custom-card>
    
    <script>
        class CustomCard extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({mode: 'open'});
                
                const title = this.getAttribute('title');
                const content = this.getAttribute('content');
                
                shadow.innerHTML = `
                    <style>
                        .card {
                            border: 1px solid #ccc;
                            padding: 20px;
                            border-radius: 5px;
                        }
                        .title {
                            font-weight: bold;
                            margin-bottom: 10px;
                        }
                    </style>
                    <div class="card">
                        <div class="title">${title}</div>
                        <div>${content}</div>
                    </div>
                `;
            }
        }
        
        customElements.define('custom-card', CustomCard);
    </script>
</body>
```

### Lifecycle Callbacks

```html
<body>
    <lifecycle-element></lifecycle-element>
    
    <script>
        class LifecycleElement extends HTMLElement {
            constructor() {
                super();
                console.log('Constructor çağrıldı');
            }
            
            connectedCallback() {
                console.log('Element DOM\'a eklendi');
                this.textContent = 'Element hazır';
            }
            
            disconnectedCallback() {
                console.log('Element DOM\'dan kaldırıldı');
            }
            
            attributeChangedCallback(name, oldValue, newValue) {
                console.log(`Özellik değişti: ${name} = ${newValue}`);
            }
            
            static get observedAttributes() {
                return ['data-value'];
            }
        }
        
        customElements.define('lifecycle-element', LifecycleElement);
    </script>
</body>
```

### Özelliklerle Custom Element

```html
<body>
    <user-card 
        name="Ahmet Yılmaz" 
        email="ahmet@example.com"
        avatar="avatar.jpg">
    </user-card>
    
    <script>
        class UserCard extends HTMLElement {
            constructor() {
                super();
            }
            
            connectedCallback() {
                this.render();
            }
            
            render() {
                const name = this.getAttribute('name');
                const email = this.getAttribute('email');
                const avatar = this.getAttribute('avatar');
                
                this.innerHTML = `
                    <div style="border: 1px solid #ccc; padding: 20px;">
                        <img src="${avatar}" width="50" height="50">
                        <h3>${name}</h3>
                        <p>${email}</p>
                    </div>
                `;
            }
        }
        
        customElements.define('user-card', UserCard);
    </script>
</body>
```

## 🎯 Önemli Notlar

- Custom element isimleri tire (-) içermelidir
- `HTMLElement` sınıfından türetilmelidir
- `customElements.define()` ile kayıt edilir
- Lifecycle callbacks ile yaşam döngüsü yönetilir
- Shadow DOM ile stil kapsülleme sağlanır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


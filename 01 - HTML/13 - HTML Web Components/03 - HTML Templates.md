# 📄 HTML TEMPLATES

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) `<template>` etiketi, sayfa yüklenirken render edilmeyen HTML şablonları oluşturur.

## 📋 Template Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| Lazy rendering | Sayfa yüklenirken render edilmez |
| JavaScript ile kullanım | `content` özelliği ile erişilir |
| Tekrar kullanılabilir | Aynı template birden fazla kez kullanılabilir |

## 💡 Kullanım Örnekleri

### Temel Template

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Templates</title>
</head>
<body>
    <template id="myTemplate">
        <div class="card">
            <h2></h2>
            <p></p>
        </div>
    </template>
    
    <div id="container"></div>
    
    <script>
        const template = document.getElementById('myTemplate');
        const container = document.getElementById('container');
        
        const clone = template.content.cloneNode(true);
        clone.querySelector('h2').textContent = 'Başlık';
        clone.querySelector('p').textContent = 'İçerik';
        
        container.appendChild(clone);
    </script>
</body>
</html>
```

### Dinamik Template Kullanımı

```html
<body>
    <template id="userCard">
        <div class="user-card">
            <img src="" alt="">
            <h3></h3>
            <p></p>
        </div>
    </template>
    
    <div id="userList"></div>
    
    <script>
        const users = [
            {name: 'Ahmet', email: 'ahmet@example.com', avatar: 'avatar1.jpg'},
            {name: 'Mehmet', email: 'mehmet@example.com', avatar: 'avatar2.jpg'}
        ];
        
        const template = document.getElementById('userCard');
        const list = document.getElementById('userList');
        
        users.forEach(user => {
            const clone = template.content.cloneNode(true);
            clone.querySelector('img').src = user.avatar;
            clone.querySelector('h3').textContent = user.name;
            clone.querySelector('p').textContent = user.email;
            list.appendChild(clone);
        });
    </script>
</body>
```

## 🎯 Önemli Notlar

- Template içeriği sayfa yüklenirken render edilmez
- `content` özelliği ile içeriğe erişilir
- `cloneNode(true)` ile kopyalanır
- JavaScript ile dinamik içerik eklenir

## ✍️ Yazar

**Bahadır B. Bekdemir**


# 📝 HTML GÜVENLİ FORM İŞLEME

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) form güvenliği kritik öneme sahiptir.

## 📋 Güvenlik Önlemleri

| Önlem | Açıklama |
| :----- | :------- |
| Input validation | Girdi doğrulama |
| CSRF protection | CSRF koruması |
| HTTPS | Güvenli bağlantı |
| Sanitization | Girdi temizleme |

## 💡 Kullanım Örnekleri

### Client-Side Validation

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Güvenli Form</title>
</head>
<body>
    <form id="secureForm" method="POST" action="/submit">
        <input type="text" name="username" required 
               pattern="[A-Za-z0-9]{3,20}" 
               title="3-20 karakter, sadece harf ve rakam">
        <input type="email" name="email" required>
        <input type="password" name="password" required minlength="8">
        <button type="submit">Gönder</button>
    </form>
    
    <script>
        document.getElementById('secureForm').addEventListener('submit', function(e) {
            const username = this.username.value;
            if (!/^[A-Za-z0-9]{3,20}$/.test(username)) {
                e.preventDefault();
                alert('Geçersiz kullanıcı adı');
            }
        });
    </script>
</body>
</html>
```

### CSRF Token

```html
<body>
    <form method="POST" action="/submit">
        <input type="hidden" name="csrf_token" value="token_here">
        <input type="text" name="data">
        <button type="submit">Gönder</button>
    </form>
</body>
```

### HTTPS Zorunluluğu

```html
<head>
    <meta http-equiv="Strict-Transport-Security" 
          content="max-age=31536000; includeSubDomains">
</head>
```

## 🎯 Önemli Notlar

- Client-side validation yeterli değildir, server-side da gerekir
- CSRF token kullanın
- HTTPS kullanın
- Girdileri sanitize edin
- SQL injection'dan kaçının (prepared statements)

## ✍️ Yazar

**Bahadır B. Bekdemir**


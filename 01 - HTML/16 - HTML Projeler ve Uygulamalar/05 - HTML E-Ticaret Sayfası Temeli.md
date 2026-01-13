# 🛒 HTML E-TİCARET SAYFASI TEMELİ

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) e-ticaret sayfası temeli ürün satışı için kullanılır.

## 📋 E-Ticaret Bölümleri

| Bölüm | Açıklama |
| :---- | :------- |
| Header | Logo, arama, sepet |
| Products | Ürün listesi |
| Product Detail | Ürün detayı |
| Cart | Sepet |
| Checkout | Ödeme |

## 💡 Kullanım Örnekleri

### Ürün Listesi

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Ticaret</title>
    <style>
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        .product {
            border: 1px solid #ddd;
            padding: 20px;
            text-align: center;
        }
        .product img {
            max-width: 100%;
            height: 200px;
            object-fit: cover;
        }
        .price {
            font-size: 24px;
            color: #e74c3c;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <h1>Mağaza</h1>
        <nav>
            <a href="/cart">Sepet</a>
        </nav>
    </header>
    
    <main>
        <div class="products">
            <div class="product">
                <img src="product1.jpg" alt="Ürün 1">
                <h3>Ürün 1</h3>
                <p class="price">₺199.99</p>
                <button>Sepete Ekle</button>
            </div>
            <div class="product">
                <img src="product2.jpg" alt="Ürün 2">
                <h3>Ürün 2</h3>
                <p class="price">₺299.99</p>
                <button>Sepete Ekle</button>
            </div>
        </div>
    </main>
</body>
</html>
```

## 🎯 Önemli Notlar

- Ürün görselleri ekleyin
- Fiyat bilgilerini gösterin
- Sepet fonksiyonelliği ekleyin
- Responsive tasarım uygulayın

## ✍️ Yazar

**Bahadır B. Bekdemir**


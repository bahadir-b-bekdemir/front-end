# 📁 HTML FILE API

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) File API, dosya okuma ve işleme işlemleri için kullanılır.

## 📋 File API Özellikleri

| API | Açıklama |
| :-- | :------- |
| FileReader | Dosya okuma |
| FileList | Dosya listesi |
| Blob | Binary veri |
| File | Dosya nesnesi |

## 💡 Kullanım Örnekleri

### Dosya Seçme ve Okuma

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>File API</title>
</head>
<body>
    <input type="file" id="fileInput">
    <div id="output"></div>
    
    <script>
        document.getElementById('fileInput').addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    document.getElementById('output').innerHTML = 
                        '<p>Dosya içeriği:</p><pre>' + e.target.result + '</pre>';
                };
                
                reader.readAsText(file);
            }
        });
    </script>
</body>
</html>
```

### Dosya Bilgileri

```html
<body>
    <input type="file" id="fileInput">
    <div id="info"></div>
    
    <script>
        document.getElementById('fileInput').addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                const info = `
                    <p>İsim: ${file.name}</p>
                    <p>Boyut: ${file.size} bytes</p>
                    <p>Tip: ${file.type}</p>
                    <p>Son değişiklik: ${file.lastModified}</p>
                `;
                
                document.getElementById('info').innerHTML = info;
            }
        });
    </script>
</body>
```

### Çoklu Dosya Seçme

```html
<body>
    <input type="file" multiple id="fileInput">
    <div id="fileList"></div>
    
    <script>
        document.getElementById('fileInput').addEventListener('change', function(e) {
            const files = e.target.files;
            let list = '<ul>';
            
            for (let i = 0; i < files.length; i++) {
                list += `<li>${files[i].name} (${files[i].size} bytes)</li>`;
            }
            
            list += '</ul>';
            document.getElementById('fileList').innerHTML = list;
        });
    </script>
</body>
```

### Resim Önizleme

```html
<body>
    <input type="file" accept="image/*" id="imageInput">
    <img id="preview" style="max-width: 300px;">
    
    <script>
        document.getElementById('imageInput').addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    document.getElementById('preview').src = e.target.result;
                };
                
                reader.readAsDataURL(file);
            }
        });
    </script>
</body>
```

### Blob Oluşturma

```html
<body>
    <button onclick="downloadFile()">Dosya İndir</button>
    
    <script>
        function downloadFile() {
            const content = "Bu bir test dosyasıdır.";
            const blob = new Blob([content], { type: 'text/plain' });
            const url = URL.createObjectURL(blob);
            
            const a = document.createElement('a');
            a.href = url;
            a.download = 'test.txt';
            a.click();
            
            URL.revokeObjectURL(url);
        }
    </script>
</body>
```

### Dosya Yükleme İlerlemesi

```html
<body>
    <input type="file" id="fileInput">
    <progress id="progress" value="0" max="100"></progress>
    <div id="status"></div>
    
    <script>
        document.getElementById('fileInput').addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                const reader = new FileReader();
                
                reader.onprogress = function(e) {
                    if (e.lengthComputable) {
                        const percentLoaded = Math.round((e.loaded / e.total) * 100);
                        document.getElementById('progress').value = percentLoaded;
                        document.getElementById('status').textContent = 
                            percentLoaded + '% yüklendi';
                    }
                };
                
                reader.onload = function() {
                    document.getElementById('status').textContent = 'Yükleme tamamlandı';
                };
                
                reader.readAsText(file);
            }
        });
    </script>
</body>
```

## 🎯 Önemli Notlar

- FileReader API dosya okuma için kullanılır
- `readAsText()` metin dosyaları için
- `readAsDataURL()` resim önizleme için
- `readAsArrayBuffer()` binary veri için
- Blob API ile dosya oluşturulabilir
- `accept` özelliği ile dosya tipi filtrelenebilir

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


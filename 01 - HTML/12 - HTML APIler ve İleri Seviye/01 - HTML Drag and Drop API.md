# 🖱️ HTML DRAG AND DROP API

**HTML**'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) Drag and Drop API, öğelerin sürüklenip bırakılmasını sağlar.

## 📋 Drag and Drop Özellikleri

| Özellik | Açıklama |
| :------ | :------- |
| `draggable` | Öğenin sürüklenebilir olması |
| `ondragstart` | Sürükleme başladığında |
| `ondrag` | Sürükleme sırasında |
| `ondragend` | Sürükleme bittiğinde |
| `ondragenter` | Hedef alana girildiğinde |
| `ondragover` | Hedef alan üzerinde |
| `ondrop` | Bırakıldığında |

## 💡 Kullanım Örnekleri

### Temel Drag and Drop

```html
<!doctype html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>Drag and Drop</title>
    <style>
        .draggable {
            width: 100px;
            height: 100px;
            background: blue;
            color: white;
            display: inline-block;
            margin: 10px;
            cursor: move;
        }
        .dropzone {
            width: 300px;
            height: 300px;
            border: 2px dashed #ccc;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="draggable" draggable="true" id="drag1">Sürükle</div>
    
    <div class="dropzone" id="dropzone">
        Bırak buraya
    </div>
    
    <script>
        const dragElement = document.getElementById('drag1');
        const dropZone = document.getElementById('dropzone');
        
        dragElement.addEventListener('dragstart', function(e) {
            e.dataTransfer.setData('text', e.target.id);
        });
        
        dropZone.addEventListener('dragover', function(e) {
            e.preventDefault();
            dropZone.style.borderColor = 'blue';
        });
        
        dropZone.addEventListener('drop', function(e) {
            e.preventDefault();
            const data = e.dataTransfer.getData('text');
            const element = document.getElementById(data);
            dropZone.appendChild(element);
            dropZone.style.borderColor = '#ccc';
        });
    </script>
</body>
</html>
```

### Çoklu Öğe Sürükleme

```html
<body>
    <div class="container">
        <div class="item" draggable="true">Öğe 1</div>
        <div class="item" draggable="true">Öğe 2</div>
        <div class="item" draggable="true">Öğe 3</div>
    </div>
    
    <div class="dropzone" id="target"></div>
    
    <script>
        document.querySelectorAll('.item').forEach(item => {
            item.addEventListener('dragstart', function(e) {
                e.dataTransfer.setData('text/html', this.innerHTML);
            });
        });
        
        document.getElementById('target').addEventListener('drop', function(e) {
            e.preventDefault();
            const data = e.dataTransfer.getData('text/html');
            this.innerHTML += '<div>' + data + '</div>';
        });
        
        document.getElementById('target').addEventListener('dragover', function(e) {
            e.preventDefault();
        });
    </script>
</body>
```

### Dosya Sürükleme

```html
<body>
    <div id="dropzone" style="border: 2px dashed #ccc; padding: 20px;">
        Dosyaları buraya sürükleyin
    </div>
    <div id="fileList"></div>
    
    <script>
        const dropzone = document.getElementById('dropzone');
        const fileList = document.getElementById('fileList');
        
        dropzone.addEventListener('dragover', function(e) {
            e.preventDefault();
            dropzone.style.borderColor = 'blue';
        });
        
        dropzone.addEventListener('dragleave', function(e) {
            dropzone.style.borderColor = '#ccc';
        });
        
        dropzone.addEventListener('drop', function(e) {
            e.preventDefault();
            dropzone.style.borderColor = '#ccc';
            
            const files = e.dataTransfer.files;
            for (let file of files) {
                const p = document.createElement('p');
                p.textContent = file.name + ' - ' + file.size + ' bytes';
                fileList.appendChild(p);
            }
        });
    </script>
</body>
```

## 🎯 Önemli Notlar

- `draggable="true"` özelliği sürüklenebilirliği etkinleştirir
- `preventDefault()` `dragover` ve `drop` olaylarında kullanılmalıdır
- `dataTransfer` API'si veri aktarımı için kullanılır
- Dosya sürükleme için `files` özelliği kullanılır

---

## ✍️ Yazar

**Bahadır B. Bekdemir**


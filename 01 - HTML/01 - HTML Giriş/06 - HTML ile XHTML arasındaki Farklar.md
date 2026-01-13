# 🔄 HTML İLE XHTML ARASINDAKİ FARKLAR

## 📋 XHTML Nedir?

**XHTML** (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili), yeni nesil web tasarım standartlarına verilen addır. HTML'in (Hyper Text Markup Language) (zengin metin işaretleme dilinin) başında bulunan **X** harfi işaretleme dili olarak tanımlanan, **XML**'in (Extensible Markup Language) (genişletilebilir işaretleme dilinin) özelliklerinin HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) içerisinde kullanılabileceği anlamına gelmektedir.

## 🔍 Temel Farklar

**HTML** (Hyper Text Markup Language) (zengin metin işaretleme dili), **SGML**'in (Standard Generalized Markup Language) (standart genelleştirilmiş işaretleme dilinin) bir türevidir. Ekranda görüntülenecek içeriğin yapılandırılmasını sağlar. **XML** (Extensible Markup Language) (genişletilebilir işaretleme dili) ise içeriğin görüntülenmesini değil, içeriğin tamamen yapılandırılmasından sorumlu bir dildir.

HTML (Hyper Text Markup Language) (zengin metin işaretleme dili) ile **XHTML** (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili) arasındaki tek fark, **doctype**'ın (belge türü tanımının) sayfaya bir diğer deyiş ile belgeye tanımlanmasından kaynaklanır.

## 📝 Doctype Tanımlamaları

HTML'de (Hyper Text Markup Language) (zengin metin işaretleme dilinde) **doctype (belge türü tanımı)** tanımlaması kısadır ve hiçbir kısıtlaması yoktur. XHTML'de (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dilinde) birden fazla doctype (belge türü tanımı) tanımlaması ile farklı içerikler için kısıtlama yapılabilmesi sağlanabilir.

Doctype (belge türü tanımı) tanımlaması XHTML'in (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dilinin) bir parçası değildir ve asıl tanımlanma amacı belge içerisinde kullanılan elementlerin standartları için ek bir bağlantı sağlamasıdır. Özellikle **XML** (Extensible Markup Language) (genişletilebilir işaretleme dili) kullanılan sayfalarda çok sık kullanılır. XHTML (Extensible Hypertext Markup Language) (genişletilebilir büyütülmüş metin işaretleme dili) **3 tip belge bildirimi** sunar. Bunlar **strict (katı)**, **transitional (geçiş)** ve **frameset (çerçeve seti)** dir.

## 🔒 Strict (Katı)

Diğer 2 bildirime göre daha katı ve net bir denetleme sağlamaktadır. Genellikle **CSS** (Cascading Style Sheets) (basamaklı stil şablonları veya basamaklı biçim sayfaları) ile yapılan tasarımlarda strict (katı) tercih edilmektedir. Dolayısı ile **browser'lar (tarayıcılar)** bu tercihe göre sayfadaki kodlamayı yorumlar. Kullanım şekli aşağıdaki gibidir:

```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

## 🔄 Transitional (Geçiş)

En çok kullanılmakta olan sayfa geçerliliği denetleyicisidir. Çünkü, strict'e (katıya) göre çok daha esnektir ve sayfadaki bazı yazım hatalarını göz ardı edebilir. Kullanım şekli aşağıdaki gibidir:

```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

## 🖼️ Frameset (Çerçeve Seti)

Genelde **frame (çerçeve)** kullanılan sitelerde sayfanın geçerliliğini denetlemede tercih edilmektedir. Kullanım şekli aşağıdaki gibidir:

```html
<!doctype html PUBLIC "-//W3C//DTD Xhtml 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

## 🚀 HTML 5 ve Sonrası

**HTML** (Hyper Text Markup Language) (zengin metin işaretleme dili) **5** ve daha sonrası sürümlerde yukarıdaki uzun bildirimlerin hiçbirini kullanmaya gerek yoktur. Kısaca aşağıdaki şekilde yazılabilir:

```html
<!doctype html>
```

---

## ✍️ Yazar

**Bahadır B. Bekdemir**

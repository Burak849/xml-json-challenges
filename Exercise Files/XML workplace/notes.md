# XML Notları

## Tags

Etiketler, başlıkları temsil etmek için kullanılabilir:

```xml
<city>Tokyo</city>
```

### Örnek:

```xml
<color>
  <red></red>
  <blue></blue>
  <green></green>
</color>
```

### Nitelikli Kullanım (Attributes ile)

```xml
<tag key="word">Can be used like this</tag>
<cost current="USD">40.99</cost>
<projectedValue decimal="2" confidence="5">23.90</projectedValue>
```

## Namespaces

* XML'de **namespace** kullanımı, etiketleri benzersiz şekilde tanımlamak için yapılır.

## Whitespace

* Boşluk, satır sonu, tab gibi karakterlerdir.
* **Tırnak içinde olmadıkça** beyaz boşlukların bir önemi yoktur.

---

## XML Formatlama Kuralları

* Her yeni etiket seviyesi için **girinti (indentation)** eklenmeli
* İçinde başka etiket bulunmayan tag'ler **aynı satırda** açılıp kapatılabilir
* Satırlar çok uzunsa **satır sonu (line break)** eklenmeli
* Diğer etiketleri içeren tag'ler **ayrı satırlarda** yer almalıdır

---

## Schemas

* XML yapıları **şema dosyaları (XSD)** ile tanımlanabilir.
* XSD dosyaları da birer **XML dosyasıdır**, anlaşılması kolaydır.
* Belgelendirme ve doğrulama işlemleri için oldukça faydalıdır.

---

## JSON ve XML Kıyaslaması

* API isteklerinde genellikle hem **JSON** hem **XML** desteklenir.
* Aynı veriyi hem JSON hem XML ile belgelemek için tek tablo kullanılabilir.

  * **Sütunlar aynı** olmalı
  * **Anahtar ve etiket adları aynı** olmalı
  * **Veri tipleri** aynı olmalı

### Yapısal Fark

* **XML**: Etiketlerde **attribute (nitelik)** kullanılabilir
* **JSON**: Attribute yoktur, her şey key-value çiftidir

---

## Kullanışlı Toollar

### Word Processor:

* Microsoft Word, Google Docs

### CMS / Wiki:

* MediaWiki
* MindTouch

### Content  Management Sistemleri:

* WordPress

### Ticari Araçlar:

* Flare
* RoboHelp
* Help+Manual

### İşaretleme Tabanlı Çözümler:

* Jekyll
* Sphinx
* GitHub
* Read the Docs

---

## Dokümantasyon Araçları

* **Swagger**
* **Stripe API Docs**

---

## XSD Dosyaları

* Şema dosyalarıdır
* XML dosyalarını tanımlar
* Kendi içinde de **XML formatındadır**
* Belgeleme yapılabilir

---


# Çalışmalar

## TV program
Represents a request to record a television program.

| Element | Description | Type | Required | Notes |
| --- | --- | --- | --- | --- |
| recordTV | Top level | TV program data | Required | |
| &nbsp; &nbsp; date | Date of the program | string | Optional | Format is YYYY-MM-DD HH:MM:SS. Default value is today's date. |
| &nbsp; &nbsp; time | Time the program begins | number | Required | Attributes: **format** has values `24` or `12` for 24 or 12 hour formats. Format is HH:MM, with am or pm afterwards for 12 hour format |
| &nbsp; &nbsp; duration | Length of the program | number | Required | In hours |
| &nbsp; &nbsp; channel | Channel to record | number | Required | |

## TV program format
Represents a request to record a television program.

| Element | Attribute | Description | Type | Required | Notes |
| --- | --- | --- | --- | --- | --- |
| recordTV | | Top level | TV program data | Required | |
| &nbsp; &nbsp; when | | Date and time when the program starts | | Required |  |
|  | date | Date | string | Optional | Format is YYYY-MM-DD. Default value is today's date. |
|  | time | Time the program begins | string | Required | Format is HH:MM, with am or pm afterwards for 12 hour format |
|  | format | Format for the time: either 12 hour or 24 hour | string | Required| Valid values: `24` or `12`  |
| &nbsp; &nbsp; duration | hours | Length of the program | number | Required | In hours |
| &nbsp; &nbsp; station | channel | Channel to record | number | Required | |
<!--! it will be completed for my notes -->
This is my **documantation**.

# JSON Notları

## Temel Yapı

* JSON (**JavaScript Object Notation**) verileri anahtar-değer (key-value) çiftleriyle tanımlar.
* Hafif yapılı, okunabilir ve makine tarafından kolay işlenebilir bir formattır.
* Genellikle **API veri alışverişi** için kullanılır.

### Basit Örnek:

```json
{
  "name": "Burak",
  "age": 25,
  "city": "Bursa"
}
```

## Veri Tipleri

* **String**: "text"
* **Number**: 10, 20.5
* **Boolean**: true, false
* **Array**: \["a", "b", "c"]
* **Object**: { "key": "value" }
* **Null**: null

## JSON Objects

* JSON nesnesi, `{}` içinde tanımlanır
* Anahtarlar daima **tırnak içinde** olur

```json
{
  "product": {
    "id": 123,
    "name": "Laptop",
    "specs": {
      "ram": "16GB",
      "cpu": "i7"
    }
  }
}
```

## Arrays

* JSON'da diziler `[]` ile belirtilir
* Dizi içinde nesneler, stringler, sayılar veya dizi olabilir

```json
[
  {
    "name": "Ali",
    "age": 25
  },
  {
    "name": "Veli",
    "age": 30
  }
]
```

## JSON vs XML

| Özellik           | JSON              | XML                            |
| ----------------- | ----------------- | ------------------------------ |
| Yapı              | Key-Value         | Tag tabanlı                    |
| Veri Tipi Tanımı  | Doğrudan (native) | Metin tabanlı, tip belirtilmez |
| Okunabilirlik     | Yüksek            | Daha az okunabilir             |
| Boyut             | Daha küçük        | Daha büyük                     |
| Destek            | Modern API'ler    | Eski sistemlerle uyumlu        |
| Attribute Desteği | Yok               | Var                            |

## JSON Formatlama Kuralları

* Anahtarlar daima tırnak içinde olmalı
* Virgül son elemandan sonra **konulmamalıdır**
* Boş değerler null olarak verilir
* JSON, **tek kök objeye** sahip olmalıdır

## API ve JSON

* Modern API'lerin çoğu, veri iletiminde **JSON** kullanır
* Swagger, Postman, Insomnia gibi aracılar bu yapıyı kolayca destekler

## Belgeleme ve Araçlar

### JSON Görselleştirme & Doğrulama:

* [JSONLint](https://jsonlint.com/)
* [Quicktype](https://quicktype.io/)
* [Mockaroo](https://mockaroo.com/)

### JSON'dan Tip Üretme:

* TypeScript, C#, Java için otomatik şema dönüşümleri sağlanabilir

```json
{
  "user": {
    "id": 1,
    "name": "Burak",
    "roles": ["admin", "editor"]
  }
}
```

## JSON Schema

* JSON yapısını doğrulamak için kullanılır
* JSON'un XSD'si gibidir

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "name": { "type": "string" },
    "age": { "type": "number" }
  },
  "required": ["name", "age"]
}
```

---



# Status Codes 
Every web request returns a *status code* that says whether it was successful or had an error. The most famous status code is `404`. 

## Common codes 
| Code | Description | 
| --- | --- | 
| 200 | OK | 
| 403 | Forbidden | 
| 404 | Not found |


## Menu
Represents a menu.

| Element | Description | Type | Notes |
|---- | --- | --- | --- |
| Top level | Menu columns | array of menu column objects | |
| &nbsp; &nbsp; header | Name of the column | string | |
| &nbsp; &nbsp; items | List of menu items under the column | array of menu items | |
| &nbsp; &nbsp; id | ID of the menu | string | |
| &nbsp; &nbsp; label | Label that is displayed in the user interface | string | |

## Song

Represents a song.

| Element | Description | Type | Notes |
|---- | --- | --- | --- |
| song | Top level | song data object | |
| &nbsp; &nbsp; title | Song title | string | |
| &nbsp; &nbsp; artist | Song artist | string | |
| &nbsp; &nbsp; musicians | A list of musicians who play on the song | array of string | |

## Comment
Represents a comment on a posting.

| Element | Description | Type | Required | Notes |
| --- | --- | --- | --- | --- |
| comment | Top level | comment data object | Required | |
| &nbsp; &nbsp; userId | ID of the user making the comment | string | Required | |
| &nbsp; &nbsp; discId | ID of the discussion that is being commented on | string | Required | |
| &nbsp; &nbsp; time | Time that the comment was posted | string | Optional | YYYY-MM-DD HH:MM:SS Greenwich Mean Time. Default is the time the comment is received by the server.|
| &nbsp; &nbsp; text | Text of the comment | string | Required | |


## Meeting
Represents a request for a meeting in a calendar.

| Element | Description | Type | Required | Notes |
|---- | --- | --- | --- | --- |
| meeting | Top level | meeting data object | Required | |
| &nbsp; &nbsp; time | When meeting starts.  | string | Required | Format is YYYY-MM-DD HH:MM:SS. Timezone is GMT. |
| &nbsp; &nbsp; duration | How long meeting lasts | number | Required | In minutes |
| &nbsp; &nbsp; description | Description of the meeting | string | Required | |
| &nbsp; &nbsp; location | Location of the meeting | number | Optional | Default is an empty string |
| &nbsp; &nbsp; reminder | How many minutes before the meeting a reminder event should take place | number | Optional | Default is 10 minutes |
| &nbsp; &nbsp; invitees | List of email address of people to invite to the meeting | array of string | Optional | The strings should be valid email addresses. Default is an empty array. |

## Forecast for days
Represents the weather forecast for multiple days.

| Element | Description | Type | Notes |
| --- | --- | --- | --- |
| longitude | Longitude of the location where the forecast takes place | number |  |
| latitude | Latitude of the location where the forecast takes place | number |  |
| forecast | Daily forecast | array of daily forecast objects |  |
| &nbsp; &nbsp; date | Date of the forecast | string | Format is YYYY-MM-DD|
| &nbsp; &nbsp; description | Text description of the weather | string | Valid values: sunny, overcast, partly cloudy, raining, and snowing |
| &nbsp; &nbsp; maxTemp | High temperature | number | In degrees Celsius |
| &nbsp; &nbsp; minTemp | Low temperature | number | In degrees Celsius |
| &nbsp; &nbsp; windSpeed | Wind speed | number | In kilometers per hour |
| &nbsp; &nbsp; danger | true if the weather conditions are dangerous; otherwise, false. | Boolean | |

## Forecast for a day
Represents the weather forecast for one day.

| Element | Description | Type | Notes |
|---- | --- | --- | --- |
| date | Date of the forecast | string | Format is YYYY-MM-DD |
| description | Text description of the weather | string | Valid values: sunny, overcast, partly cloudy, raining, and snowing |
| maxTemp | High temperature | number | In degrees Celsius |
| minTemp | Low temperature | number | In degrees Celsius |
| windSpeed | Wind speed | number | In kilometers per hour |
| danger | true if the weather conditions are dangerous; otherwise, false. | Boolean | |

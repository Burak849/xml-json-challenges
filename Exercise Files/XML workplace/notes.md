<!-- 

! XML notes
Tags => you can create them for any titles like <city>Tokyo</city>

etc:
<color>
<red></red>
<blue></blue>
<green></green>
</color>

<tag key="word">Can be used like this</tag>
<cost current="USD">40.99</cost>
<projectedValue decimal="2" confidence="5">23.90</projectedValue>

you have namespaces to uniquely identify them
White space means spaces new lines tabs etc.
White spaces doesnt matter unless its inside quotation marks

Good XML formatting Guidelines:
- In general, add an indent for every new level of tags
- Tags that do not contain other tags can have start and end tags on the same line
- Use line breaks if the lines are too long
- Tags that contain other tags should be on their own lines

Schemas= xml structured can be described with a schema, they can be very helpful in documenting xml and XSD files are themselves XML files, so its pretty esay to figure out how they work

API requests can often use either JSON and XML. In this case, you can try to create one table that documents both formats. => table columns are the same, key names and tag names should be identical, type should be identical

Complex types => multiple tables can be hard to identify the type

The biggest structural difference between JSON and XML is that XML has attributes and JSON doesnt. If API uses both XML doesnt have attributes. 


 -->


Represents a request to record a television program.

| Element | Description | Type | Required | Notes |
| --- | --- | --- | --- | --- |
| recordTV | Top level | TV program data | Required | |
| &nbsp; &nbsp; date | Date of the program | string | Optional | Format is YYYY-MM-DD HH:MM:SS. Default value is today's date. |
| &nbsp; &nbsp; time | Time the program begins | number | Required | Attributes: **format** has values `24` or `12` for 24 or 12 hour formats. Format is HH:MM, with am or pm afterwards for 12 hour format |
| &nbsp; &nbsp; duration | Length of the program | number | Required | In hours |
| &nbsp; &nbsp; channel | Channel to record | number | Required | |


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

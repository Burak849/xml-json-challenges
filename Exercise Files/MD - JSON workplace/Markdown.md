<!-- My documantation -->
<!-- 

Objects are JSON's dictionaries
Most JSON has nesting.
Table for each object type




 -->


<!--! it will be completed for my notes -->
This is my **documantation**

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

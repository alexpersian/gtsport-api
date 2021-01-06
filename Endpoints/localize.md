## Localize

Base URL: `https://www.gran-turismo.com/us/gtsport/module/community/localize/`

### Description
Localize is a GET resource that provides a JSON response containing a ton of objects and strings that are used throughout the website and in some cases referenced via api responses. These are key value pairs where the key corresponds to what the text value is used for.
The language version of the file's contents is controled by the two character country code in the 1st URL segment. For example: `us` or `jp`

### Example Usage
The [event](event.md) endpoint returns an object that contains a course code hash.
This hash can be used to lookup the localized name of the course through the JSON table provided. You compare the course code hash to the CourseName object keys.

Partial event endpoint response:
```
	"tracks": [
  		{
		"course_code": "44cc5bba82772146ae612e3f1e8a5f84",
		"WeatherList": [
  			{
			"weather_id": 2187
			}
		],
		}
	],
```
In this example the course code hash is `44cc5bba82772146ae612e3f1e8a5f84`.

Find the key in the localize file that contains the course code hash:
```
gt7sp.game.COMMON.CourseName.44cc5bba82772146ae612e3f1e8a5f84
```

This key corresponds to the following localized string:
```
"KYOTO DRIVING PARK - YAMAGIWA+MIYABI"
```

### Related Resources
* [meta](meta.md)
* [tags](tags.md)

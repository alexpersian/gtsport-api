## Localize

Base URL: `https://www.gran-turismo.com/us/gtsport/module/community/localize/`

### Description
Localize is a GET resource that provides objects and strings that are used throughout the website and in some cases referenced via api responses.
The language version of the file's contents is controled by the two character country code in the 1st URL segment. For example: `us` or `jp`

### Example Usage
the event endpoint returns an object with a course code hash.
compare the course code hash to the CourseName objects

partial event endpoint response
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

localize file string:
```
gt7sp.game.COMMON.CourseName.44cc5bba82772146ae612e3f1e8a5f84": "KYOTO DRIVING PARK - YAMAGIWA+MIYABI"
```


### Related Resources
* [meta](Endpoints/meta.md)
* [tags](Endpoints/tags.md)


## Profile

**NOTE:** It is *not* possible to perform a reverse lookup of PSN ID -> GTS ID. The service only provides information given you already have the GTS ID.

Base URL: `https://www.gran-turismo.com/us/api/gt7sp`

### Endpoint
`/profile`

### Request Method
`POST`

### Universal Parameters
- `user_no`: String, user profile number
- `job`: String, request job number. See below

### Job IDs
- `1`: Provides basic info like PSN id, country code, profile photo id

    Example Request:
    `POST https://www.gran-turismo.com/us/api/gt7sp/profile/?user_no=9568550&job=1`

    Example Response:
    ```
    {
      "profile": {
        "id": "xGranadier",
        "status": "1",
        "number": "9568550",
        "country": "us",
        "profile_photo_id": "8224232633225479708-0"
      }
    }
    ```

- `3`: Provides detailed stats about user's GTS records

    Example Request:
    `POST https://www.gran-turismo.com/us/api/gt7sp/profile/?user_no=9568550&job=3`

    Example Response:
    ```
    {
      "stats": {
        "user_no": "9568550",
        "manufacturer_id": "17",
        "stats": "{  \"achievement_arcade\": \"0,0,0,0,0,0,0,300,0,300,0,0,0,300,0,0,0,200,0,0,0,0,0,0,0,0,300,0,0,0,0,0,0,0,100,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0\",  \"achievement_history\": \"300,263,300,300,0,203,300,300,187,214,125,300,142,300,253,200,0,50,126,203\",  \"achievement_history_raw\": \"811708,25573406,618184,10531,0,21005910,277915,177926,44,15945300,3,27,7,354,13,103,0,5,34,93\",  \"buy_car_count\": 44,  \"campaign_progress\": \"100,100,100\",  \"car_count\": 217,  \"credit_earned\": 21005910,  \"delivery_reward_car_ticket\": 0,  \"level\": 37,  \"level_progress\": 3,  \"livery_count\": 0,  \"login_count\": 93,  \"mileage_earned\": 277915,  \"nickname\": \"xGranadier\",  \"photo_count\": 103,  \"profile_color\": 9,  \"ride_car_id\": 3253,  \"total_running_meter\": 25573406,  \"xp\": 1536}",
        "ugc_all_count": "26",
        "ugc_photo_3_count": "11",
        "ugc_photo_11_count": "5",
        "ugc_livery_1_count": "0",
        "ugc_livery_2_count": "0",
        "ugc_livery_3_count": "0",
        "ugc_decal_count": "0",
        "ugc_replay_count": "10",
        "comment": "Brooklyn",
        "driver_class": "4",
        "driver_point": "23630",
        "manner_point": "99",
        "race_count": "354",
        "driver_point_up_rate": "68",
        "driver_photo_id": "8295639381191197212-0",
        "profile_photo_id": "8224232633225479708-0",
        "follower_count": "37"
      }
    }
    ```

- `12`: Provides a Driver Rating history for the user. 
    **Additional params:**
    * `month_begin` 1-12
    * `month_end` 1-12
    * `year_begin` YYYY
    * `year_end` YYYY
    
    Example Request:
    `POST https://www.gran-turismo.com/us/api/gt7sp/profile/?user_no=9568550&job=12&month_begin=10&month_end=10&year_begin=2019&year_end=2019`

    Example Response:
    ```
    {
      "stats_history": [
        {
          "year": "2019",
          "month": "10",
          "stats1": [
            "22510",
            "21317",
            "21228",
            "20390",
            "22535",
            "20703",
            "0",
            "22773",
            "31618",
            "0",
            "29776",
            "29229",
            "26339",
            "0",
            "25690",
            "25329",
            "24883",
            "23847",
            "0",
            "23630",
            "0",
            "0",
            "22705" 
          ],
          "stats2": [ // more numbers ],
          // stats3 - n ...
        }
      ]
    }
    ```

- `13`: Provides a history of Sport Mode race stats.

    Example Request:
    `POST https://www.gran-turismo.com/us/api/gt7sp/profile/?user_no=9568550&job=13`

    Example Response:
    ```
    {
      "sport_stats":[
        {
          "index":"1",
          "race":"572",
          "win":"24",
          "top5":"169",
          "pole_position":"35",
          "rank_qualify":"4317",
          "rank_final":"4742",
          "rank_change":"425",
          "lap":"3132",
          "lead_lap":"115",
          "top_match":"0"
        },
        //...
      ]
    }
    ```

### Private Job IDs
Some job ids are not available publicly and will return 403 errors if you attempt to use them. These include: `2`, `4-11`, and `14`. It is unknown what these jobs correspond to or the data they provide. `14` is the last valid job ID. Higher numbers simply return 400 errors.

### Retrieving Driver Photos from GTS
The member profile photo, if set by the player, may be retrieved via job 1 or job 3 as `profile_photo_id`.  
Likewise, the driver's racing suit portrait may be retrieved via job 3 as `driver_photo_id`

The image asset files are stored on AWS with the following suffixes and file extensions:
- AWS path is `https://s3.amazonaws.com/gt7sp-prod/photo/`
- member profile photo : `_0.jpg`
- driver full portrait with transparent background : `_22.png`
- driver half portrait with transparent background: `_14.png`

To retrieve the image asset, parse the photo ID as follows to get the path:
`Example: driver_photo_id: 8574875682894774301-0`
- drop the last two characters of the string [`-0`] `$id = 8574875682894774301`
- take the last six digits [`774301`]
- reorder the last six digits in pairs `[CCBBAA]  =  AA/BB/CC = 01/43/77`
- cat the AWS asset path, ID and extension. (member profile photos uses extension `_0.jpg` | driver images use `_22.png` or `_14.png`)
- using the driver_photo_id example: `https://s3.amazonaws.com/gt7sp-prod/photo/01/43/77/8574875682894774301_14.png`

***
Profile Photo Example:
<img src="https://s3.amazonaws.com/gt7sp-prod/photo/08/97/47/8224232633225479708_0.jpg" alt="profile_photo_id" width="128" height="128"/>

Driver Image Examples:
<img src="https://s3.amazonaws.com/gt7sp-prod/photo/01/43/77/8574875682894774301_14.png" alt="driver_photo_id half portrait" width="200"/>
<img src="https://s3.amazonaws.com/gt7sp-prod/photo/01/43/77/8574875682894774301_22.png" alt="driver_photo_id full portrait" width="200"/>
***

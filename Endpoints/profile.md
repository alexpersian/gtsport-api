## Profile

Base URL: `https://www.gran-turismo.com/us/api/gt7sp`

### Endpoint
`/profile`

### Universal Parameters
- `user_no`: String, user profile number
- `job`: String, request job number. See below

### Job IDs
- `1`: Provides basic info like PSN id, country code, profile photo id
    ```
    Example Response:
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
    ```
    Example Response:
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
- `12`: Provides a stats history for the user. Requires additional parameters.
    * `month_begin` 1-12
    * `month_end` 1-12
    * `year_begin` YYYY
    * `year_end` YYYY
    ```
    Example Response:
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

### Private Job IDs
Some job ids are not available publicly and will return 403 errors if you attempt to use them. These include: `2`, `4-11`, and `14`. It is unknown what these jobs correspond to or the data they provide. `14` is the last valid job ID. Higher numbers simply return 400 errors.
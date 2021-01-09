## Driver Ranking

Provides details on a driver rankings.

Base URL: `https://www.gran-turismo.com/us/api/gt7sp`

### Endpoint
`/ranking`

### Request Method
`POST`

### Universal Parameters
- `user_no`: String, user profile number
- `job`: String, request job number. See below

### Job IDs
- `1`: Specific river ranking details.
    **Additional params:**
    * `board_id`: String, ID of the region board. Retrieved from `/event` endpoint.

    Example Request:
    `POST https://www.gran-turismo.com/es/api/gt7sp/ranking/?job=1&user_no=1761906&board_id=1030442`

    Example Response:
    ```
    {
      "ranking":[
        {
          "ranking_id":"1214394018",
          "board_id":"1030442",
          "user_id":"lluisRV",
          "profile_photo_id":"8440335044841865741-0",
          "user_no":"1761906",
          "create_time":"2021-01-03T18:59:06Z",
          "score":"539757",
          "user_country":"es",
          "driver_class":"4",
          "manner_point":"94"
        }
      ]
    }
    ```

- `3`: Regional driver rankings
  **Additional params**
  * `board_id`: String, ID of the region board. Retrieved from `/event` endpoint.
  * `begin`: String, place on rank board to start
  * `end`: String, place on rank board to end

  Example Request:
  "Top 10 in region"
  `POST https://www.gran-turismo.com/es/api/gt7sp/ranking/?job=3&board_id=1030442&begin=1&end=10`

  Example Response:
  ```
  {
    "ranking":[
      {
        "ranking_id":"1211940317",
        "board_id":"1030442",
        "user_id":"Williams_BRacer",
        "profile_photo_id":"4971975167656100869-0",
        "user_no":"5980830",
        "create_time":"2021-01-01T15:11:51Z",
        "score":"519604",
        "replay":"3",
        "user_country":"it",
        "driver_class":"6",
        "manner_point":"99"
      },
      {
        "driver_display_name":"L. Pobric",
        "ranking_id":"1210998059",
        "board_id":"1030442",
        "user_id":"VLX_Pepi",
        "profile_photo_id":"5765176040032043012-0",
        "user_no":"2477416",
        "create_time":"2020-12-31T14:21:23Z",
        "score":"520447",
        "replay":"3",
        "user_country":"de",
        "driver_class":"6",
        "driver_star":"true",
        "manner_point":"99"
      },
      //...
    ]
  }
  ```

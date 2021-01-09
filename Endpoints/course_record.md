## Course Record

Provides course records for a driver. This is specific to Sport Mode records.

Base URL: `https://www.gran-turismo.com/us/api/gt7sp`

### Endpoint
`/course_record`

### Request Method
`POST`

### Universal Parameters
- `user_no`: String, user profile number
- `job`: String, request job number. See below

### Job IDs
- `1`: Gives course records
    **Additional params:**
    * `course_id`: String, ID of the track
    * `category_id`: String, TBD
    * `is_category`: String, TBD

    Example Request:
    `POST https://www.gran-turismo.com/us/api/gt7sp/course_record/?job=1&user_no=9568550&course_id=9&category_id=0&is_category=0`

    Example Response:
    ```
    {
      "course_record":[
        {
          "update_time":"2020-06-02T17:51:32Z",
          "user_no":"9568550",
          "category_id":"13",
          "course_id":"9",
          "result":"84350",
          "car":"c1ca0f9c010377abcdfb656fd5f186c1"
        },
        {
          "update_time":"2020-01-21T00:07:48Z",
          "user_no":"9568550",
          "category_id":"12",
          "course_id":"9",
          "result":"89844",
          "car":"04e2df052e2139b9885e94786732a0bb"
        }
      ]
    }
    ```

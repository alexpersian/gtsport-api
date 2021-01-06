## Event

Base URL: `https://www.gran-turismo.com/us/api/gt7sp`

### Endpoint
`/event`

### Universal Parameters
- `job`: String, request job number. See below

### Other Parameters (requirements vary based on Job ID)
- `event_id_csv`: String, comma separated Event ID
- `channel_id_csv`: String, comma separated Channel ID accepts the following:
	- 11 : Nations
	- 12 : Manufacturers
	-  1 : Daily Race A
	-  2 : Daily Race B
	-  3 : Daily Race C
	- Example: `1,2,3` for all daily races
- `begin_date`: String, date format YYYY-MM-DD
- `end_date`: String, date format YYYY-MM-DD

### Job IDs
- `1`: Event Details

	**Requires: event_id_csv**

	Example Request:
	`POST https://www.gran-turismo.com/us/api/gt7sp/event/?job=1&event_id_csv=24465`

	Example Response:
	```
	{
	  "event":[
	    {
	      "event_id":"24465",
	      "create_time":"2020-12-25T04:09:24Z",
	      "update_time":"2020-12-25T04:09:24Z",
	      "value":[
	        {
	          "GameParameter":{
	            "championship":0,
	            "events":[
	              {
	                "event_id":24465,
	                "championship_id":0,
	                "season_id":0,
	                "round_id":0,
	                "championship_color":null,
	                "game_mode":"SPORT_DAILY_RACE",
	                "event_type":"RACE",
	                "sports_mode":"DAILY",
	                "information":{
	                  "title":{
	                    "JP":"\u30c7\u30a4\u30ea\u30fc\u30ec\u30fc\u30b9 A",
	                    //...
	                  },
	                  "one_line_title":{
	                    "JP":"A",
	                    //...
	                  },
	                  "description":{
	                    "JP":"",
	                    //...
	                  },
	                  "registration_notice":{
	                    "JP":"",
	                    //...
	                  },
	                  "event_target":{
	                    "JP":"",
	                    //...
	                  },
	                  "event_restrict":null,
	                  "logo_image_path":null,
	                  "flyer_image_path":null
	                },
	                "entry_set":[
	                  {
	                    "entry_generate":{
	                      "player_entry_base_array":[
	                        //empty
	                      ]
	                    }
	                  }
	                ],
	                "race":{
	                  "behavior_damage_type":"WEAK",
	                  "behavior_slip_stream_type":"SIMULATION",
	                  "boost_level":null,
	                  "low_mu_type":"REAL",
	                  "entry_max":12,
	                  "start_type":"GRID",
	                  "consume_fuel":0,
	                  "consume_tire":0,
	                  "race_limit_laps":4,
	                  "race_limit_minute":0,
	                  "nos_amount_scale":1.0,
	                  "pit_constraint":0,
	                  "need_compound_use":"0",
	                  "limit_fuel_capacity":0
	                },
	                "ranking":{
	                  "board_id":1020439,
	                  "begin_date":null,
	                  "end_date":null
	                },
	                "regulation":{
	                  "limit_tire_f":8,
	                  "need_tire_f":8,
	                  "use_bop":1,
	                  "tuning":1,
	                  "need_driver_class":null,
	                  "car_category_types":[
	                    "GR4"
	                  ],
	                  "cars":null,
	                  "cars_count":0
	                },
	                "refueling_speed":0,
	                "track_index":0,
	                "matching_method":0,
	                "is_uncertain_event":0,
	                "qualifier_initial_tank":-1,
	                "is_seasonal_event":0,
	                "begin_date":null,
	                "end_date":null,
	                "online_timeattack_registration_key":null,
	                "online_timeattack_type":null,
	                "np_regions":null
	              }
	            ],
	            "online_room":{
	              "qualifier_consume_tire":-1,
	              "qualifier_consume_fuel":-1
	            },
	            "tracks":[
	              {
	                "course_code":"74ad0cdc10df08eb301c90d5d1f3a8d9",
	                "WeatherList":[
	                  {
	                    "weather_id":3953
	                  }
	                ]
	              }
	            ]
	          }
	        },
	        "15"
	      ]
	    }
	  ]
	}
	```

- `2`: Event Calendar (Date Range)
		
	**Requires: channel_id_csv, begin_date, end_date**

	Example Request:
	`POST https://www.gran-turismo.com/us/api/gt7sp/event/?job=2&channel_id_csv=1&begin_date=2021-01-04&end_date=2021-01-10`

	Example Response:
	```
	{
	  "event_calendar":[
	    {
	      "event_calendar_id":"3977695",
	      "region_id":"3",
	      "channel_id":"1",
	      "start_time":"2021-01-05T00:00:00Z",
	      "end_time":"2021-01-05T00:14:59Z",
	      "event_id":"24465"
	    },
	    {
	      "event_calendar_id":"3977696",
	      "region_id":"3",
	      "channel_id":"1",
	      "start_time":"2021-01-05T00:20:00Z",
	      "end_time":"2021-01-05T00:34:59Z",
	      "event_id":"24465"
	    },
	    //...
	   ]
	 }
	```

- `3`: Event Calendar (Upcoming)

	**Requires: channel_id_csv**

	Example Request:
	`POST https://www.gran-turismo.com/us/api/gt7sp/event/?job=3&channel_id_csv=1,2,3`

	Example Response:
	```
	{
	  "event_calendar":[
	    {
	      "event_calendar_id":"3977784",
	      "region_id":"3",
	      "channel_id":"1",
	      "start_time":"2021-01-06T05:40:00Z",
	      "end_time":"2021-01-06T05:54:59Z",
	      "event_id":"24465"
	    },
	    //...
	    {
	      "event_calendar_id":"3978287",
	      "region_id":"3",
	      "channel_id":"2",
	      "start_time":"2021-01-06T05:30:00Z",
	      "end_time":"2021-01-06T05:44:59Z",
	      "event_id":"24466"
	    },
	    //...
	    {
	      "event_calendar_id":"3978745",
	      "region_id":"3",
	      "channel_id":"3",
	      "start_time":"2021-01-06T05:30:00Z",
	      "end_time":"2021-01-06T05:54:59Z",
	      "event_id":"24467"
	    },
	    //...
	  ]
	}
	```

***
### Notes
> Please see [Localize](localize.md) for discussion on retrieving the Circuit Name from the course_code ID

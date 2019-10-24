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
	Example `1,2,3` for all daily races
- `begin_date`: String, date format YYYY-MM-DD
- `end_date`: String, date format YYY-MM-DD

### Job IDs
- `1`: Detailed Info about a specific Race Event
	Requires: event_id_csv
    ```
    Example Response:
    {
		"event": [
  			{
			"event_id": "20317",
			"create_time": "2019-09-16T10:20:08Z",
			"update_time": "2019-09-18T08:36:41Z",
			"value": [
  				{
				"GameParameter": {
					"championship": 0,
					"events": [
  						{
						"event_id": 20317,
						"championship_id": 12,
						"season_id": 1977,
						"round_id": 9,
						"championship_color": "#960014",
						"game_mode": "SPORT_CHAMPIONSHIP",
						"event_type": "RACE",
						"sports_mode": "MANUFACTURER",
						"information": {
							"title": {
								...
							},
							"one_line_title": {
								...
							},
							"description": {
								... 	
							},
							"registration_notice": {
								...
							},
							"event_target": {
								...
							},
							"event_restrict": {
								...
							},
							"logo_image_path": "img_131_6b91f4d083b5866c964db2c483559f03.png",
							"flyer_image_path": "img_132_ad7ed60cd617294486a19ebec6f70c5b.png"
						},
						"entry_set": [
  							{
							"entry_generate": {
								"player_entry_base_array": null
								}
							}
						],
						"race": {
							"behavior_damage_type": "MIDDLE",
							"behavior_slip_stream_type": "REAL",
							"boost_level": null,
							"low_mu_type": "REAL",
							"entry_max": 20,
							"start_type": "FORMATION_ROLL_A",
							"consume_fuel": 3,
							"consume_tire": 9,
							"race_limit_laps": 14,
							"race_limit_minute": 0,
							"pit_constraint": 0,
							"need_compound_use": "7",
							"limit_fuel_capacity": 0
						},
						"ranking": {
							"board_id": 1040158,
							"begin_date": null,
							"end_date": null
						},
						"regulation": {
							"limit_tire_f": 10,
							"need_tire_f": 8,
							"use_bop": 1,
							"tuning": 1,
							"need_driver_class": "-1",
							"car_category_types": [
							  "GR3"
							],
							"cars": null,
							"cars_count": 0
						},
						"refueling_speed": 7,
						"track_index": 0,
						"matching_method": 0,
						"is_uncertain_event": 0,
						"is_seasonal_event": 0,
						"begin_date": null,
						"end_date": null,
						"online_timeattack_registration_key": null,
						"online_timeattack_type": null,
						"np_regions": null
						}
					],
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
				}
				},
  				"60"
			],
			}
		],
	}

    ```
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
- `end_date`: String, date format YYY-MM-DD

### Job IDs
- `1`: Detailed Info about a specific Race Event

	**Requires: event_id_csv**
    
    Example Response:
    ```
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
								...multiple language strings...
							},
							"description": {
								...multiple language strings...	
							},
							"registration_notice": {
								...multiple language strings...
							},
							"event_target": {
								...multiple language strings...
							},
							"event_restrict": {
								...multiple language strings...
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

- `10`: Season Info

	Example Response
	```
	{
		"season_information": {
			"seasons": [
  				{
				"season_id": 303,
				"championship_id": 0,
				"global_ranking_id": 0,
				"color": {
					"a": "255",
					"r": "0",
					"g": "40",
					"b": "95"
				},
				"rounds": [
  					{
					"round_id": "1",
					"start_date": "2017-11-05T02:00:00Z",
					"end_date": "2017-11-05T06:39:59Z",
					"car_category_type": "GR4",
					"event_id": "5475",
					"sports_mode": "NATIONS",
					"championship_valid_race_count": "3",
					"logo_image_path": "img_6.png",
					"flyer_image_path": "img_14.png",
					"title": {
						"JP": "FIA GT ネイションズカップ",
						"US": "FIA Gran Turismo Championship // Nations Cup",
						"GB": "FIA Gran Turismo Championship // Nations Cup",
						"FR": "FIA Gran Turismo Championship // Nations Cup",
						"DE": "FIA Gran Turismo Championship // Nations Cup",
						"IT": "FIA Gran Turismo Championship // Nations Cup",
						"ES": "FIA Gran Turismo Championship // Nations Cup",
						"PT": "FIA Gran Turismo Championship // Nations Cup",
						"NL": "FIA Gran Turismo Championship // Nations Cup",
						"RU": "FIA Gran Turismo Championship // Nations Cup",
						"KR": "FIA GT ​네이션스 ​컵",
						"TW": "FIA Gran Turismo Championship // Nations Cup",
						"EL": "FIA Gran Turismo Championship // Nations Cup",
						"TR": "FIA Gran Turismo Championship // Nations Cup",
						"PL": "FIA Gran Turismo Championship // Nations Cup",
						"CZ": "FIA Gran Turismo Championship // Nations Cup",
						"BP": "FIA Gran Turismo Championship // Nations Cup",
						"MS": "FIA Gran Turismo Championship // Nations Cup",
						"AR": "FIA Gran Turismo Championship // Nations Cup",
						"TH": " FIA Gran Turismo Championship // Nations Cup"
					},
					"event_target": {
						"JP": "シリーズ2017 - テストシーズン1",
						"US": "Series 2017 - Test Season 1",
						"GB": "Series 2017 - Test Season 1",
						"FR": "Série 2017 - Saison test 1",
						"DE": "Serie 2017 – Testsaison 1",
						"IT": "Campionato 2017 - Stagione di prova 1",
						"ES": "Series 2017 - Temporada de prueba 1",
						"PT": "Série 2017 - Época de teste 1",
						"NL": "2017-serie - Testseizoen 1",
						"RU": "Series 2017 - Test Season 1",
						"KR": "Series 2017 - Test Season 1",
						"TW": "2017系列賽：測試賽季 1",
						"EL": "Πρωτάθλημα 2017 - Δοκιμαστική Σεζόν 1",
						"TR": "2017 Serisi - Test Sezonu 1",
						"PL": "Zawody 2017 – sezon próbny 1",
						"CZ": "Series 2017 - Test Season 1",
						"BP": "Série 2017 - Temporada de Teste 1",
						"MS": "Serie 2017 - Temporada de prueba 1",
						"AR": "1 سلسلة 2017 - موسم تجريبي",
						"TH": "​ซี​รีส์ 2017 - ​ฤดูกาล​แข่ง​ทดสอบ 1"
					},
					"course_code": "597704ed70764fcfaee9660932e90677",
					"matching_method": 0,
					"is_uncertain_event": 0
				},
				...
	```

- `2`: Event Calendar by date
	
	**Requires: channel_id_csv, begin_date, end_date**

	Example Response
	```
	{
		"event_calendar": [
  			{
			"event_calendar_id": "2834232",
			"region_id": "6",
			"channel_id": "11",
			"start_time": "2019-10-30T22:00:00Z",
			"end_time": "2019-10-30T22:59:59Z",
			"event_id": "20256"
			}
		],
	}
	```


- `3`: Event Calendar (Daily or Series Races)

	**Requires: channel_id_csv**

	Example Response
	```
	{
		event_calendar": [
  			{
			"event_calendar_id": "3000346",
			"region_id": "3",
			"channel_id": "1",
			"start_time": "2019-10-24T07:40:00Z",
			"end_time": "2019-10-24T07:54:59Z",
			"event_id": "20558"
			},
  			{
			"event_calendar_id": "3000347",
			"region_id": "3",
			"channel_id": "1",
			"start_time": "2019-10-24T08:00:00Z",
			"end_time": "2019-10-24T08:14:59Z",
			"event_id": "20558"
			},
			{
			"event_calendar_id": "3000849",
			"region_id": "3",
			"channel_id": "2",
			"start_time": "2019-10-24T07:30:00Z",
			"end_time": "2019-10-24T07:44:59Z",
			"event_id": "20559"
			},
			{
			"event_calendar_id": "3000850",
			"region_id": "3",
			"channel_id": "2",
			"start_time": "2019-10-24T07:50:00Z",
			"end_time": "2019-10-24T08:04:59Z",
			"event_id": "20559"
			},
			{
			"event_calendar_id": "3001281",
			"region_id": "3",
			"channel_id": "3",
			"start_time": "2019-10-24T07:30:00Z",
			"end_time": "2019-10-24T07:54:59Z",
			"event_id": "20560"
			},
			{
			"event_calendar_id": "3001282",
			"region_id": "3",
			"channel_id": "3",
			"start_time": "2019-10-24T08:00:00Z",
			"end_time": "2019-10-24T08:24:59Z",
			"event_id": "20560"
			}
		],
	}
	```
***
### Notes
> Please see [Localize](Endpoints/localize.md) for discussion on retrieving the Circuit Name from the course_code ID
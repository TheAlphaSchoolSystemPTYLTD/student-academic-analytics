**getStatisticTestingData**
----
	Returns an array of statistic types data in JSON format.

* **Version History:**

	TASS v50.4 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`

* **Params:**

	**Required:**

	`stat_type [string]` - status type

	`group_code [string]` - group code

	`test_code [string]` - test code

	`study_yr [string]` - study year

	`criteria_code [string]` - criteria code

	`year_grp [string]` - year group

	**Optional:**

	none

	**Conditional:**

	none

* **Success Response:**

	```javascript
	{
		"DATA": [
			{
				"PL_FLAG": "Y",
				"YEAR_GRP": 6,
				"STAT_TYPE": "AVG",
				"RESULT_STAT": 12345.12345,
				"TEST_CODE": "TEST",
				"TK_FLAG": "Y",
				"GROUP_CODE": "N",
				"CRITERIA_CODE": "TXT",
				"SC_FLAG": "Y",
				"STUDY_YR": 2015
			}
		],
		"token": {
			"year_grp": 6,
			"stat_type": "AVG",
			"test_code": "TEST",
			"timestamp": "{ts '2019-03-21 09:52:33'}",
			"group_code": "N",
			"criteria_code": "TXT",
			"study_yr": 2015
		}
	}
	```

* **Error Response:**

	`stat_type` not supplied
	```javascript
	"__invalid": {
		"stat_type": "field is required"
	}
	```

	`group_code` not supplied
	```javascript
	"__invalid": {
		"group_code": "field is required"
	}
	```

	`test_code` not supplied
	```javascript
	"__invalid": {
		"test_code": "field is required"
	}
	```

	`study_yr` not supplied
	```javascript
	"__invalid": {
		"study_yr": "field is required"
	}
	```

	`criteria_code` not supplied
	```javascript
	"__invalid": {
		"criteria_code": "field is required"
	}
	```

	`year_grp` not supplied
	```javascript
	"__invalid": {
		"year_grp": "field is required"
	}
	```

* **Sample Parameters:**

	```javascript
	{"stat_type":"AVG","group_code":"N","test_code":"TEST","study_yr":"2015","criteria_code":"TXT","year_grp":"6"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://local.tassweb.net.au/tassweb/api/?appcode=API17&v=2&method=getStatisticTestingData&token=V8LLLCBhCwZRz%2B6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w%3D&company=10
	```

* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStatisticTestingData" />
		<input type="hidden" name="appcode" value="API17" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="2" />
		<textarea name="token">V8LLLCBhCwZRz+6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w=</textarea>
	</form>
	```

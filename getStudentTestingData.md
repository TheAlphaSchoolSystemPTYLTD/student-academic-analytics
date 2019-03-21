**getStudentTestingData**
----
	Returns an array of student testing data data in JSON format.

* **Version History:**

	TASS v50.4 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`

* **Params:**

	**Required:**

	`test_code [string]` - test code

	`study_yr [string]` - study year

	`criteria_code [string]` - criteria code

	`year_grp [string]` - year group

	**Optional:**

	`stud_code [string]` - student code

	**Conditional:**

	none

* **Success Response:**

	```javascript
	{
		"DATA": [
			{
				"TEXT_RESULT": "WP",
				"YEAR_GRP": "",
				"INT_RESULT": "",
				"STUD_CODE": "0010050",
				"TEST_CODE": 2013,
				"DEC_RESULT": "NAPLAN",
				"CRITERIA_CODE": "Banksia",
				"STUDY_YR": 9
			}
		],
		"token": {
			"year_grp": 9,
			"stud_code": "0010050",
			"test_code": "NAPLAN",
			"timestamp": "{ts '2019-03-21 09:53:55'}",
			"criteria_code": "WP",
			"study_yr": 2013
		}
	}
	```

* **Error Response:**

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
	{"test_code":"NAPLAN","study_yr":"2013","criteria_code":"WP","year_grp":"9","stud_code":"0010050"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://local.tassweb.net.au/tassweb/api/?appcode=API17&v=2&method=getStudentTestingData&token=V8LLLCBhCwZRz%2B6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w%3D&company=10
	```

* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStudentTestingData" />
		<input type="hidden" name="appcode" value="API17" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="2" />
		<textarea name="token">V8LLLCBhCwZRz+6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w=</textarea>
	</form>
	```

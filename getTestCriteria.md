**getTestCriteria**
----
	Returns an array of testing criteria data in JSON format.

* **Version History:**

	TASS v50.4 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`

* **Params:**

	**Required:**

	`test_code [string]` - test code

	**Optional:**

	none

	**Conditional:**

	none

* **Success Response:**

	```javascript
	{
		"DATA": [
			{
				"PL_FLG": "Y",
				"CRITERIA_DESC": "Reading Scale Score",
				"TEST_CODE": "NAPLAN",
				"RESULT_DATA_TYPE": "I",
				"SC_FLG": "Y",
				"CRITERIA_CODE": "RSS",
				"TK_FLG": "Y"
			},
			{
				"PL_FLG": "Y",
				"CRITERIA_DESC": "Spelling Scale Score",
				"TEST_CODE": "NAPLAN",
				"RESULT_DATA_TYPE": "I",
				"SC_FLG": "Y",
				"CRITERIA_CODE": "SSS",
				"TK_FLG": "Y"
			}
		],
		"token": {
			"test_code": "NAPLAN",
			"timestamp": "{ts '2019-03-15 15:11:03'}"
		}
	}
	```

* **Error Response:**

	`codeonly` not supplied
	```javascript
	"__invalid": {
		"codeonly": "field is required"
	}
	```

* **Sample Parameters:**

	```javascript
	{"test_code":"NAPLAN"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://local.tassweb.net.au/tassweb/api/?appcode=API17&v=2&method=getTestCriteria&token=V8LLLCBhCwZRz%2B6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w%3D&company=10
	```

* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getTestCriteria" />
		<input type="hidden" name="appcode" value="API17" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="2" />
		<textarea name="token">V8LLLCBhCwZRz+6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w=</textarea>
	</form>
	```

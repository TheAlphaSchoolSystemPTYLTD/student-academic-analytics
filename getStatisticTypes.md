**getStatisticTypes**
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

	`codeonly [boolean]` - Return Code only. Must be 'true' or 'false'.

	**Optional:**

	none

	**Conditional:**

	none

* **Success Response:**

	```javascript
	{
		"StatisticTypes": [
			{
				"CODE": "AVG",
				"DESC": "Average"
			},
			{
				"CODE": "MAX",
				"DESC": "Maximum"
			},
			{
				"CODE": "Q3",
				"DESC": "Quartile 3"
			},
			{
				"CODE": "MED",
				"DESC": "Median"
			},
			{
				"CODE": "Q1",
				"DESC": "Quartile 1"
			},
			{
				"CODE": "MIN",
				"DESC": "Minimum"
			}
		],
		"token": {
			"timestamp": "{ts '2019-03-15 15:18:55'}",
			"codeonly": "false"
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

	`codeonly` not boolean
	```javascript
	"__invalid": {
		"codeonly": "Value is not a valid boolean."
	}
	```

* **Sample Parameters:**

	```javascript
	{"codeonly":"false"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://local.tassweb.net.au/tassweb/api/?appcode=API17&v=2&method=getStatisticTypes&token=V8LLLCBhCwZRz%2B6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w%3D&company=10
	```

* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStatisticTypes" />
		<input type="hidden" name="appcode" value="API17" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="2" />
		<textarea name="token">V8LLLCBhCwZRz+6fFEKIb6yZnBFKcAiBWzW9QH3Ja2w=</textarea>
	</form>
	```

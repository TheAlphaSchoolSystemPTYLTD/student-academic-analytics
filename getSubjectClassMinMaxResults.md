

**getSubjectClassMinMaxResults**
----
  Returns an array of structured minimum/maximum results comprising results year/period, set code, subject code, objective code, assessment code, validation type, minimum/maximum result and archived flag in JSON format.

* **Version History:**

  TASS v50.0 - Method Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `subcode [string]` -  Must be 'ALL' or a list of subject codes separated by the comma symbol.
      
   **Optional:**

   `resyear [number]` - Results Year.

   `resperiod [number]` - Results Period.

   `setcode [string]` - Set Code.

   `sublevel [number]` - Subject year level.

   `objcode [string]` - Objective code.

   `asscode [string]` - Assessment code.

   `valtype [string]` - Validation type. Valid values are I (individual) and R (range).

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      "DATA": [
          {
            "RES_PERIOD": 1,
            "SUB_CODE": "0024",
            "ARCHIVED_FLAG": "Y",
            "VAL_TYPE": "I",
            "ASS_CODE": "QT",
            "MAX_RESULT": 50,
            "RES_YEAR": 2015,
            "SET_CODE": "A",
            "OBJ_CODE": "OG",
            "MIN_RESULT": 0,
            "SUB_LEVEL": 8
          },
          {
            "RES_PERIOD": 1,
            "SUB_CODE": "0024",
            "ARCHIVED_FLAG": "Y",
            "VAL_TYPE": "I",
            "ASS_CODE": "G+",
            "MAX_RESULT": 150,
            "RES_YEAR": 2015,
            "SET_CODE": "A",
            "OBJ_CODE": "OG",
            "MIN_RESULT": 10,
            "SUB_LEVEL": 10
          }
      ],
      "__tassversion": "01.053.3.000",
      "token": {
          "resyear": 2015,
          "timestamp": "{ts '2021-01-22 11:23:52'}",
          "resperiod": 1,
          "subcode": "0024"
      }
    }
    ```
 
* **Error Response:**

    `subcode` not supplied
    ```javascript
    __invalid: {
      "subcode": "field is required"
    }
    ```

    `studcode` invalid
    ```javascript
    __invalid: {
      "subcode": "Subject code is invalid"
    }
    ```

* **Sample Parameters:**

  ```javascript
    {
        "subcode":"0024",
        "resyear":2015,
        "resperiod":1
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getSubjectClassMinMaxResults&token=70CMN1%2Bv8PSB8VwIWXFEHXzZLqxb0UjoAHSTD0JT6lix5LJrdc8LKVXKu7SOkIuO&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getSubjectClassMinMaxResults">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

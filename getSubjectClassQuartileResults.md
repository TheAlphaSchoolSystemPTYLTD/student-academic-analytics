

**getSubjectClassQuartileResults**
----
  Returns an array of structured result analytics data comprising subject code, subject year level, results year/period, class, statistic type, objective code, assessment code, progressive assessment type and archived flag in JSON format.

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

   `sublevel [number]` - Subject year level.

   `class [string]` - Class.
   
   `objcode [string]` - Objective code.

   `asscode [string]` - Assessment code.

   `patype [string]` - Progressive Assessment type. Valid values are QS and QT.

   `stattype [string]` - Statistics type. Valid values are:

    ```HTML
        AVG - Average result
        MAX - Maximum result
        MIN - Minimum result
        Q1_EE - First quartile (Excel exclusive method)
        Q1_EI - First quartile (Excel inclusive method)
        Q1_EX - First quartile (exclusive method)
        Q1_IN - First quartile (inclusive method)
        Q1_MT - First quartile (miniTab method)
        Q2 - Second quartile (median)
        Q3_EE - Third quartile (Excel exclusive method)
        Q3_EI - Third quartile (Excel inclusive method)
        Q3_EX - Third quartile (exclusive method)
        Q3_IN - Third quartile (inclusive method)
        Q3_MT - Third quartile (miniTab method)
    ```

   `resyear [number]` - Results Year.

   `resperiod [number]` - Results Period.

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
              "STAT_TYPE": "AVG",
              "ASS_CODE": "QT",
              "PA_TYPE": "QT",
              "RES_YEAR": 2015,
              "CLASS": "A",
              "OBJ_CODE": "OG",
              "RESULT": 40,
              "SUB_LEVEL": 8
            },
            {
              "RES_PERIOD": 1,
              "SUB_CODE": "0024",
              "ARCHIVED_FLAG": "Y",
              "STAT_TYPE": "MAX",
              "ASS_CODE": "QT",
              "PA_TYPE": "QT",
              "RES_YEAR": 2015,
              "CLASS": "A",
              "OBJ_CODE": "OG",
              "RESULT": 40,
              "SUB_LEVEL": 8
            }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "resyear": 2015,
            "timestamp": "{ts '2021-01-22 11:10:23'}",
            "resperiod": 1,
            "class": "A",
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
      "subcode": "Subject Code is invalid"
    }
    ```
    
* **Sample Parameters:**

  ```javascript
  {
    "subcode":"0024",
    "resyear":2015,
    "resperiod":1,
     "class":"A"
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getSubjectClassQuartileResults&token=jUmqNx1ZSmKPTfQm2ozMk9ybMZB9NoDY5qz%2FLx0CI4NEJv%2FI8Akp0bVzbe2ZKuTvLOc9O%2FKOuirpgv%2FZoqci9wnZ58A0HOSRQmwbACHs7uZwkN6Z1x1YDLGwkroyRYuOasbdGcKwtMFrOP8N%2Fddw6uDU0IdUdhTQ%2BVp6jvwPmFQ%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getSubjectClassQuartileResults">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

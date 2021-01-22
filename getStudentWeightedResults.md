

**getStudentWeightedResults**
----
  Returns an array of structured student weighted result data comprising student code, year group, results year/period, semester, objective code, assessment code, result, result mapping, weighted sum, weighted count, unweighted count and archived flag indicator in JSON format.

* **Version History:**

  TASS v50.0 - Method Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `studcode [string]` -  Must be 'ALL' or a list of student codes separated by the comma symbol.
   
   **Optional:**

   `yeargrp [number]` - Student year Group.

   `resyear [number]` - Results Year.

   `resperiod [number]` - Results Period.

   `objcode [string]` - Objective code.

   `asscode [string]` - Assessment code.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
      {
        "DATA": [
          {
            "RES_PERIOD": 1,
            "RESULT_MAPPING": 81.25,
            "ARCHIVED_FLAG": "Y",
            "ASS_CODE": "G+",
            "RES_YEAR": 2013,
            "WEIGHTED_COUNT": 8,
            "OBJ_CODE": "OG",
            "SEMESTER": 1,
            "YEAR_GRP": 8,
            "STUD_CODE": "0009601",
            "STUD_RESULT": "",
            "UNWEIGHTED_COUNT": 8,
            "WEIGHTED_SUM": 650
          },
          {
            "RES_PERIOD": 1,
            "RESULT_MAPPING": 64,
            "ARCHIVED_FLAG": "Y",
            "ASS_CODE": "N",
            "RES_YEAR": 2013,
            "WEIGHTED_COUNT": 8,
            "OBJ_CODE": "RAW",
            "SEMESTER": 1,
            "YEAR_GRP": 8,
            "STUD_CODE": "0009601",
            "STUD_RESULT": 64,
            "UNWEIGHTED_COUNT": 8,
            "WEIGHTED_SUM": 512
          }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "resyear": 2013,
            "timestamp": "{ts '2021-01-22 11:32:28'}",
            "resperiod": 1,
            "studcode": "0009601"
        }
      }
    ```
 
* **Error Response:**

    `studcode` not supplied
    ```javascript
    __invalid: {
      "studcode": "field is required"
    }
    ```

    `studcode` invalid
    ```javascript
    __invalid: {
      "studcode": "Student Code XXXX is invalid"
    }
    ```

* **Sample Parameters:**

  ```javascript
    {
      "studcode":"0009601",
      "resyear":2013,
      "resperiod":1
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentWeightedResults&token=iUMGAbEBjxmnI2F8sjXtlG8SPDMyDixiC43bbX09n0hzXV5PErax83l%2BOL9w9IoOwaS88B8NeLrJ%2F8a4iT1Kz4nJqAssyxzL%2FMCwhHIBiMRzhhGrDqnys1PEGDw9JRN%2F&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentWeightedResults">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

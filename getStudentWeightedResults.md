

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
      DATA: [
        {
          RES_PERIOD: 2,
          RESULT_MAPPING: 4,
          ARCHIVED_FLAG: "Y",
          ASS_CODE: "QO",
          RES_YEAR: 2011,
          WEIGHTED_COUNT: 1,
          OBJ_CODE: "ACH",
          SEMESTER: 2,
          YEAR_GRP: 12,
          STUD_CODE: "LANE001",
          STUD_RESULT: "B",
          UNWEIGHTED_COUNT: 1,
          WEIGHTED_SUM: 4
        }
      ],
      token: {
        resperiod: 2,
        studcode: "LANE001",
        timestamp: "{ts '2018-07-25 15:30:51'}",
        resyear: 2011,
        objcode: "ACH"
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
    "studcode":"LANE001",
    "objcode":"ACH",
    "resyear":2011,
    "resperiod":2
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

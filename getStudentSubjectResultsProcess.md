

**getStudentSubjectResultsProcess**
----
  Returns an array of structured student subject result process data comprising student code, year group, subject code, class, result year/period, semester, objective code, assessment code, result, result mapping, ranking and percent completion in JSON format.

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

   `yeargrp [number]` - Year Group.

   `subcode [string]` - Subject Code.

   `class [string]` - Class.
   
   `resyear [number]` - Results Year.

   `resperiod [number]` - Results Period.

   `semester [number]` - Semester..

   `objcode [string]` - Objective code.

   `asscode [string]` - Assessment code.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
      {
        "DATA": [
            {
                RES_PERIOD: "",
                RESULT_MAPPING: "",
                SUB_CODE: "0017",
                ASS_CODE: "",
                RES_YEAR: 2017,
                CLASS: "A",
                OBJ_CODE: "",
                RANKING: "",
                SUB_YEAR_GRP: "",
                PROCESS_TEXT: "No LMS flag",
                SEMESTER: 2,
                STUD_CODE: "JONE001",
                STUD_RESULT: "",
                PROCESS_CODE: 1,
                COMP_PERCENT: "",
                SUB_LEVEL: 11
            }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "timestamp": "{ts '2021-01-22 13:54:43'}",
            "studcode": "0010141"
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
    "resyear":2013
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentSubjectResultsProcess&token=iUMGAbEBjxmnI2F8sjXtlAWpGGm32kkL8CyHjge8VhCtPt3dzTimIgBuGl8F3JDLr%2BNGmi3hLrppaB0%2BEWdftU0VmXBHUPxL63HJ4uMOTo%2BkAYO0MlWBPchGYnWo7aow&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentSubjectResultsProcess">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

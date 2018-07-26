

**getStudentSubjectMapResults**
----
  Returns an array of structured student subject map result data comprising student code, year group, subject code, class, result year/period, period description, semester, subject description (standard/long/short), faculty ID, objective code, assessment code, progressive assessment type, result, result mapping, ranking and archived flag in JSON format.

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

   `facultyid [string]` - Faculty ID.

   `objcode [string]` - Objective code.

   `asscode [string]` - Assessment code.

   `patype [string]` - Progressive Assessment type. Valid values are QS and QT.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      DATA: [
        {
          RES_PERIOD: 1,
          RESULT_MAPPING: 4,
          SUB_CODE: "0031",
          SUB_SHORT: "Mat1",
          ARCHIVED_FLAG: "Y",
          ASS_CODE: "QO",
          RES_YEAR: 2010,
          SUB_LONG: "Mathematics I",
          CLASS: "A",
          OBJ_CODE: "ACH",
          RANKING: "",
          SUB_YEAR_GRP: "",
          PRD_DESC: "Semester 1, 2010",
          SEMESTER: 1,
          STUD_CODE: "AGNE003",
          STUD_RESULT: "B",
          PA_TYPE: "QS",
          FACULTY_ID: "",
          SUB_DESC: "Mathematics I",
          SUB_LEVEL: 2
        }
      ],
      token: {
        resperiod: 1,
        subcode: "0031",
        studcode: "AGNE003",
        timestamp: "{ts '2018-07-25 15:59:48'}",
        resyear: 2010,
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
    "studcode":"AGNE003",
    "subcode":"0031",
    "objcode":"ACH",
    "resyear":2010,
    "resperiod":1
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentSubjectMapResults&token=iUMGAbEBjxmnI2F8sjXtlOFhw0pWNXPbJUvOjwkLceR5H%2FrwtakkF5AoF85XqXItSO7Tgc2g6pLp6lNEG2Q2g7S8WSgCx%2BMN6fUjqyLMiOXERXEMCldl4E%2FxZr6I%2B5zl0jSgEGPMSeTTx%2Bo3XOFpvA%3D%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentSubjectMapResults">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

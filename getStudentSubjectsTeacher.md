

**getStudentSubjectsTeacher**
----
  Returns an array of structured student subject teacher data comprising student code, subject code, subject description (standard, long and short), year group, class, archived flag, result year/period, semester, teacher code/name and faculty ID in JSON format.

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

   `subcode [string]` - Subject code.

   `yeargrp [number]` - Year group.

   `class [string]` - Class.
   
   `resyear [number]` - Results year.

   `resperiod [number]` - Results period.

   `semester [number]` - Semester.

   `tchcode [string]` - Teacher code.

   `facultyid [string]` - Faculty ID.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
      {
        "DATA": [
            {
              "RES_PERIOD": 1,
              "SUB_CODE": "0009",
              "SUB_SHORT": "Japans",
              "ARCHIVED_FLAG": "Y",
              "RES_YEAR": 2013,
              "TCH_CODE": "RMC",
              "SUB_LONG": "Japanese",
              "CLASS": "D",
              "SUB_YEAR_GRP": "",
              "SEMESTER": 1,
              "TCH_NAME": "Mr R McClelland",
              "YEAR_GRP": 8,
              "STUD_CODE": "0009601",
              "FACULTY_ID": 4,
              "SUB_DESC": "Japanese"
            },
            {
              "RES_PERIOD": 1,
              "SUB_CODE": "0024",
              "SUB_SHORT": "Geog",
              "ARCHIVED_FLAG": "Y",
              "RES_YEAR": 2013,
              "TCH_CODE": "GB",
              "SUB_LONG": "Geography",
              "CLASS": "D",
              "SUB_YEAR_GRP": "",
              "SEMESTER": 1,
              "TCH_NAME": "Mrs G F Battersby",
              "YEAR_GRP": 8,
              "STUD_CODE": "0009601",
              "FACULTY_ID": 3,
              "SUB_DESC": "Geography"
            }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "resyear": 2013,
            "timestamp": "{ts '2021-01-22 10:54:21'}",
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
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentSubjectsTeacher&token=oNpiH9LDQx7oOOD1NEl0pXmplw3%2BWPQQKwsk%2F5xRfuBaA1xDEwDLKo0HMCmqyp%2FrGMe2URwCwDPGr6c11IY%2BFSRsaeF0ZQlcKn3ppjIS1FY%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentSubjectsTeacher">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

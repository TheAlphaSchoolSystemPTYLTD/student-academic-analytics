

**getStudentActivityAnalyticMapping**
----
  Returns an array of structured student activity analytic mapping data comprising student code, activity name, objective code, assessment code, class, analytic mapping, class rank and cohort rank indicator in JSON format.

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

   `objcode [string]` -  Objective code.
   
   `asscode [string]` - Assessment code.

   `class [string]` - Class.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
      {
        "DATA": [
            {
            "ACTIVITY_NAME": "Which volcanoes are erupting?",
            "COHORT_RANK": 14,
            "STUD_CODE": "0010131",
            "STUD_RESULT": 60,
            "ANALYTIC_MAPPING": 60,
            "ASS_CODE": "_N",
            "CLASS": "B",
            "OBJ_CODE": "_ATS",
            "CLASS_RANK": 6
            },
            {
            "ACTIVITY_NAME": "Which volcanoes are erupting?",
            "COHORT_RANK": 1,
            "STUD_CODE": "0010131",
            "STUD_RESULT": 20,
            "ANALYTIC_MAPPING": 20,
            "ASS_CODE": 20,
            "CLASS": "B",
            "OBJ_CODE": "APP",
            "CLASS_RANK": 1
            }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
            "timestamp": "{ts '2021-01-22 14:05:31'}",
            "studcode": "0010131"
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
  {"studcode":"0010131"}
  ```
  
* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentActivityAnalyticMapping&token=Mi2fSYBI04Jhq65zh91j94SqWaC5FXDVQ59O2lFo2Rk%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentActivityAnalyticMapping">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```



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
      DATA: [
        {
          ACTIVITY_NAME: "Looking for Alibrandi - Character Study",
          COHORT_RANK: 2,
          STUD_CODE: 20094,
          STUD_RESULT: 10,
          ANALYTIC_MAPPING: 10,
          ASS_CODE: 2,
          CLASS: "A",
          OBJ_CODE: "I",
          CLASS_RANK: 2
        }
      ],
      token: {
        studcode: 20094,
        timestamp: "{ts '2018-07-26 09:56:16'}"
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
    "studcode":"20094"
  }
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

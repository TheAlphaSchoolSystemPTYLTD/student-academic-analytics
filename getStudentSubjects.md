

**getStudentSubjects**
----
  Returns an array of structured student subjetcs data comprising student code, timetable ID, subject code, subject description, year group, class and lesson count in JSON format.

* **Version History:**

  TASS v50.0 - Method Added
  
  TASS v50.4 - Lesson Count Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `studcode [string]` -  Must be 'ALL' or a list of student codes separated by the comma symbol.
   
   **Optional:**

   `ttid [number]` - Timetable ID number.

   `yeargrp [number]` - Student year Group.

   `subcode [string]` - Subject code.

   `class [string]` - Class.

   **Conditional:**
 
   none
   
* **Success Response:**

  ```javascript
    {
      "DATA": [
        {
          "SUB_CODE": "0005",
          "YEAR_GRP": 11,
          "STUD_CODE": "0009709",
          "CLASS": "B",
          "TT_ID": 84,
          "SUB_DESC": "French",
          "LESSON_COUNT": 11
        },
        {
          "SUB_CODE": "0021",
          "YEAR_GRP": 11,
          "STUD_CODE": "0009709",
          "CLASS": "A",
          "TT_ID": 84,
          "SUB_DESC": "Modern History",
          "LESSON_COUNT": 12
        }
      ],
      "__tassversion": "01.053.3.000",
      "token": {
          "timestamp": "{ts '2021-01-22 10:15:05'}",
          "studcode": "0009709",
          "ttid": 84
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
      "studcode":"0009709",
      "ttid":"84"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getStudentSubjects&token=pswuOtGYaANzM3vrlmF06DgMqL4ESsl6%2Bp4F4tOev1DDyTuNPzcMYcGxCZW7XABT9k0dMijRU4%2By3eTqNvd6zg%3D%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentSubjects">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

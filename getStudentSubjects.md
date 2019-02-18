

**getStudentSubjects**
----
  Returns an array of structured student subjetcs data comprising student code, timetable ID, subject code, subject description, year group, class and lesson count in JSON format.

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

   `ttid [number]` - Timetable ID number.

   `yeargrp [number]` - Student year Group.

   `subcode [string]` - Subject code.

   `class [string]` - Class.

   **Conditional:**
 
   none
   
* **Success Response:**

  ```javascript
    {
      DATA: [
        {
            SUB_CODE: "0027",
            YEAR_GRP: 11,
            STUD_CODE: "BELL001",
            CLASS: "A",
            TT_ID: 55,
            SUB_DESC: "Economics"
            LESSON_COUNT: "45"
          }
      ],
      token: {
        subcode: "0027",
        studcode: "BELL001",
        timestamp: "{ts '2018-07-25 10:13:56'}",
        tt_id: 55
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
      "studcode":"BELL001",
      "subcode":"0027",
      "ttid":"55"
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

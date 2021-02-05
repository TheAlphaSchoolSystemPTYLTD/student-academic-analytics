

**getStudentAbsences**
----
  Returns an array of structured student absences data comprising student code, timetable ID, absent date, week, day, period, subject code, year group, class and acceptable reason indicator in JSON format.

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

   `absentdatefrom [date]` - Absent date from
   
   `absentdateto [date]` - Absent date to
   
   `ttid [number]` - Timetable ID number.

   `yeargrp [number]` - Year group.

   `subcode [string]` - Subject code.

   `acceptind [string]` - Acceptable reason indicator.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      "DATA": [
          {
            "SUB_CODE": "HOME9997",
            "YEAR_GRP": 11,
            "ACCEPT_IND": "N",
            "STUD_CODE": "0009709",
            "PRD_CODE": 1,
            "CLASS": "A",
            "WEEK": 22,
            "TT_ID": 87,
            "ABSENT_DATE": "2019-06-05 00:00:00.0",
            "DAY_CODE": 8
          },
          {
            "SUB_CODE": "0021",
            "YEAR_GRP": 11,
            "ACCEPT_IND": "N",
            "STUD_CODE": "0009709",
            "PRD_CODE": 3,
            "CLASS": "A",
            "WEEK": 22,
            "TT_ID": 87,
            "ABSENT_DATE": "2019-06-05 00:00:00.0",
            "DAY_CODE": 8
          }
      ],
      "__tassversion": "01.053.3.000",
      "token": {
            "absentdatefrom": "01/06/2019",
            "timestamp": "{ts '2021-01-22 08:50:09'}",
            "studcode": "0009709",
            "currentstatus": "current",
            "absentdateto": "30/06/2019"
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

    
* **Sample Parameters:**

  ```javascript
    { 
      "currentstatus":"current",
      "studcode":"0009709",
      "absentdatefrom":"01/06/2019",
      "absentdateto":"30/06/2019"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=GetStudentAbsences&token=L8tzq%2Baot1VES4Q6JprNQ%2FpmWIcmExWUg4FGgh3%2FbBXnUz6UnyOdEOnm%2FvMlE9f9jpDLinzxho4oKCH3ebdotg%3D%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="GetStudentAbsences">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

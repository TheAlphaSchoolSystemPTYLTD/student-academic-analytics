

**getClassLessons**
----
  Returns an array of structured Class Lessons data comprising timetable ID, timetable date, day, period, subject, year group and class in JSON format.

* **Version History:**

  TASS v50.4 - Method Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `ttid [string]` -  Must be 'ALL' or a list of timetable ID numbers separated by the comma symbol.
   
   **Optional:**

   `datefrom [date]` - Timetable date from
   
   `dateto [date]` - Timetable date to
   
   `subcode [string]` - Subject code.

   `yeargrp [number]` - Year group.

   `class [string]` - Class.

   `daycode [string]` - Day Code.

   `prdcode [string]` - Period code.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      DATA: [
        {
          SUB_CODE: "0001",
          YEAR_GRP: 12,
          TTDATE: "2018-08-01 00:00:00.0",
          PRD_CODE: 5,
          CLASS: "A",
          TT_ID: 84,
          DAY_CODE: 3
        }
      ],
      token: {
        daycode: "3",
        timestamp: "{ts '2018-07-24 17:16:03'}",
        ttid: "84"
      }
    }
    ```
 
* **Error Response:**

    `ttid` not supplied
    ```javascript
    __invalid: {
      "ttid": "Value must be a valid integer"
    }
    ```

    
* **Sample Parameters:**

  ```javascript
    { 
      "ttid":"84",
      "datefrom":"31/03/2018",
      "dateto":"31/03/2018"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=GetClassLessons&token=L8tzq%2Baot1VES4Q6JprNQ%2FpmWIcmExWUg4FGgh3%2FbBXnUz6UnyOdEOnm%2FvMlE9f9jpDLinzxho4oKCH3ebdotg%3D%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="GetClassLessons">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

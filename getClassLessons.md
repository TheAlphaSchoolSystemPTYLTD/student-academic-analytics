

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
        "DATA": [
            {
              "SUB_CODE": "LEARNING",
              "YEAR_GRP": 8,
              "TTDATE": "2020-09-03 00:00:00.0",
              "PRD_CODE": 4,
              "CLASS": "C",
              "TT_ID": 93,
              "DAY_CODE": 9
            },
            {
              "SUB_CODE": "ANCH20",
              "YEAR_GRP": 10,
              "TTDATE": "2020-09-04 00:00:00.0",
              "PRD_CODE": 3,
              "CLASS": "E",
              "TT_ID": 93,
              "DAY_CODE": 10
            }
        ],
        "__tassversion": "01.053.3.000",
        "token": {
              "datefrom": "03/09/2020",
              "timestamp": "{ts '2021-01-22 14:10:19'}",
              "ttid": 93,
              "dateto": "05/09/2020"
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
      "ttid":"93",
      "datefrom":"02/09/2020",
      "dateto":"05/09/2020"
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

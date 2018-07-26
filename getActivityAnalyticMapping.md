

**getActivityAnalyticMapping**
----
  Returns an array of structured activity analytic data comprising activity name, objective code, assessment code, statistics type, class, activity statistic result and analytic mapping in JSON format.

* **Version History:**

  TASS v50.0 - Method Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `objcode [string]` -  Must be 'ALL' or an objective code.
   
   **Optional:**

   `asscode [string]` - Assessment code.

   `stattype [string]` - Statistics type. Valid values are:

    ```HTML
        AVG - Average result
        MAX - Maximum result
        MIN - Minimum result
        COUNT - Results count
        STDEVP - Standard Deviation
        Q1_EE - First quartile (Excel exclusive method)
        Q1_EI - First quartile (Excel inclusive method)
        Q1_EX - First quartile (exclusive method)
        Q1_IN - First quartile (inclusive method)
        Q1_MT - First quartile (miniTab method)
        Q2 - Second quartile (median)
        Q3_EE - Third quartile (Excel exclusive method)
        Q3_EI - Third quartile (Excel inclusive method)
        Q3_EX - Third quartile (exclusive method)
        Q3_IN - Third quartile (inclusive method)
        Q3_MT - Third quartile (miniTab method)
    ```

   `class [string]` - Class.

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      DATA: [
        {
          ACTIVITY_NAME: "Looking for Alibrandi - Character Study",
          ACT_STATS_RESULT: 19.88,
          STAT_TYPE: "AVG",
          ANALYTIC_MAPPING: 19.88,
          ASS_CODE: 2,
          CLASS: "A",
          OBJ_CODE: "I"
        }
      ],
      token: {
        stattype: "AVG",
        timestamp: "{ts '2018-07-25 17:41:57'}",
        class: "A",
        obj_code: "ALL"
      }
    }
    ```
 
* **Error Response:**

    `objcode` not supplied
    ```javascript
    __invalid: {
      "objcode": "field is required"
    }
    ```

    
* **Sample Parameters:**

  ```javascript
  {
    "objcode":"ALL",
    "stattype":"AVG",
    "class":"A"
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
  https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getActivityAnalyticMapping&token=lQzYcdQ0qd4KA0lgZ2LKmEsQRYN6Z51fNpXIMqkipRuo%2FUzTJwQPIkM4AAMuHU6kyIeTpAvw7MzgMf%2BSHhi2MA%3D%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getActivityAnalyticMapping">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

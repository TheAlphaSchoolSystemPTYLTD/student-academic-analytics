

**getActivityMinMaxResults**
----
  Returns an array of structured activity minimum/maximum result data comprising activity name, objective code, assessment code, validation type and minimum/maximun results in JSON format.

* **Version History:**

  TASS v50.0 - Method Added

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `objcode [string]` - Must be 'ALL' or an objective code.
   
   **Optional:**

   `asscode [string]` - Assessment code.

   `valtype [string]` - Validation type. Valid values are I (individual) and R (range).

   **Conditional:**
 
   none
   
* **Success Response:**

    ```javascript
    {
      DATA: [
        {
          ACTIVITY_NAME: "Looking for Alibrandi - Character Study",
          VAL_TYPE: "I",
          ASS_CODE: "G+",
          MAX_RESULT: 15,
          OBJ_CODE: "CO",
          MIN_RESULT: 1
        }
      ],
      token: {
        timestamp: "{ts '2018-07-26 10:38:11'}",
        objcode: "CO"
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
  "objcode":"CO"
}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
https://local.tassweb.net.au/tassweb/api/?appcode=SAA&v=2&method=getActivityMinMaxResults&token=Q7rc5W4OACq9Q9GWbaWB6eDU0IdUdhTQ%2BVp6jvwPmFQ%3D&company=10
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getActivityMinMaxResults">
       <input type="hidden" name="appcode" value="SAA">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="2">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```

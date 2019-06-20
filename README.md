## RLN URL shortener API

More coming soon...

The **RLN API** is an HTTP-based interface designed to facilitate work with RLN service.  

We support **GET** and **POST** HTTP methods. We support three ways of passing parameters in RLN API requests:  

* _URL query string_
* _application/x-www-form-urlencoded_
* _application/json_


**API request limits:**  
15 any requests per second. Flood wait time after 15 requests/second is 300 seconds.

#### createLink

Use this method to shorten one or more links.

**Headers:**
| Key | Value |
| --- | --- |
| Content-Type | `application/json` |

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| token | `string` | Token generated during registration |
| links | `array` | Array of links for shortening |

Example **#1** `(200OK)`:
__Request:__
```bash
curl --location --request GET "https://api.rln.uz/createLink?token=TOKEN&links=LINKS" \
  --header "Content-Type: application/json"
```
 
__Response:__
```json
{
  "ok": true,
  "result": {
    "links": [
      {
        "id": "pHV9",
        "long": "https://www.toptal.com/laravel/restful-laravel-api-tutorial",
        "short": "https://rln.uz/pHV9"
      }
    ]
  }
}
```
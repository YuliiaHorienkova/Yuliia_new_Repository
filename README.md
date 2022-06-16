## Checklist

**/user**
* send positive requeest: all fields are filled with valid data
* only required fields are filled with valid data
* check each required fields (not send required field and check result)
* send empty request (empty body)
* send empty JSON
* send request with mistakes in body syntax
* check validation body fields according to api doc:
```json
 {
"id": integer($int64)
"username": "string"
"firstName": "string"
"lastName": "string"
"email": "string"
"password: "string"
"phone": "string"
"userStatus": integer($int32)
}
```
   * id:
       * type integer
       * check min/max(64) length
       * negative tests: enter cyrillic, latin. spec symbols 
       * enter only space
       * send empty field (empty data in fields)
    * username, firstName, lastName, email, password, phone: 
       * type string
       * check min/max length
       * negative tests: enter cyrillic, latin. spec symbols 
       * enter only space
       * send empty field (empty data in fields)
   * userStatus:
       * type integer
       * check min/max(32) length
       * negative tests: enter cyrillic, latin. spec symbols 
       * enter only space
       * send empty field (empty data in fields)
* check that response is correct (according to structure in api doc)
```json
{
"code": integer($int32)
"type": "string"
"message": "string"
}
```
* check Allow-Methods for requert (ER: if methot is not allowed - 405 Method Not Allowed)
* check with/without token
* check with http/https


**/user/{{username}}/ (find)**
* send valid parametr "username" in patch
* send not exist "username"  in patch (ER: 404 Not Found)
* send only space in "username" 
* check Allow-Methods for requert 
*  check with hhtp/https
* check respons body (according to structure in api doc):
```json
{
  "id": 0,
  "username": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "password": "string",
  "phone": "string",
  "userStatus": 0
}
```


**/user/{{username}}/ (update)**
* send valid parametr "username" in patch
* send not exist "username" in patch (ER: 404 Not Found)
* send only space in "username" 
* check Allow-Methods for requert 
* check with hhtp/https
* send positive requeest: all fields are filled with valid data
* only required fields are filled with valid data
* check each required fields (not send required field and check result)
* send empty request (empty body)
* send empty JSON
* send request with mistakes in body syntax
* check validation body fields according to api doc (use validation cases from /user endpoint):
```json
 {
"id": integer($int64)
"username": "string"
"firstName": "string"
"lastName": "string"
"email": "string"
"password: "string"
"phone": "string"
"userStatus": integer($int32)
}
```

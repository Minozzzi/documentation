<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;users&#x2F;class.user.js">class.user.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` User 
### Description:

Represents a user item

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| scope | `Object` |  C_USERS component instance (<this> scope) |
| obj | `Object` |  Object that matches the item schema. See properties below: |
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| _id | `String` | MongoDB Object is as string |
| name | `String` | User name (Human friendly name/real name) |
| email | `String` | User E-Mail Address |
| password | `String` | Password for logins |
| enabled | `Boolean` | Is user enabled/can login? |
| tokens | `Array` | Internal used to store JWTs (Active tokens/sessions) |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .addToken(cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| cb | `Function` |  Optional callback |


Adds a new JWT token for the user.
The token can be used for authentication.


*Returns*  `Promise`    If no callback is provided


<!-- LINKS -->
<!-- LINKS -->

####  .removeToken(token, cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| token | `String` |  Token to be removed |
| cb | `Function` |  Optional callback |


Removes a token from the user.
If the token is removed, it can not be longer used for authentication


*Returns*  `Promise`    If no callback is provided


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
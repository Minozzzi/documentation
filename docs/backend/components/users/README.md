<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;users&#x2F;index.js">index.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` C_USERS  `extends`  [COMPONENT](backend/system/component/class.component.js)  
### Description:

Manages users, handle accounts, hash/compares passwords.<br />
All stuff that a user component should do ;)

<!-- GENERAL -->

<!-- PARAMETER -->
<!-- PARAMETER -->

<!-- PROPERTIES -->
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
####  .login(email, pass, cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| email | `String` |  E-Mail address of the user |
| pass | `String` |  Password of the user (plain text) |
| cb | `Function` |  Optional callback function |


Takes username & password and compares these data with documents in the database.
If a user is found it compares the passwords with the hash and returns the user/valid boolean.


*Returns*   `undefined`    


<!-- LINKS -->
<!-- LINKS -->

####  .logout(email, cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| email | `String` |  User E-Mail address |
| cb | `Function` |  Callback function |


Remove all created tokens from user item.
Thus, the user is not able to perform any api calls more (until a login is made again)


*Returns*   `undefined`    


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
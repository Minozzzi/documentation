<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;vault&#x2F;class.secret.js">class.secret.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Secret 
### Description:

Represents a single secret that wraps encrypt/decrypt methods

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| obj | `Object` |  Object that matches the item schema. See properties below: |
| changed | `Function` |  Optional callback that is fired when the value changed (Interal use only!) |
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| _id | `String` | MongoDB Object id is as string |
| name | `String` | Human readable name |
| description | `String` | Description of the secret |
| key | `String` | Simple machine readable key. E.g.: ```PASSWORD``` or ```TOKEN``` |
| value | `String` | Value for the key field. E.g: ```Pa$$w0rd``` or ```eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c``` |
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
####  .schema();  `static`  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns joi schema for a single secret


*Returns*  `Object`    Joi.object 


<!-- LINKS -->
<!-- LINKS -->

####  .encrypt(text);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| text | `String` |  Input value to be encrypted |


Sets & encrypt the value for this secret


*Returns*  `String`    Ecnrypted string


<!-- LINKS -->
<!-- LINKS -->

####  .decrypt();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns & decrypt the setted value
 

*Returns*  `String`    Decrypted string


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
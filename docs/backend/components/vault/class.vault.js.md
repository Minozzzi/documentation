<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;vault&#x2F;class.vault.js">class.vault.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Vault 
### Description:

Contains a collection of secrets

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| obj | `Object` |  Object that matches the item schema. See properties below: |
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| _id | `String` | MongoDB Object id is as string |
| key | `String` |  |
| value | `String` |  |
| description | `String` |  |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [secret](/backend/components/vault/class.secret.js)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .schema();  `static`  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns a joi object that matches the schema


*Returns*  `Object`    Joi.object() 


<!-- LINKS -->
<!-- LINKS -->

####  .changes();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns a EventEmitter that can be used to watch for changes


*Returns*  `EventEmitter`    node.js EventEmitter instance



<!-- LINKS -->
##### See:
- [https://nodejs.org/dist/latest-v16.x/docs/api/events.html#class-eventemitter](https://nodejs.org/dist/latest-v16.x/docs/api/events.html#class-eventemitter)<br />
<!-- LINKS -->

####  .decrypt();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Decrypt all secrets at once, and returns a object with key/value


*Returns*  `Object`    Key = Secret key property, Value = decrypted value


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
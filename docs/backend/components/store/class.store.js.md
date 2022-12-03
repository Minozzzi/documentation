<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;store&#x2F;class.store.js">class.store.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Store 
### Description:

Contains a collection of values that are used as configuration object

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
| config | `Array` | Array of value instances, see "value" link below |
| item | `String` | Can be a Endpoint or Device _id, or what ever you want |
| namespace | `String` | Object namespace, `uuid -v4` |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [value](/backend/components/store/class.value.js)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .changes();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns a EventEmitter that can be used to watch for changes


*Returns*  `EventEmitter`    node.js EventEmitter instance



<!-- LINKS -->
##### See:
- [https://nodejs.org/dist/latest-v16.x/docs/api/events.html#class-eventemitter](https://nodejs.org/dist/latest-v16.x/docs/api/events.html#class-eventemitter)<br />
<!-- LINKS -->

####  .lean();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Create a new lean object with key/value based on schema


*Returns*  `Object`    Key/value object


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
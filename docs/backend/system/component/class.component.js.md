<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;system&#x2F;component&#x2F;class.component.js">class.component.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` COMPONENT  `extends`  [COMMON](backend/system/component/class.common.js)  
### Description:

Parent class for components which provides hookable, event emitting methods:
- add
- get
- update
- remove
- find

<!-- GENERAL -->

<!-- PARAMETER -->
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| items | `Array` | Store where instance of items are keept |
| collection | `Object` | MongoDB collection instance |
| schema | `Object` | Joi Object schema which is extend by a timestamp object: |
| schema.timestamps | `Object` | Timestamps |
| schema.timestamps.created | `Number` | Set to `Date.now()` when a item is created/added |
| schema.timestamps.updated | `Number` | Set to `Date.now()` when a item is updated |
<!-- PROPERTIES -->

<!-- EVENTS -->
#### Events:
| Name | Description |
| :---- | :----------- |
| add | When function has completed |
| get | When function has completed |
| remove | When function has completed |
| update | When function has completed |
| find | When function has completed |
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [https://mongodb.github.io/node-mongodb-native/3.7/api/Db.html#collection](https://mongodb.github.io/node-mongodb-native/3.7/api/Db.html#collection)<br />
- [https://joi.dev/api/?v=17.6.0#object](https://joi.dev/api/?v=17.6.0#object)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .add(data, options, options.returnDuplicate);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| data | `Object` |  Object that matches the component schema |
| options | `Object` |  Options object |
| options.returnDuplicate | `Boolean` |  When a duplicate is detected, return the already existing item instance? |


Adds a new item that matches the component schema


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .get(_id);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| _id | `String` |  Item ObjectId as string (<._id>) |


Returns a item that matches the <_id> property


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .remove(_id);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| _id | `String` |  Removes item with matching ObjectId as string (<._id>) |


Removes a item from the database and the `.items` array


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .update(_id, data);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| _id | `String` |  Item ObjectId as string (<._id>) |
| data | `Object` |  Partial object properties to update item |


Updates a existing item in the database  & `.items` array


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .find(query);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| query | `Object` |  key/value pair to search for in `.items` array |


Find matching item with key/values 


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .found(filter, cb, nothing);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| filter | `Object` |  Object that matches the component schema |
| cb | `Function` |  Callback function |
| nothing | `Function` |  Function that is called when not matching item in <items> array is found. Usefull to add then something, when its not found. |


A dynamic function which is called when either a item with matching filter is found in items array, 
or a new item with matching filter is added. It "search" as long as the wanted item is found.

Arrays as filter arguments are currently ignored and invalidate the query.
As result, the function would not returny any items. Remove the array.

NOTE: The filter values are case sensetive!


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
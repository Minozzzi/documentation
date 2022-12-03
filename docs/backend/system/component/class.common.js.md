<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;system&#x2F;component&#x2F;class.common.js">class.common.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` COMMON  `extends`  [BASE](backend/system/component/class.base.js)  
### Description:

Class description

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| logger | `Object` |  Logger instance |
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| logger | `Logger` | Logger instance |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [Logger](/backend/system/logger/)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  ._defineMethod(name, executor);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| name | `String` |  Name of the method that gets patche into the scope |
| executor | `Function` |  Wokrer function that does the actual implementation |


Defines a hookable/event emitting method on component scope


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  ._mapMethod(name, method, arr);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| name | `String` |  Name to set on the component object |
| method | `String` |  Method name on item |
| arr | `Array` |  Array too look for the target item object |


Maps a item method to the component scope
The mapped method is full hookable & emit evenits
Just like the build in component methods


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  ._ready(cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| cb | `Function` |  Callback to register |


Calls the provided callback as soon as the component is ready to be used.<br />
If this function is called while the component is ready, the callback is immediately called.


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
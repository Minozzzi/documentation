<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;endpoints&#x2F;class.command.js">class.command.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Command 
### Description:

Single command

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
| _id | `String` | MongoDB ObjectID as String |
| interface | `String` | Device Interface `_id` |
| name | `String` | Human friendly name |
| alias | `String` | Machine friendly name, e.g.: `POWER_ON` |
| identifier | `String` | Simple/custom identifiert for custom command handler |
| payload | `String` | The payload to send over the device interface |
| description | `String` | Command description, displayed on the frontend |
| params | `Array` | Possible parameter for the command |
| params[].key | `String` | Custom key |
| params[].type | `String` | Type of value: "string", "number" or "boolean" |
| params[].value | `String|Number|Boolean` | Value to set |
| params[].min | `Number` | Min value if param type is a number (`type=number`) |
| params[].max | `Number` | Max value if param type is a number (`type=number`) |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
#### Examples:
        
```json
{
    _id: "604a75e6eb5de037846df24c",
    name: "Power On",                           // Human redable
    alias: "POWER_ON",                          // Something you can easy reminder, e.g for register handling callbacks
    //identifier: "1",                            // Something your devices sets/needs 
    payload: "PWR01",                           // Payload that gets send raw to the device
    description: "",                            // should be self-explanatory]
    interface: "603fe5d18791152879a9babd"
}, {
    _id: "604a75e6eb5de037846df24d",
    name: "Power Off",                          // Human redable
    alias: "POWER_OFF",                         // Something you can easy reminder, e.g for register handling callbacks
    //identifier: "2",                            // Something your devices sets/needs 
    payload: "PWR00",                           // Payload that gets send raw to the device
    description: "",                            // should be self-explanatory  
    interface: "603fe5d18791152879a9babd"
}, {
    _id: "60546eaff7d8a2b752330b37",
    name: "Master Volume",       // Human redable
    alias: "MASTER_VOLUME",      // Something you can easy reminder, e.g for register handling callbacks
    //identifier: "4",        // Something your devices sets/needs 
    payload: "MVL${v}",       // Payload that gets send raw to the device
    description: "",
    params: [{
        key: "v",
        min: 0,
        max: 100,
        default: 35
    }],
    interface: "603fe5d18791152879a9babd"
}, {
    _id: "604a75e6eb5de037846df24e",
    name: "Mute (Toggle)",
    //alias: "",
    payload: "AMTTG",
    interface: "603fe5d18791152879a9babd"
}
  ```
<!-- EXAMPLES -->

<!-- LINKS -->
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .setHandler(handler);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| handler | `Function` |   |


Set the handler function that implements the command sepcific execution


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .getHandler();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Get the handler function that is currently set


*Returns*  `Function`    Setted handler function


<!-- LINKS -->
<!-- LINKS -->

####  .setTimeout(n);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| n | `Number` |  Timeout in msec |


Set the duration of a command timeout


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .getTimeout();  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Returns the setted timeout


*Returns*  `Number`    Timeout in msec


<!-- LINKS -->
<!-- LINKS -->

####  .trigger(params, cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| params | `Array` |  Parameter array |
| cb | `Function` |  Callback |


Calls the handler function and trigger the command execution


*Returns*   `undefined`   


<!-- LINKS -->
<!-- LINKS -->

####  .schema();  `static`  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |


Command schema


*Returns*  `Object`    Joi Object


<!-- LINKS -->
<!-- LINKS -->

####  .validate(obj);  `static`  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| obj | `Object` |  Input data to validate |


Validate schema object


*Returns*  `Object`    Joi validation response 


<!-- LINKS -->
##### See:
- [https://joi.dev/api/?v=17.6.0#anyvalidatevalue-options](https://joi.dev/api/?v=17.6.0#anyvalidatevalue-options)<br />
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
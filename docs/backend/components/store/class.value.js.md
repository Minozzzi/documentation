<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;store&#x2F;class.value.js">class.value.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Value 
### Description:

Represents a single key/value item.

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| obj | `Object` |  Object that matches the item schema. See properties below: |
| changed | `Function` |  Function that is called when the value has changed |
<!-- PARAMETER -->

<!-- PROPERTIES -->
#### Properties:
| Name | Type | Description |
| :---- | :-------- | :----------- |
| _id | `String` | MongoDB Object id is as string |
| key | `String` | Object key, like in a regular object |
| value | `String|Boolean|Numver` | Value of the property <key> |
| type | `String` | Type of <value> key: "string", "boolean" or "number" |
| description | `String` | Description for what the key is used |
| namespace | `String` | Object namespace, `uuid -v4` |
| item | `String` | MongoDB ObjectID for for what item the config applays (E.g: device or endpoint item) |
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
<!-- EXAMPLES -->

<!-- LINKS -->
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
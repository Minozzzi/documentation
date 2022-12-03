<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;store&#x2F;index.js">index.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` C_STORE  `extends`  [COMPONENT](backend/system/component/class.component.js)  
### Description:

This component can be used to store key/value configurations.<br />
Just like in redis, or a plain javascript object.<br />
If the value gets modified the changes are synct to other instance via MongoDB change streams (if enabled).
 
<!-- GENERAL -->

<!-- PARAMETER -->
<!-- PARAMETER -->

<!-- PROPERTIES -->
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
#### Examples:
        
```js
const C_STORE = require(".../components/store");

C_STORE.add({
  namespace: "4b564aab-ff4d-42b9-b15b-38885d4a0613",
  key: "poll_interval",
  value: 6000,
  description: "Interval in which miliseconds the API should be fetched"
});
```

<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [Namespace](/backend/components/store/class.namespace.js)<br />
- [https://www.mongodb.com/docs/manual/changeStreams/](https://www.mongodb.com/docs/manual/changeStreams/)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
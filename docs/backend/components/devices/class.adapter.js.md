<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;devices&#x2F;class.adapter.js">class.adapter.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` Adapter  `extends`  [Duplex](https://nodejs.org/dist/latest-v16.x/docs/api/stream.html#class-streamduplex)  
### Description:

Create a encode/decode data flow with adapters

<!-- GENERAL -->

<!-- PARAMETER -->
#### Parameter:
| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| stack | `Array` |  Array of called adapter functions |
| upstream | `Object` |  Upstream socket connecto to device (WebSocket) |
| options | `Object` |  Duplex stream options |
<!-- PARAMETER -->

<!-- PROPERTIES -->
<!-- PROPERTIES -->

<!-- EVENTS -->
<!-- EVENTS -->

<!-- EXAMPLES -->
#### Examples:
        
```js
const Adapter = require(".../components/devices/class.adapter.js");

let stack = ["raw"].map((name) => {
    try {

        return require(path.resolve(process.cwd(), "adapter", `${name}.js`))();

    } catch (err) {

        console.error(`Error in adapter "${name}" `, err);

    }
});

let adapter = new Adapter(stack, upstream, {
  encoding: "utf8"
});

adapter.write("foo");
```

<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [Quick-start](/backend/backend/quick-start?id=dataflow)<br />
- [InterfaceStream](/backend/backend/components/devices/class.interfaceStream.js)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
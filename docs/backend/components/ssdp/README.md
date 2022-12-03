<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;components&#x2F;ssdp&#x2F;index.js">index.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
## `class` C_SSDP  `extends`  [COMPONENT](backend/system/component/class.component.js)  
### Description:

Listen for ssdp message and sends discovery requests.<br />
This requires the "connector" software or bridging via other tools.<br />
A example for bridging can you see below with `socat` & `wscat`.

The emitted message events is the parsed data received on the underlaying udp socket.<br />
As third parameter the content of the `LOCATION` header field can be seen.<br />
This is only available if the connector is used.

<!-- GENERAL -->

<!-- PARAMETER -->
<!-- PARAMETER -->

<!-- PROPERTIES -->
<!-- PROPERTIES -->

<!-- EVENTS -->
#### Events:
| Name | Description |
| :---- | :----------- |
| message | Received message on udp socket; Arguments: [0]&#x3D;message type, [1]&#x3D;headers, [2]&#x3D;body (location header url content as json) |
<!-- EVENTS -->

<!-- EXAMPLES -->
#### Examples:
        
```sh
socat UDP4-RECVFROM:1900,ip-add-membership=239.255.255.250:0.0.0.0,fork - | wscat --connect=ws://127.0.0.1:8080/api/ssdp
```

        
```json
{
 host: '239.255.255.250:1900',
 man: '"ssdp:discover"',
 st: 'upnp:rootdevice',
 mx: '5'
}
```

<!-- EXAMPLES -->

<!-- LINKS -->
#### See:
- [router.api.ssdp.js](router.api.ssdp.js)<br />
- [https://en.wikipedia.org/wiki/Simple_Service_Discovery_Protocol](/backend/)<br />
- [https://github.com/nashwaan/xml-js](/backend/)<br />
<!-- LINKS -->

<!-- CLASS -->



<!-- METHODS -->
<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
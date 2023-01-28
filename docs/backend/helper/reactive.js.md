<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;helper&#x2F;reactive.js">reactive.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .reactive(obj, getter, setter, apply);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| obj | `Object|Array` |  Instace of `Object`. Anything that can in js be called "Object" |
| getter | `Function` |  Same as proxy `get()` |
| setter | `Function` |  Same as proxy `set()` |
| apply | `Function` |  Same as proxy `apply()` |


Returns the given object wrapped in a proxy object.<br />
Get/set & apply calls to the object are intercepted and additional callbacks called.


*Returns*  `Proxy`    Wrapped given <obj> Object.



<!-- LINKS -->
##### See:
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get)<br />
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/set)<br />
- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply)<br />
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;helper&#x2F;waterfall.js">waterfall.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .waterfall(arr, cb);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| arr | `Array` |  Array with functions |
| cb | `Function` |  Optional function that gets called when all previous functions has run |


Executes the functions in the array one after the previous has finished.
Just like in asyncs `waterfall` function.


*Returns*   `undefined`   

##### Examples
    
```js
_waterfall([(next) => {
    console.log("1");
    setTimeout(next, 1000);
}, (next) => {
    console.log("2");
    setTimeout(next, 1000);
}, (next) => {
    console.log("3");
    setTimeout(next, 1000);
}], () => {
    console.log("Waterfall done");
});
```


<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
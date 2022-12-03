<div class="mb-0">
    🔗 <a class="source-code" target="_blank"
        href="https://github.com/OpenHausIO/backend/blob/dev&#x2F;helper&#x2F;expose.js">expose.js</a>
</div>
<hr style="margin: 0 !important" />

<!-- CLASS -->

<!-- GENERAL -->
<!-- CLASS -->



<!-- METHODS -->
### Methods:
####  .expose(arr, method, key);  

| Parameter | Type       | Description    |
| :-------- | :--------- |:------------- |
| arr | `Array` |  Array where to look for exposing method |
| method | `String` |  Name of the method to look for |
| key | `String` |  Identifier key |


Expose a function/method on a array object


*Returns*   `undefined`   Wrapped method that accepts as first argument a _id


##### Examples
    
```js
class Item {

 constructor(obj) {
     Object.assign(this, obj);
 }

 fnc1() {
      console.log("fnc1 called", this);
      return "Yeah!";
  }

 fnc2() {
     console.log("fnc2 called");
     return new Promise((resolve) => {

         setTimeout(() => {
              resolve(Date.now())
         }, 1000);

     });
 }

 fnc3(cb) {
     console.log("fnc3 called");
     //setTimeout(cb, 1000);
     //return cb();
     //return null;
 }

}

const arr = new Array(3).fill(0).map((item, index) => {
  return new Item({
      _id: index,
     foo: {
         bar: "baz"
     }
  });
});


const fnc1 = _export(arr, "fnc1");
const fnc2 = _export(arr, "fnc2");
const fnc3 = _export(arr, "fnc3");

console.log(arr, fnc1(1, { data: true }));
console.log(fnc2(2))
console.log(fnc3(0, () => { return "foo" }));
console.log(fnc1, fnc2, fnc3)
```

<!-- LINKS -->
<!-- LINKS -->

<!-- METHODS -->



<!-- DESCRIPTION -->
<!-- DESCRIPTION -->
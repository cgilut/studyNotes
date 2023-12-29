# Study Notes

Writing down what I have learnt so far. Trying to explain concepts in human language rather than technical mumbo-jumbo.


## addEventListener

`addEventListener(x, y)` takes two parameters:
**x** is the event we are looking for, like clicking a mouse button, or loading the page
**y** is what we do when the **x** happens, like another function, which is called **callback function**!

## Callback function

> A callback function is a function that is used as a parameter for another function  
And that is it! Why does it deserve it's own special name?

It can be performed using anonymous arrow function:
```javascript
function myForEach(array, callback) {
  for (let i = 0; i < array.length; i++) {
    callback(array[i]); // This is when the callback function gets called, or executed
  }
}

// You would call it like this:
const myArry = [2, 3, 4, 2];
myForEach(myArry, (item) => {
  console.log(item + 2); 
})
```
the `item` is just `array[i]`
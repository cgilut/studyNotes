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

## :hover on links

For `scale()` to work on `:hover` links it needs to have a `display:inline-block.`

## hiding elements

`display:none` hides the element and completely removes it, like `position:absolute`.
`visibility:hidden` hides the element, but keeps the space reserved for it.

## responsive width

Set `width: 100%` and then `max-width: ??` to get a responsive width of a container.
When it can fit, it will be the `max-width: ??` wide,
and when the screen starts shrinking it will shrink with it.

## responsive height

A container inside a parent container that had `display:flex` and 
`flex-direction:column` properties didn't extend all the way down unless it had a 
`height:100%` property. However, with that property the contents also overflowed out
 of the container when viewing the website on devices with smaller hight. 
Removing `height:100%` and adding `flex: 1` solved the problem. 
It ensured the container took all the available space of its parent flex container.
# Study Notes

Writing down what I have learnt so far. Trying to explain concepts in human language rather than technical mumbo-jumbo.


## addEventListener

`addEventListener(x, y)` takes two parameters:
**x** is the event we are looking for, like clicking a mouse button, or loading the page
**y** is what we do when the **x** happens, like another function, which is called **callback function**!

## Callback function

A callback function is a function that is used as a parameter for another function  
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

## Hiding elements

`display:none` hides the element and completely removes it, like `position:absolute`.
`visibility:hidden` hides the element, but keeps the space reserved for it.

## Responsive width

Set `width: 100%` and then `max-width: ??` to get a responsive width of a container.<br>
When it can fit, it will be the `max-width: ??` wide,
and when the screen starts shrinking it will shrink with it.

## Stretch body height across the screen

In order to have body cover the whole height of the screen instead of using `100vh` we will use 100%

```css
html {
    height: 100%;
}

body {
    min-height: 100%;
    box-sizing: border-box;
}
```

without the `box-sizing` the screen will have a scroll to the bottom

## Responsive height

A container inside a parent container that had `display:flex` and 
`flex-direction:column` properties didn't extend all the way down unless it had a 
`height:100%` property. <br>
However, with that property the contents also overflowed out of the container when viewing the website on devices with smaller hight.<br>
Removing `height:100%` and adding `flex: 1` solved the problem. 
It ensured the container took all the available space of its parent flex container.

## git log --pretty

`git log` command has a `--pretty` option. which makes `git log` readable.
Here is an example: 

`git log --max-count=15 --pretty="format:%C(dim green) %<(9,trunc)%ar %C(bold magenta)%h %C(bold green)%<(12,trunc)%an %C(bold yellow)%<(113,trunc)%s"`

   - %C(dim green): This sets the color of the following text to dim green.

   - %<(9,trunc): This is a field width specifier. It specifies that the next placeholder should have a width of 9 characters, and if the content is longer, it should be truncated. This is often used for aligning columns.

   - %ar: This shows the author date, relative. %ar stands for "author date, relative".

   - %C(bold magenta): This sets the color of the following text to bold magenta.

   - %h: This shows the abbreviated commit hash.

   - %C(bold green): This sets the color of the following text to bold green.

   - %<(12,trunc): Similar to the first field width specifier, but here it specifies a width of 12 characters.

   - %an: This shows the author name.

   - %C(bold yellow): This sets the color of the following text to bold yellow.

   - %<(113,trunc): Another field width specifier, specifying a width of 113 characters.

   - %s: This shows the commit subject.

## Event objects

When an event happens (mouse clicks, button presses, etc) the event is saved into an object, called the event object. All the info about this event is then
passed into a callback function that you specify in the `addEventListener`.

The information about the even goes as the 2nd parameter FUNCTION:

`addEventListener( EVENT , FUNCTION )`

That information can later be used when executing the function. In the `addEventlistener` the function should be without the parenthesis `()`, because we are **executing it**. 
The actual function itself should have parenthesis with some kind of variable. It can be anything, but the standard practice is to call it `e`, or `event`.
Something like this:

```javascript 
function functionName(e) {
  if (e.target.checked) {
  // some code
  } else {
  // some code
  }
}

checkBox.addEventListener('change', functionName)
```

We have a checkbox, and we are listening to an event. In this case its the box getting checked via `change`. The information about the event is passed to the function `functionName`. The `e` here is a placeholder for that information. Inside the function we look at the `target` parameter, and if its `checked` some code is executed. For example it could be a switch for dark mode, or a different language.  
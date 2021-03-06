# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Created by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) |  [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Website](https://rafase282.github.io/) | [My Original Wiki](http://rafase282.github.io/My-FreeCodeCamp-Code/)

# Details
- Difficulty: 2/5

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument).

Remember to use [RSAP](http://www.freecodecamp.com/field-guide/how-do-i-get-help-when-I-get-stuck) if you get stuck. Try to pair program. Write your own code.

# Useful Links
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)

# Problem Script:

```js
function find(arr, func) {
  var num = 0;
  return num;
}

find([1, 2, 3, 4], function(num){ return num % 2 === 0; });
```

## Explanation:
The problem is quite simple to understand. You will check for each element in the array that is passed in the first argument, if the element plugged in to the function passed as the second argument returns true the first time. We do not care about the second or third one that is true, only the very first one if any. If there are none, then return undefined. This last bit is not explained but it is part of the tests used.

## Hint: 1
You can use the function directly from the parameter, no need to rename it or anything.

## Hint: 2
You need to pass an element and record it if the function returns true, for this you just have to pass the element as the parameter for the function.

## Hint: 3
If no element satisfy the function then you must return **undefined**

## My code:

```js
function find(arr, func) {
  // Make num undefined by default
  var num;

  // Loop thorugh the array and use the function to check
  for (var a = 0; a < arr.length; a++) {
    if (func(arr[a])) {
      // Store the first case and break the loop
      num = arr[a];
      return num;
    }
  }

  // otherwise return undefined
  return num;
}

find([1, 2, 3, 4], function(num) {
  return num % 2 === 0;
});
```

```js
// Using Arr.filter()

function find(arr, func) {
  // filter the provide array by the function provided and return only the first element.
  return arr.filter(func)[0];
}

find([1, 2, 3, 4], function(num){ return num % 2 === 0; });
```

## My Code Explanation:
- To make the code easier, create an undefined variable that will be returned.
- Loop through the array to check for each element if it satisfy the function. This is done by passing the arr[index of the loop] as the parameter for the function from the second argument.
- If true, then store the array element, and return it. This will stop the loop. No else needed.
- If the loop was not broken and it has ended, then return **num** which by default is undefined. This means that none of the elements from the array satisfied the function.

## [Go Home](https://github.com/Rafase282/My-FreeCodeCamp-Code/wiki)

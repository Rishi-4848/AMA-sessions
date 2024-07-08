# 6th-july-2024

### 1. What is the difference between (==) and (===) operator ?
     
     * == (Equality Operator): Compares values with type conversion.

     * Example: 2 == '2' is true.


     * === (Strict Equality Operator): Compares values without 
       type conversion; both value and type must match.
     * Example: 2 === '2' is false.

### 2. Console.log(typeof []) is equals to 'object' why? 
    
     * console.log(typeof []) equals 'object' because in  JavaScript, arrays are a specialized type of object. 
     * Arrays inherit from Object.prototype, and their internal implementation classifies them as objects, even though they have additional properties and methods    
       that allow them to function as arrays.

### 3. Whats are the disadvantages of using closure ?
     
     * Memory Consumption: Closures can lead to higher memory usage because they maintain references to the variables they capture. This can prevent garbage 
                           collection, leading to memory leaks if not managed properly.

     * Debugging Difficulty: Debugging code that uses closures can be more challenging because the state of the variables captured by the closure may not be     
                             immediately clear. This can make it harder to track down bugs and understand the flow of the program.
    
     * Performance Issues: If closures are used excessively, especially in performance-critical code, they can lead to performance issues due to the overhead of 
                           maintaining references to the captured variables.

### 4. Why using global variables are bad in js ?
     
     * Namespace Pollution: Global variables are accessible from anywhere in the code, which increases the risk of name collisions where different parts of the code 
                            might inadvertently overwrite each other’s values.

     * Reduced Maintainability: When variables are globally accessible, it becomes harder to track where they are being modified or used, making the code more     
                                 difficult to understand, debug, and maintain

     * Increased Risk of Bugs:Global variables can be changed by any part of the code, which can introduce bugs that are hard to trace since the state of the global 
                              variable can be altered unexpectedly.*

### 5. How to extract certain properties from an array of objects to create a new array ?
    
    * we can extract certain properties from an array of objects and create a new array using the map() method.
Example : 

```
const users = [
  { id: 1, name: 'Alice', age: 28 },
  { id: 2, name: 'Bob', age: 25 },
  { id: 3, name: 'Charlie', age: 30 }
];

const userNames = users.map(user => ({
  id: user.id,
  name: user.name
}));

console.log(userNames);
// Output: [{ id: 1, name: 'Alice' }, { id: 2, name: 'Bob' }, { id: 3, name: 'Charlie' }]


```

### 6. Difference between charAt() and at() method in js ?
     
     * Negative Indices: charAt() does not support negative indices. at() supports negative indices to count from the end of the string.

     * Empty String Return: charAt() returns an empty string if the index is out of bounds.at() also returns undefined if the index is out of bounds.


### 7. How to reset initial or 1st commit in git, if its possible ?
    
     * git reset --hard HEAD~1

### 8. console.log(typeof []) returns 'object', then why can not we use (.) operator in array to accesss its values just like objects,where we use (.) operator in  objects for accessing key and values

     * Array Indices: Array elements are accessed by numerical indices, not by named keys.Bracket notation allows you to use a variable to access array elements.

     * Array Methods and Properties: Arrays have special methods and properties that you can access using the dot operator.

     * Dot Notation and Strings: Dot notation requires valid JavaScript identifiers (keys must be strings that are valid variable names).Array indices are numbers, 
                                 which are not valid identifiers for dot notation.

### 9. Why 'forEach' loop skips 'not defined' whereas 'for' loop gives 'undefined'  in a array?
     
    * forEach Method : When using the forEach method on an array, it iterates over the elements that have been explicitly defined (i.e., those with assigned values). 
                       It skips over elements that have not been initialized or explicitly set, treating them as if they do not exist:

    * for Loop : A traditional for loop, on the other hand, iterates over all elements in the array, including those that are uninitialized (undefined). This means 
                 you will see undefined for any element that has not been explicitly set or initialized:

### 10. How can we mimic the action Array.splice and 'Array.slice' on objects  ?
     
    * Mimicking Array.splice() on Objects : The splice() method in arrays allows you to modify the contents of an array by removing existing elements and/or adding 
                                            new elements. To achieve similar functionality with objects (e.g., adding or removing properties), you can use object manipulation methods like Object.assign(), property deletion (delete), and the spread operator (...).

Example :

```
// Mimicking Array.splice() on an object

let obj = { a: 1, b: 2, c: 3 };

// Adding new properties using spread operator
obj = { ...obj, d: 4, e: 5 };

// Removing properties using delete
delete obj.b;

console.log(obj); // { a: 1, c: 3, d: 4, e: 5 }

```


     * Mimicking Array.slice() on Objects : The slice() method in arrays returns a shallow copy of a portion of an array into a new array object selected from begin 
                                            to end (end not included). For objects, you can achieve a similar result by creating a new object and copying the desired properties.

Example :

```
// Mimicking Array.slice() on an object

let obj = { a: 1, b: 2, c: 3, d: 4 };

// Creating a shallow copy of a portion of the object
let newObj = {
  b: obj.b,
  c: obj.c
};

console.log(newObj); // { b: 2, c: 3 }

```


### 11. What is "Callback Hell" problem and how to avoid it ?

      *  Use Promises:Promises provide a cleaner way to handle asynchronous operations and avoid deeply nested callbacks. They allow chaining of operations and better 
                      error handling using then() and catch() methods.

      *  Use Async/Await: Async functions and await keywords provide syntactic sugar over promises, making asynchronous code look synchronous. This improves 
                          readability and reduces nesting.

      *  Modularization and Named Functions: Break down complex operations into smaller, modular functions. Use named functions instead of anonymous callbacks to    
                                             improve readability and reusability.


### 12. why "hello" is being printed , when we are exporting only aaray..?
 
 ```
 //file1.js
let ar = [1,2,3];
console.log("Hello");
module.exports.ar = ar;

//file2.js
const {ar} = require('file1.js');
let print = ar;
console.log(print);

Output: "Hello"  [1,2,3]
```

    * The "Hello" is logged because console.log("Hello"); is executed at the time file1.js is loaded, regardless of whether ar is accessed or not in file2.js. This behavior is normal for how Node.js modules work: code in the module file runs as soon as it is loaded or required by another module.


    



















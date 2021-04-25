# Javascript Technologies

## Event Loop

A primary concept used in Javascript. This is to avoid using threads because each thread has its own heap and stack. A thread blocks a lot of things.

JS is a single threaded non blocking language.

JS Architecture of V8 has the following 2 things only:
  1. heap - memory allocation where actual data is saved
  2. stack - maintains the execution queue (method stack sort of things)

Extra are event loop and WEB API (provided by the OS) and they are not provided by JS.

Amazing explanation by Philip Roberts
https://www.youtube.com/watch?v=8aGhZQkoFbQ

Please note that JS runs on many threads but the code is executed only on one thread. Other threads capture triggers, clicks, etc.

e.g. setTimeout does not sit on the stack but moves to the callback queue/event loop. When the time comes, it is pushed back to the stack through task queue. Event loop just checks if there is anything in the task queue. If there is and the stack is empty, it will push the task to stack.

Browser has a JS engine but also provides other things like webapis, etc.

## JS Promise

At first glance looks like a callback. Indeed the promise uses the callbacks behind the scene but they were added to provide better readability and intuition. It comes handy when callbacks are called within other callbacks (nested)

## ES6 (Also called ECMAScript6, ES 2015)

> Source: https://www.w3schools.com/js/js_es6.asp

## New Stuff!!

## let

block scoped

## const

declare a constant

## Arrow Function

const x = (x, y) => x * y;

or

const x = (x, y) => {return x * y};  /*helpful in multiline function*/

## Classes

roughly same as java

## Array.find(myFunc) and Array.findIndex(myFunc)

Returns the element or index of the first element which matches the condition defined in myFunc.

## Added more to existing utilities

Number.EPSILON
Number.MIN_SAFE_INTEGER
Number.MAX_SAFE_INTEGER
Number.isInteger(10.5);      // returns false
Number.isSafeInteger(10);    // returns true
isFinite(10/0);       // returns false
isFinite(10/1);       // returns true
isNaN("Hello");       // returns true

## Exponential

var z = x ** 2;          // if x is 5 then result is 25

## JSON

JSON Syntax Rules
Data is in name/value pairs
Data is separated by commas
Curly braces hold objects
Square brackets hold arrays

e.g.

```javascript
{
  "employees":[
                {
                  "firstName":"John", 
                  "lastName":"Doe"
                },
                {
                  "firstName":"Anna", 
                  "lastName":"Smith"
                },
                {
                  "firstName":"Peter", 
                  "lastName":"Jones"
                }
              ]
}
```

## Prototype

Instead of using classes, as Java does, JS simply allows to create objects without classes. The inheritence is through a reference to parent object. So each object will have a prototype member which will point to its parent. It is possible for child object to update parent prototype's properties which will then apply to all its children.

Though you cannot add new properties to an object without adding that property to its constructor, you can add it to its prototype. For example - assuming that nationality is not its property currently:

Not Allowed - Person.nationality = "English";
Allowed - Person.prototype.nationality = "English";

## Fetch API

better way developed by Google as an alternative to XMLHTTPRequest.

## Promises

Better way to manage callbacks.

## nodejs

oclif - library to build cli apps using nodejs

webpack - bundles all dependencies into a single pack

---
layout: default
---
# New things added to ES6 (Also called ECMAScript6, ES 2015)

Source: https://www.w3schools.com/js/js_es6.asp

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

{
"employees":[
              {"firstName":"John", "lastName":"Doe"},
              {"firstName":"Anna", "lastName":"Smith"},
              {"firstName":"Peter", "lastName":"Jones"}
            ]
}

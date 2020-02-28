---
layout: default
---
# Other Concepts

## Anonymous Functions (function literal)

It is a unnamed function


## Closure

An instance of a function which has references to its environment (for example var). More simply, they are funciton with presevered data. See below - getFName has a reference to \_firstName. getFName will always refer to the latest value of \_firstName no matter where the value is updated from.

function Person(fName) {
  var \_firstName = fName;

  this.getFName = function(){
    return \_firstName;
  };
}


## First Class Functions

A programming language is said to have them if they are treated as first class citizens, which means that functions can be return value of functions or parameters to functions. A function name does not have any special meaning.

## Functional Language

## Lambda Calculus

## Referentially transparent - Given the same input you get the same output.

## No side-effects - The function does not modify anything outside itself.

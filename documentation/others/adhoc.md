---
layout: default
---
# Adhoc Tricks

## Run JD decompiler on mac

CD to the directory with the JD jar and then run the following command:

> java --add-opens java.base/jdk.internal.loader=ALL-UNNAMED --add-opens jdk.zipfs/jdk.nio.zipfs=ALL-UNNAMED -jar jd-gui-1.4.0.jar


## Enable unidentified apps to run, enable Anywhere option in MAC:

> sudo spctl --master-disable
> sudo spctl --master-enable

## css more tricks -

display:grid is very useful
will-change - giving browser a headsup.

## Firebase

Google cloud app which helps deverloper with database, analytics, etc.

## Serverless computing

No dedicated server. Load managed by provider and customer is charged per usage.

## Ansible
Automation tool. Agentless > Talk through ssh

## Ansible Tower

Comes with Ansible and a web app which helps manage roles, playbooks, etc.

## Long polling vs WebSocket

HTML5 has the option to keep a WebSocket open for push notifications. Older technologies used long polling technique which was more like a workaround. This would not return the response but would keep it open for a long time before closing it and firing another one.

## Jenkins

Comes with many preinstalled plugins but one useful one is "Build Pipeline" which lets you connect the projects in a sequence and lets you see it in that way.

## Difference between CI and CD

CI = Continously integration/checkin in your code to the master + Running your unit tests/automated tests. Code should always be in prod ready state.

C Delivery = CI + Deployment to prod which might be manual

C Deployment = deployment to prod is automated

## Functional programming

Functions are first class citizen - functions are objects

higher order functions - functions can take and return other functions as parameters. Higher order functions help e.g. the below takes each element of arr1 and multiplies with 2 and makes a new arr2. The below is using array.prototype.map

const arr2 = arr1.map(item => item * 2);

The below is using array.prototype.filter. This gets all persons whose age is more than 18.

const fullAge = persons.filter(person => person.age >= 18);

Array.prototype.reduce. Takes a reducer function which takes accumulator, currentvalue, etc.

const sum = arr.reduce(function(accumulator, currentValue) {
  return accumulator + currentValue;
});



## JS Closure

Function bnundled with its lexical scope. The function can use the variable outside it. This is calculated (including the variable) during runtime when the function is called.

## Javascript Curry

Taking multiple parameters one at a time

## JS Partial app

A function with some parameters fixed in its closure scope.

## JS ES6 Spread Operator - Spread, combine and expand

const numbers = [5, 7, 3];
// Yuck!
Math.max(numbers[0], numbers[1], numbers[2]);
// And this won't work
Math.max(numbers); // NaN

// ES^ way - Much Better!
Math.max(...numbers); // 7

const one = [1,2,3];
const two = [4,5,6];
const merged = [...one, ...two];
// [ 1, 2, 3, 4, 5, 6 ]

## variadic functions

Which can take variable number of arguments, even infinity. e.g. Math.max

## JS What is generator function function*

## What is ES6?

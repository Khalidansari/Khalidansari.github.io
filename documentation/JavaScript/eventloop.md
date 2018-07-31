---
layout: default
---
# Event Loop

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

# JS Promise

At first glance looks like a callback. Indeed the promise uses the callbacks behind the scene but they were added to provide better readability and intuition. It comes handy when callbacks are called within other callbacks (nested)

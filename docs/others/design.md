---
layout: default
---
# Design

## Keep classes small?

The length of the class is not the problem but the abstraction. Each class should abstract out as small an idea as possible.

## Classes should be deep

Visualization
The top layer is the interface which we want to keep as small as possible (less dependency) while we want the area of the class (which corresponds to functionality) to be more. So shallow classes are bad while deeper are good.

-----------------
|               |
-----------------
|               |
|               |
|               |
-----------------

## Throw as less exceptions as possible

Because then the calling class has the burden to deal with it. Ideally avoid as much as possible throwing the error by writing code which does not fail. E.g. a method which deletes a variable. You can either throw exception if the variable is not there or simply don't do anything as it is already deleted.

Errors are easier to pass from one layer to further away to another layer

Sometimes it might be a good idea to return an error code. This generally helps if the immediate layer wants to process it rather than a layer further away.

# Create boiler plate for the test

## Protocol

 * [Create a new test with no constraints](extendTestWithoutConstraints.md)
  
## Discussion

The first part in creating the new test is to get the basic
boilerplate done.  Typically, this means inventing a name
for the new test module, dealing with whatever imports you
may need for the test framework, and so on.

The heuristic hints for naming the test module aren't great;
the test module is a _module_, meaning that we should be
thinking about a suite of tests that explore some cohesive
idea -- at some level, we should be able to shoot the
entire module if it turns out that we abandon this development,
or if we later need to deprecate the system under test.

You should not be touching the production side of the source
tree at all; all of this activity occurs in your build system
and in the test side of the source tree.
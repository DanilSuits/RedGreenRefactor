# Extend Test Without Constraints

## Protocol

 * [The test doesn't compile](theTestExtensionDoesn'tCompile.md)
 * [I hate this API](iHateThisApi.md)
 * [The test is ready]()
 
## Overview

Entering this state, the bar should be green; the test compiles, because the
API defined in your production code is sufficient to support the messages
being sent to it by the test code.

So you continue to explore the design of your API by writing more test
code until you either finish the behavior of the test, or until a compile
error reveals a missing part of the API.

This discover phase includes trying out _names_ for the concepts in the
production code.  As much as possible, you want names that make sense
to the caller without revealing specific details of an implementation.

I find that in the API there are two competing constraints; the ease
of expressing the constraints on behavior in your tests, and the anticipated
interaction points.  Pure functions, or queries on well understood objects,
these are easy to test.  But most programs need side effects to do anything
interesting, and there are likely to be constraints imposed by the
integration boundary -- especially if you are working at the boundary
of your runtime framework (JVM, container, etc).

In most cases, your eventual constraint is going to be an check of
a value returned by the model matching some constraint defined in the
test.  In this phase of the protocol, you are capturing that value,
because the type of the return value is part of the definition of
your API, and you want to discover that it feels right to interact
with the API in that way when composing client code.

But you don't actually introduce the check itself yet.
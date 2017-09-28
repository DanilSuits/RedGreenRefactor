# The new check passed

## Protocol

 * The test is now properly calibrated

## Overview

It can happen that the auto generated behavior in your production code
can satisfy the constraint defined by your new test.  It's fine to have
constraints that are so easily satisfied, because you still want to have
the constraint present when you are refactoring.

The simple move to make is to go to the location in the _production_ code
where the final result is returned, and hard code into that place a new
value that won't satisfy the check you have already implemented.

After all, the value selected by the code completion tool was effectively
arbitrary; so we hack in a new value to re-calibrate.


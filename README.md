# JavaScript Loose Comparison Bug

This repository demonstrates a common JavaScript bug related to loose comparison using the == operator.

## The Bug
The `foo` function uses loose comparison (==) to check if two values are equal. This can lead to unexpected results when comparing values of different types.

For example:
```javascript
foo(0, false); // Returns true (unexpected)
foo(1, true);  // Returns true (unexpected)
foo('1', 1); // Returns true (unexpected)
```
Loose comparison performs type coercion, which can lead to unexpected truthy/falsy comparisons.

## The Solution
The solution is to use strict comparison (===) instead of loose comparison (==). Strict comparison checks for both value and type equality.

```javascript
function foo(a, b) { return a === b; }
```
This ensures that the function returns `true` only when both the value and type of `a` and `b` are identical.
# What I Learned in Week 6

## Week 6 was more array work, including new ways of iterating through arrays, and function expressions.

### ARRAY ITERATION

#### For of loops ####
Another way of iterating through an array is the 'for of' loop.  Instead of specifying commands and expressions in the if arguments, the `of` expression automatically iterates through a string and array elements, creating a variable for each iteration.  Syntax:
```
let array = [1, 2, 3, 4, 5];

for(element of array) {
	element;
}
```
Same as:
```
let array = [1, 2, 3, 4, 5];

for(let i = 0; i < array.length; i++) {
	array[i];
}
```

#### `.reduce()` ####
Another way to iterate through an array is the `.reduce` array method.  It is provided with a function to call for each array element.  The function is provided with several arguments that allow it to know its position in the array that's being processed.  The method is intended to reduce the contents of an array into one value, so this 'running total' of sorts starts as `initialValue`.

```
.reduce(function(total, currentValue, currentIndex, arr), initialValue);
```
*Parameters passed to function:*
- `total`: (Required) For the first element `initialValue` is passed, and for subsequent elements the last return value of `function` is passed.
- `currentValue`: (Required) The current element of the array that's being iterated through.
- `currentIndex`: (Optional) The current array index.
- `arr`: (Optional) The actual array that is being iterated through.

An example is shown below for summing up the values in an array:
```
let array = [1, 2, 3, 4, 5];

arraySum = array.reduce(makeSum, 0);

function makeSum(total, currentValue) {
	return total + currentValue;
}
```
Same as:
```
let array = [1, 2, 3, 4, 5];

arraySum = reduce(array, makeSum, 0);

function reduce(array, func, total) {
	for(item of array) {
		total = func(total, item);
	}
}

function makeSum(total, currentValue) {
	return total + currentValue;
}
```

### ARRAY MAPPING ###
Array mapping is the process of taking an array as input, processing its elements in whichever way, and outputting an array with its modified elements.  The mapping example below multiplies each array element by two.
```
function double(array) {
	let out = [];
	for(item of array) {
		out.push(item * 2);)
	}
	return out;
}
```

### ARRAY FILTERING ###
Array filtering is similar to array mapping, except that the processing checks each element and decides if the output array should include the element or not.  The example below filters an array and gets rid of odd ones.
```
function filterOdd(array) {
	let out = [];
	for(item of array) {
		if(item % 2 === 0) {
			out.push(item);
		}
	}
	return out;
}
```

### FUNCTION ASSIGNMENTS ###
Functions can be assigned to variables.  They can also be assigned to constants, preventing functions' identifiers from being overwritten.
```
const add = function(a, b) {
	return a + b;
}
```

### FUNCTION EXPRESSIONS ###
Function arrow notation can be used to create a function expression.  The difference is that the function doesn't have to `return` a value.  Instead, the value of the last expression in the function is returned automatically.
```
const add = (a, b) => a + b;
```

# Main module for make array

## Imports

	curry = require 'ramped.curry'


## Exports

CoffeeScript has a nice trick of creating an Array of the values from each iteration in a `for` loop.
This only works when the loop is assigned to a variable or placed as the return value.

It allows for a very concise definition of this function.

	module.exports = curry (items, value)->
		for call in items
			call value

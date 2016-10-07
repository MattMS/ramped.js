# Reduce

## Imports

	curry = require 'ramped.curry'


## Exports

Take note of the reversed order of the call to the `reducer` function.
The current item from the list is first and the accumulator is second.

	module.exports = curry (reducer, initial_value, list)->
		accumulator = initial_value

		for item in list
			accumulator = reducer(item, accumulator)

		accumulator

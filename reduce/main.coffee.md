# Reduce

## Imports

	{curry} = require 'ramda'


## Exports

	module.exports = curry (reducer, initial_value, list)->
		accumulator = initial_value

Take note of the reversed order of the call to the `reducer` function.
The current item from the list is first and the accumulator is second.

		for item in list
			accumulator = reducer(item, accumulator)

		accumulator

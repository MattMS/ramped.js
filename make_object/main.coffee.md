# Main module for make object

## Imports

	curry = require 'ramped.curry'


## Exports

	module.exports = curry (items, value)->
		o = {}

		for n, v of items
			o[n] = v value

		o

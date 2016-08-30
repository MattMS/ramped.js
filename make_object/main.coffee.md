# Make object

## Imports

	R = require 'ramda'


## Exports

	module.exports = R.curry (items, value)->
		o = {}

		for n, v of items
			o[n] = v value

		o

# Make object

## Imports

	{curry} = require 'ramda'


## Exports

	module.exports = curry (items, value)->
		o = {}

		for n, v of items
			o[n] = v value

		o

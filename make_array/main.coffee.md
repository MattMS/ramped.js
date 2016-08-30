# Make array

## Imports

	R = require 'ramda'


## Exports

	module.exports = R.curry (items, value)->
		for call in items
			call value

# Make array

## Imports

	{curry} = require 'ramda'


## Exports

	module.exports = curry (items, value)->
		for call in items
			call value

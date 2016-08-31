# At least

## Imports

	{curry} = require 'ramda'


## Exports

	module.exports = curry (minimum_value, value)->
		minimum_value <= value

# At least

## Imports

	curry = require 'ramped.curry'


## Exports

	module.exports = curry (minimum_value, value)->
		minimum_value <= value

# Less than

## Imports

	curry = require 'ramped.curry'


## Exports

	module.exports = curry (maximum_value, value)->
		value < maximum_value

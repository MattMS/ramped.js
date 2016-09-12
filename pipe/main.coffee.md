# Pipe

## Library imports

	curry = require 'ramped.curry'


## Exports

	module.exports = curry (calls, initial_value)->
		current_value = initial_value

		for call in calls
			current_value = call current_value

		current_value

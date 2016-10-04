# Main module of bit

## Imports

	curry = require 'ramped.curry'


## Exports

	compare = [128, 64, 32, 16, 8, 4, 2, 1]

	module.exports = curry (index, value)->
		if ('string' == typeof value) and (1 <= value.length)
			value = value.charCodeAt(0)

		if isNaN(index) or isNaN(value)
			0
		else if (index < 1) or (8 < index) or (value < 0) or (255 < value)
			0
		else if 0 < (value & compare[index - 1])
			1
		else
			0

# Main module for append

## Imports

	copy = require 'ramped.copy'

	curry = require 'ramped.curry'


## Exports

Appending anything to an Array will push that item to the end.
Appending an Array to anything except an Array is undefined.

Appending an Integer or String to a String will convert the item to a String and then concatenate them.

When 2 numbers are appended, then it joins them like a String and then converts them back to a number.

	module.exports = curry (item, base)->
		if Array.isArray base
			new_array = copy base

			new_array.push item

			new_array

		else if Array.isArray item
			undefined

		else if 'number' == typeof base
			if 'number' == typeof item
				parseFloat base.toString().concat item.toString()

			else if 'string' == typeof item
				base.toString().concat item

			else
				undefined

		else if 'string' == typeof base
			if 'number' == typeof item
				base.concat item.toString()

			else if 'string' == typeof item
				base.concat item

			else
				undefined

		else
			undefined

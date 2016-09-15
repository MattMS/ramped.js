# Main module

## Imports

	curry = require 'ramped.curry'


## Specific getter functions

### Index in Array

	get_index_in_array = (lookup, original)->
		index = parseInt lookup

		if index < 0
			index = original.length + index
		else
			index -= 1

		if 0 <= index and index < original.length
			original[index]
		else
			undefined


### Key in Object

	get_key_in_object = (lookup, original)->
		original[lookup]


### Path in Object

	get_path_in_object = (lookup, original)->
		current = original

		for key in lookup
			if not current[key]?
				return undefined

			current = current[key]

		current


## Exports

	module.exports = curry (lookup, original)->
		if Array.isArray(original)
			get_index_in_array lookup, original

		else if Array.isArray(lookup)
			get_path_in_object lookup, original

		else
			get_key_in_object lookup, original

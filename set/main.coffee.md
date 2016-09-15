# Main module

## Imports

	copy = require 'ramped.copy'

	curry = require 'ramped.curry'


## Object check function

Using `toString()` seems to avoid matching `new Date()` and `[]`.

- [Check if a value is an object in JavaScript @ Stack Overflow](https://stackoverflow.com/questions/8511281/check-if-a-value-is-an-object-in-javascript)

	is_object = (value)->
		'[object Object]' == value.toString()


## Specific setter functions

### Index in Array

	set_index_in_array = (lookup, value, original)->
		editable = copy original

		index = parseInt lookup

		if index < 0
			index = original.length + index
		else
			index -= 1

		if 0 <= index and index < original.length
			editable[index] = value

		editable


### Key in Object

	set_key_in_object = (lookup, value, original)->
		editable = copy original

		editable[lookup] = value

		editable


### Path in Object

	set_path_in_object = (lookup, value, original)->
		editable = copy original

		current = editable
		index = 0
		last_index = lookup.length - 1

		while index < last_index
			key = lookup[index]

			if not current[key]? or not is_object(current[key])
				current[key] = {}

			current = current[key]

			index += 1

		current[lookup[last_index]] = value

		editable


## Exports

	module.exports = curry (lookup, value, original)->
		if Array.isArray(original)
			if 'number' == typeof value
				set_index_in_array lookup, value, original
			else
				copy original

		else if Array.isArray(lookup)
			set_path_in_object lookup, value, original

		else
			set_key_in_object lookup, value, original

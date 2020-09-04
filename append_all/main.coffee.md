# Main module for append all

## Imports

	append = require 'ramped.append'

	curry = require 'ramped.curry'

	reduce = require 'ramped.reduce'


## Exports

	module.exports = curry (items, existing_array)->
		reduce(append, existing_array, items)

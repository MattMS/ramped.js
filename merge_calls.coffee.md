# Merge called

## Imports

	R = require 'ramda'


## Exports

	module.exports = (items)->
		R.converge R.merge, items

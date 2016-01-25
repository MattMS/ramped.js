# Test make object

## Imports

	make_object = require '../make_object'

	R = require 'ramda'


## Exports

	module.exports = [
		call: make_object
			c: R.prop 'a'
			d: R.prop 'b'

		input:
			a: 1
			b: 2

		output:
			c: 1
			d: 2
	,
		call: make_object
			a: R.pipe R.prop('a'), R.add(2)
			b: R.pipe R.prop('b'), R.add(2)

		input:
			a: 1
			b: 2

		output:
			a: 3
			b: 4
	]

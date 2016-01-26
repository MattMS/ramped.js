# Test make array

## Imports

	main = require '..'

	R = require 'ramda'


## Exports

	module.exports = [
		call: main.make_array [
			R.prop 'a'
			R.prop 'b'
		]

		input:
			a: 1
			b: 2

		output: [
			1
			2
		]
	]

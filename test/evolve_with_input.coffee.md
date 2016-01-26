# Test evolve with input

## Imports

	main = require '..'

	R = require 'ramda'


## Exports

	module.exports = [
		call: main.evolve_with_input
			a: R.prop 'b'
			b: R.prop 'a'

		input:
			a: 1
			b: 2

		output:
			a: 2
			b: 1
	]

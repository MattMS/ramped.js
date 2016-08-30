# Test make array

## Library imports

	R = require 'ramda'

	tape = require 'tape'


## Relative imports

	make_array = require './main'


## Exports

	tests = [
		call: make_array [
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

	for test_data in tests
		tape 'Make array', (t)->
			t.plan 1

			desired_output = test_data.output

			actual_output = test_data.call test_data.input

			t.deepEqual actual_output, desired_output

# Test evolve with input

## Library imports

	R = require 'ramda'

	tape = require 'tape'


## Relative imports

	evolve_with_input = require '../evolve_with_input'


## Exports

	tests = [
		call: evolve_with_input
			a: R.prop 'b'
			b: R.prop 'a'

		input:
			a: 1
			b: 2

		output:
			a: 2
			b: 1
	]

	for test_data in tests
		tape 'Evolve with input', (t)->
			t.plan 1

			desired_output = test_data.output

			actual_output = test_data.call test_data.input

			t.deepEqual actual_output, desired_output

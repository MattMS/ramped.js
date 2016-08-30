# Test make object

## Library imports

	R = require 'ramda'

	tape = require 'tape'


## Relative imports

	make_object = require './main'


## Exports

	tests = [
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

	for test_data in tests
		tape 'Make object', (t)->
			t.plan 1

			desired_output = test_data.output

			actual_output = test_data.call test_data.input

			t.deepEqual actual_output, desired_output

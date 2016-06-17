# Test merge calls

## Library imports

	R = require 'ramda'

	tape = require 'tape'


## Relative imports

	merge_calls = require '../merge_calls'


## Exports

	tests = [
		call: merge_calls [
			R.compose R.objOf('c'), R.prop('a')
		,
			R.compose R.objOf('d'), R.prop('b')
		]

		input:
			a: 1
			b: 2

		output:
			c: 1
			d: 2
	]

	for test_data in tests
		tape 'Merge calls', (t)->
			t.plan 1

			desired_output = test_data.output

			actual_output = test_data.call test_data.input

			t.deepEqual actual_output, desired_output

# Testing make array

## Imports

### Library imports

	get = require 'ramped.get'

	tape = require 'tape'


### Relative imports

	make_array = require './main'


## Run test

	tape 'Make array', (t)->
		t.plan 1

		desired_output = [
			1
			2
		]

		actual_output = make_array [
			get 'a'
			get 'b'
		],
			a: 1
			b: 2

		t.deepEqual actual_output, desired_output

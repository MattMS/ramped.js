# Test make object

## Imports

	assert = require 'assert'

	test_modules = [
		require './make_array'
		require './make_object'
	]


## Run

	for test_module in test_modules
		for test in test_module
			assert.deepEqual test.call(test.input), test.output

# Test make object

## Imports

	assert = require 'assert'

	make_object = require './make_object'


## Run

	for test in make_object
		assert.deepEqual test.call(test.input), test.output

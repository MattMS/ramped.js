# Testing make object

## Imports

### Library imports

	get = require 'ramped.get'

	pipe = require 'ramped.pipe'

	subtract = require 'ramped.subtract'

	tape = require 'tape'


### Relative imports

	make_object = require './main'


## Run tests

	tape 'Make object with get functions', (t)->
		t.plan 1

		desired_output =
			c: 1
			d: 2

		actual_output = make_object
			c: get 'a'
			d: get 'b'
		,
			a: 1
			b: 2

		t.deepEqual actual_output, desired_output


	tape 'Make object with pipes', (t)->
		t.plan 1

		desired_output =
			a: 4
			b: 2

		actual_output = make_object
			a: pipe [
				get 'a'
				subtract 2
			]
			b: pipe [
				get 'b'
				subtract 2
			]
		,
			a: 6
			b: 4

		t.deepEqual actual_output, desired_output

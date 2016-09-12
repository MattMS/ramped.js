# Test pipe

## Library imports

	curry = require 'ramped.curry'

	tape = require 'tape'


## Relative imports

	pipe = require './main'


## Run tests

	tape 'Integer math functions', (t)->
		t.plan 1

		add = curry (b, a)->
			a + b

		divide = curry (b, a)->
			a / b

		get_value = pipe [
			divide(2)
			add(7)
		]

		t.equal get_value(30), 22, 'Pipe 2 partially-applied functions'

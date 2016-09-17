# Test pipe

## Library imports

	curry = require 'ramped.curry'

	tape = require 'tape'


## Relative imports

	pipe = require './main'


## Helper functions

	add = curry (b, a)->
		a + b

	divide = curry (b, a)->
		a / b


## Run tests

	tape 'Integer math functions', (t)->
		t.plan 1

		get_value = pipe [
			divide(2)
			add(7)
		]

		t.equal get_value(30), 22, 'Pipe 2 partially-applied functions'


	tape 'Multiple arguments to first call', (t)->
		t.plan 1

		get_value = pipe [
			add
			divide(2)
		]

		t.equal get_value(8, 4), 6, 'Pipe 2 functions'


	tape 'Nested pipe calls', (t)->
		t.plan 1

		get_value = pipe [
			divide(2),
			pipe([
				add(1),
				add(2)
			]),
			add(4)
		]

		t.equal get_value(30), 22, 'Returned result correctly'

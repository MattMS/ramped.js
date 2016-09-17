# Test pipe

## Imports

### Library imports

	curry = require 'ramped.curry'

	tape = require 'tape'


### Relative imports

	pipe = require './main'


## Helper functions

	add = curry (b, a)->
		a + b

	divide = curry (b, a)->
		a / b


## Run tests

	tape 'Pipe 2 partially-applied functions', (t)->
		t.plan 1

		get_value = pipe [
			divide 2
			add 7
		]

		result = get_value 30

		t.equal result, 22, 'Correct result'


	tape 'Multiple arguments to first call', (t)->
		t.plan 1

		get_value = pipe [
			add
			divide 2
		]

		result = get_value 8, 4

		t.equal result, 6, 'Correct result'


	tape 'Nested pipe calls', (t)->
		t.plan 1

		get_value = pipe [
			divide 2
			pipe [
				add 1
				add 2
			]
			add 4
		]

		result = get_value 30

		t.equal result, 22, 'Correct result'

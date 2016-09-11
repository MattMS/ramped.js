# Test curry

## Library imports

	tape = require 'tape'


## Relative imports

	curry = require './main'


## Helper function

	curried_adder = curry (a, b)->
		b + a


## Run tests

	tape 'Call with all arguments', (t)->
		t.plan 1

		t.equal curried_adder(4, 2), 6, 'Call 2 arguments'

	tape 'Call with single arguments', (t)->
		t.plan 1

		t.equal curried_adder(4)(2), 6, 'Call 2 arguments'

	tape 'Call with extra arguments', (t)->
		t.plan 1

		t.equal curried_adder(4, 2, 1), 6, 'Call 3 arguments'

	tape 'Extra calls with no arguments', (t)->
		t.plan 1

		t.equal curried_adder()(4)()(2), 6

	tape 'Multiple calls to partially-applied function', (t)->
		t.plan 3

		add_4 = curried_adder(4)

		t.equal add_4(2), 6, 'First call to partial function'

		t.equal add_4(3), 7, 'Second call to partial function'

		t.equal add_4(4), 8, 'Third call to partial function'

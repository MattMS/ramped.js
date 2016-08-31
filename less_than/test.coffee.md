# Test less than

## Library imports

	tape = require 'tape'


## Relative imports

	less_than = require './main'


## Run tests

### Positive integers

	tape 'positive integers', (t)->
		t.plan 3

		t.ok less_than(4)(2), '2 is less than 4'

		t.notOk less_than(4)(4), '4 is not less than 4'

		t.notOk less_than(4)(6), '6 is not less than 4'


### Negative integers

	tape 'negative numbers', (t)->
		t.plan 3

		t.ok less_than(-4)(-6), '-6 is less than -4'

		t.notOk less_than(-4)(-4), '-4 is not less than -4'

		t.notOk less_than(-4)(-2), '-2 is not less than -4'

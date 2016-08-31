# Test more than

## Library imports

	tape = require 'tape'


## Relative imports

	more_than = require './main'


## Run tests

### Positive integers

	tape 'positive integers', (t)->
		t.plan 3

		t.notOk more_than(4)(2), '2 is not more than 4'

		t.notOk more_than(4)(4), '4 is not more than 4'

		t.ok more_than(4)(6), '6 is more than 4'


### Negative integers

	tape 'negative numbers', (t)->
		t.plan 3

		t.notOk more_than(-4)(-6), '-6 is not more than -4'

		t.notOk more_than(-4)(-4), '-4 is not more than -4'

		t.ok more_than(-4)(-2), '-2 is more than -4'

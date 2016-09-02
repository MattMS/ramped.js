# Test subtract

## Library imports

	tape = require 'tape'


## Relative imports

	subtract = require './main'


## Run tests

### Positive integers

	tape 'positive integers', (t)->
		t.plan 3

		t.equal subtract(4)(2), -2, '2 - 4'

		t.equal subtract(4)(4), 0, '4 - 4'

		t.equal subtract(4)(6), 2, '6 - 4'


### Negative integers

	tape 'negative numbers', (t)->
		t.plan 3

		t.equal subtract(-4)(-6), -2, '-6 - -4'

		t.equal subtract(-4)(-4), 0, '-4 - -4'

		t.equal subtract(-4)(-2), 2, '-2 - -4'

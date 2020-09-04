# Test add

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	add = require './main'


## Run tests

### Positive integers

	tape 'positive integers', (t)->
		t.plan 3

		t.equal add(4)(2), 6, '2 + 4'

		t.equal add(4)(4), 8, '4 + 4'

		t.equal add(4)(6), 10, '6 + 4'


### Negative integers

	tape 'negative numbers', (t)->
		t.plan 3

		t.equal add(-4)(-6), -10, '-6 + -4'

		t.equal add(-4)(-4), -8, '-4 + -4'

		t.equal add(-4)(-2), -6, '-2 + -4'

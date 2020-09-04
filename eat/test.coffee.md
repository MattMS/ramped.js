# Test eat

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	eat = require './main'


## Run tests

	add = (a)-> (b)-> (c)-> a + b + c

	tape 'positive integers', (t)->
		t.plan 1

		t.equal eat(add, 2, 4, 6), 12, '2 + 4 + 6'

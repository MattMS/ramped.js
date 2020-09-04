# Testing reverse

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	reverse = require './main'


## Run tests

### Array

	tape 'Reverse Array', (t)->
		t.plan 1

		t.deepEqual reverse([1, 2, 3]), [3, 2, 1]


### Integer

	tape 'Reverse positive Integer', (t)->
		t.plan 1

		t.deepEqual reverse(12), 21


### String

	tape 'Reverse String', (t)->
		t.plan 1

		t.deepEqual reverse('abc'), 'cba'

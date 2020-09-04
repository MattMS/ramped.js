# Testing append all

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	append_all = require './main'


## Run tests

	tape 'Extend Array with a couple of items', (t)->
		t.plan 3

		add_numbers = append_all([3, 4])

		t.deepEqual add_numbers([1, 2]), [1, 2, 3, 4]

		t.deepEqual add_numbers(12), 1234

		t.deepEqual add_numbers('a'), 'a34'


	tape 'Empty Array does not change the original', (t)->
		t.plan 3

		empty = append_all([])

		t.deepEqual empty([1, 2]), [1, 2]

		t.deepEqual empty(12), 12

		t.deepEqual empty('ab'), 'ab'


	tape 'Extend with String Array', (t)->
		t.plan 3

		add_text = append_all(['cd', 'ef'])

		t.deepEqual add_text(['ab']), ['ab', 'cd', 'ef']

		t.deepEqual add_text(12), '12cdef'

		t.deepEqual add_text('ab'), 'abcdef'

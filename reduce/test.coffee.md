# Test reduce

## Library imports

	{curry} = require 'ramda'

	tape = require 'tape'


## Relative imports

	reduce = require './main'


## Helper functions

	append = curry (item, acc)->
		acc.push(item)
		acc

	subtract = curry (item, acc)->
		acc - item


## Run tests

### Append

	tape 'reduce with append', (t)->
		t.plan 1

		actual = reduce(append, [], [1, 2, 3])

		expected = [1, 2, 3]

		t.deepEqual actual, expected


### Subtract

	tape 'reduce with subtract', (t)->
		t.plan 1

		actual = reduce(subtract, 12, [1, 2, 3])

		expected = 6

		t.equal actual, expected

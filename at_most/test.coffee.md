# Test at most

## Library imports

	tape = require 'tape'


## Relative imports

	at_most = require './main'


## Run tests

### Positive integers

	tape '6 is not at most 4', (t)->
		t.plan 1

		t.notOk at_most(4)(6)

	tape '2 is at most 4', (t)->
		t.plan 1

		t.ok at_most(4)(2)

	tape '4 is at most 4', (t)->
		t.plan 1

		t.ok at_most(4)(4)


### Negative integers

	tape '-2 is not at most -4', (t)->
		t.plan 1

		t.notOk at_most(-4)(-2)

	tape '-6 is at most -4', (t)->
		t.plan 1

		t.ok at_most(-4)(-6)

	tape '-4 is at most -4', (t)->
		t.plan 1

		t.ok at_most(-4)(-4)

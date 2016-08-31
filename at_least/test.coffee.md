# Test at least

## Library imports

	tape = require 'tape'


## Relative imports

	at_least = require './main'


## Run tests

### Positive integers

	tape '6 is at least 4', (t)->
		t.plan 1

		t.ok at_least(4)(6)

	tape '2 is not at least 4', (t)->
		t.plan 1

		t.notOk at_least(4)(2)

	tape '4 is at least 4', (t)->
		t.plan 1

		t.ok at_least(4)(4)


### Negative integers

	tape '-2 is at least -4', (t)->
		t.plan 1

		t.ok at_least(-4)(-2)

	tape '-6 is not at least -4', (t)->
		t.plan 1

		t.notOk at_least(-4)(-6)

	tape '-4 is at least -4', (t)->
		t.plan 1

		t.ok at_least(-4)(-4)

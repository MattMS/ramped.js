# Testing bit

## Library imports

	tape = require 'tape'


## Relative imports

	bit = require './main'


## Run tests

### All set to 0

	tape 'All bits set to 0', (t)->
		t.plan 8

		value = 0
		expected = [0, 0, 0, 0, 0, 0, 0, 0]

		for i in [1..8]
			t.equal bit(i)(value), expected[i - 1], "Bit #{i} is 0"


### All set to 1

	tape 'All bits set to 1', (t)->
		t.plan 8

		value = 255
		expected = [1, 1, 1, 1, 1, 1, 1, 1]

		for i in [1..8]
			t.equal bit(i)(value), expected[i - 1], "Bit #{i} is 1"


### Digit in String value

	tape 'Digit 1 in String for value', (t)->
		t.plan 8

		value = '1'
		expected = [0, 0, 1, 1, 0, 0, 0, 1]

		for i in [1..8]
			t.equal bit(i)(value), expected[i - 1], "Bit #{i} is #{expected[i - 1]}"


### ASCII character value

	tape 'Lower-case a for value', (t)->
		t.plan 8

		value = 'a'
		expected = [0, 1, 1, 0, 0, 0, 0, 1]

		for i in [1..8]
			t.equal bit(i)(value), expected[i - 1], "Bit #{i} is #{expected[i - 1]}"


### ASCII String value

	tape 'String of abc for value', (t)->
		t.plan 8

		value = 'abc'
		expected = [0, 1, 1, 0, 0, 0, 0, 1]

		for i in [1..8]
			t.equal bit(i)(value), expected[i - 1], "Bit #{i} is #{expected[i - 1]}"


### Single bit set to 1

	tape 'Single bit set to 1', (t)->
		t.plan 4

		t.equal bit(1)(128), 1, "Bit 1 of 128 is 1"

		t.equal bit(8)(128), 0, "Bit 8 of 128 is 0"

		t.equal bit(1)(1), 0, "Bit 1 of 1 is 0"

		t.equal bit(8)(1), 1, "Bit 8 of 1 is 1"


### Invalid index

	tape 'Invalid index', (t)->
		t.plan 2

		t.equal bit(0)(255), 0, "Invalid index 0 is 0"

		t.equal bit(9)(255), 0, "Invalid index 9 is 0"


### Invalid value

	tape 'Invalid value', (t)->
		t.plan 2

		t.equal bit(1)(-1), 0, "Invalid value -1 is 0"

		t.equal bit(1)(256), 0, "Invalid value 256 is 0"

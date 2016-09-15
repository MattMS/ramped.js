# Test change

## Library imports

	tape = require 'tape'


## Relative imports

	copy = require './main'


## Run tests

	tape 'Date', (t)->
		t.plan 1

		original = new Date(1999, 12, 31, 23, 59, 59)

		actual = copy(original)

		expected = new Date(1999, 12, 31, 23, 59, 59)

		original.setDate 1

		original.setFullYear 2000

		original.setHours 1

		original.setMinutes 1

		original.setMonth 1

		original.setSeconds 1

		t.deepEqual actual, expected

	tape 'Integer', (t)->
		t.plan 1

		actual = copy(12)

		expected = 12

		t.equal actual, expected

	tape 'String', (t)->
		t.plan 1

		actual = copy('Matt')

		expected = 'Matt'

		t.equal actual, expected

	tape 'Array of Integers', (t)->
		t.plan 1

		original = [4, 8, 12]

		actual = copy(original)

		original[1] = 24

		original.push 36

		expected = [4, 8, 12]

		t.deepEqual actual, expected

	tape 'Object of Integers', (t)->
		t.plan 1

		original =
			a: 2
			b: 4
			c: 8

		actual = copy(original)

		original.b = 24

		original.d = 36

		expected =
			a: 2
			b: 4
			c: 8

		t.deepEqual actual, expected

	tape 'Object with nested Array', (t)->
		t.plan 1

		original =
			a:
				ab: 'cd'
				ac: [
					2,
					4,
					ace: 32
					ack: 64
				]
			b: 12

		expected =
			a:
				ab: 'cd'
				ac: [
					2,
					4,
					ace: 32
					ack: 64
				]
			b: 12

		actual = copy(original)

		original.a.ac[1] = 24

		original.a.ac[2].ack = 36

		t.deepEqual actual, expected

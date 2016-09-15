# Test main module

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	set = require './main'


## Run tests

### Array

	tape 'Array', (t)->
		t.plan 7

		original = [16, 32, 64]

		t.deepEqual set(-4, 12, original), [16, 32, 64], 'Index too small on Array does nothing'

		t.deepEqual set(-3, 12, original), [12, 32, 64], 'Index of -3 changes third last Array item'

		t.deepEqual set(-1, 12, original), [16, 32, 12], 'Index of -1 changes last Array item'

		t.deepEqual set(0, 12, original), [16, 32, 64], 'Index of 0 on Array does nothing'

		t.deepEqual set(1, 12, original), [12, 32, 64], 'Index of 1 changes first Array item'

		t.deepEqual set(3, 12, original), [16, 32, 12], 'Index of 3 changes third Array item'

		t.deepEqual set(4, 12, original), [16, 32, 64], 'Index too big on Array does nothing'


### Object

	tape 'Object', (t)->
		t.plan 2

		original = {a: 16, b: 32, c: 64}

		t.deepEqual set('b', 12, original), {a: 16, b: 12, c: 64}, 'Matching key sets property on Object'

		t.deepEqual set('d', 12, original), {a: 16, b: 32, c: 64, d: 12}, 'Missing key adds property to Object'


### Object with path

	tape 'Object with path', (t)->
		t.plan 4

		original = {a: {b: 32}, c: 64}

		t.deepEqual set(['a', 'b'], 12, original), {a: {b: 12}, c: 64}, 'Matching path changes property on Object'

		t.deepEqual set(['a', 'c'], 12, original), {a: {b: 32, c: 12}, c: 64}, 'Partially matching path adds property to Object'

		t.deepEqual set(['d', 'e'], 12, original), {a: {b: 32}, c: 64, d: {e: 12}}, 'Missing path adds property with path to Object'

		t.deepEqual set(['c', 'd'], 12, original), {a: {b: 32}, c: {d: 12}}, 'Matching path replaces simple property on Object'


### Ensure copy

	tape 'Copy Array', (t)->
		t.plan 1

		original = [16, 32, 64]

		expected = set(1, 12, original)

		original[1] = 24

		t.deepEqual expected, [12, 32, 64], 'Array is copied, so changes to original are ignored'

	tape 'Copy Object', (t)->
		t.plan 1

		original = {a: 16, b: 32, c: 64}

		expected = set('a', 12, original)

		original.a = 24

		t.deepEqual expected, {a: 12, b: 32, c: 64}, 'Object is copied, so changes to original are ignored'

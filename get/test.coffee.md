# Test main module

## Imports

### Library imports

	tape = require 'tape'


### Relative imports

	get = require './main'


## Run tests

### Array

	tape 'Array', (t)->
		t.plan 7

		original = [16, 32, 64]

		t.deepEqual get(-4, original), undefined, 'Index too small on Array returns undefined'

		t.deepEqual get(-3, original), 16, 'Index of -3 returns third last Array item'

		t.deepEqual get(-1, original), 64, 'Index of -1 returns last Array item'

		t.deepEqual get(0, original), undefined, 'Index of 0 on Array returns undefined'

		t.deepEqual get(1, original), 16, 'Index of 1 returns first Array item'

		t.deepEqual get(3, original), 64, 'Index of 3 returns third Array item'

		t.deepEqual get(4, original), undefined, 'Index too big on Array returns undefined'


### Object

	tape 'Object', (t)->
		t.plan 2

		original = {a: 16, b: 32, c: 64}

		t.deepEqual get('b', original), 32, 'Matching key returns property on Object'

		t.deepEqual get('d', original), undefined, 'Missing key returns undefined'


### Object with path

	tape 'Object with path', (t)->
		t.plan 5

		original = {a: {b: 32}, c: 64}

		t.deepEqual get(['a', 'b'], original), 32, 'Matching path returns nested property on Object'

		t.deepEqual get(['a', 'c'], original), undefined, 'Partially matching path returns undefined'

		t.deepEqual get(['d', 'e'], original), undefined, 'Missing path returns undefined'

		t.deepEqual get(['c', 'd'], original), undefined, 'Partially matching path on simple property returns undefined'

		original = {a: {b: {c: 16}}, c: 64}

		t.deepEqual get(['a', 'b'], original), {c: 16}, 'Matching path returns nested Object on Object'

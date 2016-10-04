# Testing append

## Library imports

	tape = require 'tape'


## Relative imports

	append = require './main'


## Run tests

### Append to Array

	tape 'append Array to Array pushes to Array', (t)->
		t.plan 1

		t.deepEqual append([3, 4])([1, 2]), [1, 2, [3, 4]]

	tape 'append Integer to Array pushes to Array', (t)->
		t.plan 1

		t.deepEqual append(3)([1, 2]), [1, 2, 3]

	tape 'append Object to Array pushes to Array', (t)->
		t.plan 1

		t.deepEqual append({a: 3})([1, 2]), [1, 2, {a: 3}]

	tape 'append String to Array pushes to Array', (t)->
		t.plan 1

		t.deepEqual append('ef')(['ab', 'cd']), ['ab', 'cd', 'ef']


### Append Array to non-Array

	tape 'append Array to Integer is undefined', (t)->
		t.plan 1

		t.deepEqual append([3, 4])(12), undefined

	tape 'append Array to Object is undefined', (t)->
		t.plan 1

		t.deepEqual append([3, 4])({a: 1}), undefined

	tape 'append Array to String is undefined', (t)->
		t.plan 1

		t.deepEqual append([3, 4])('ab'), undefined


### Append to Integer

	tape 'append Integer to Integer joins both', (t)->
		t.plan 1

		t.deepEqual append(34)(12), 1234

	tape 'append Object to Integer is undefined', (t)->
		t.plan 1

		t.deepEqual append({a: 1})(12), undefined

	tape 'append String to Integer joins both', (t)->
		t.plan 1

		t.deepEqual append('ab')(12), '12ab'


### Append to String

	tape 'append Integer to String joins both', (t)->
		t.plan 1

		t.deepEqual append(12)('ab'), 'ab12'

	tape 'append Object to String is undefined', (t)->
		t.plan 1

		t.deepEqual append({a: 1})('ab'), undefined

	tape 'append String to String joins both', (t)->
		t.plan 1

		t.deepEqual append('def')('abc'), 'abcdef'

# Ramped set

Change an item in an Array or Object, without modifying the original.

Accepts an Array of keys for setting a nested property.

To change the first item in an Array use `1`, and `-1` for the last.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.set --save


## Usage

	set = require('ramped.set')

	set(1, 12, [1, 2, 3])
	// [12, 2, 3]

	set(-1, 12, [1, 2, 3])
	// [1, 2, 12]

	set('a', 12, {a: 1, b: 2})
	// {a: 12, b: 2}

	set('c', 12, {a: 1, b: 2})
	// {a: 1, b: 2, b: 12}

	set(['a', 'b'], 12, {a: {b: 2}})
	// {a: {b: 12}}

	set(['c', 'd'], 12, {a: {b: 2}})
	// {a: {b: 2}, c: {d: 12}}


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

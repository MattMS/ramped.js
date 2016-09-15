# Ramped get

Get an item in an Array or Object.

Accepts an Array of keys for getting a nested property.

To get the first item in an Array use `1`, or `-1` for the last.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.get --save


## Usage

	get = require('ramped.get')

	get(1, [1, 2, 3])
	// 1

	get(-1, [1, 2, 3])
	// 3

	get('a', {a: 1, b: 2})
	// 1

	get('c', {a: 1, b: 2})
	// undefined

	get(['a', 'b'], {a: {b: 2}})
	// 2

	get(['c', 'd'], {a: {b: 2}})
	// undefined


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

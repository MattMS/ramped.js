# Ramped copy

Make a copy of an Array, Date, or Object.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.copy --save


## Usage

	copy = require('ramped.copy')

	original = {a: 1, b: {c: [2, 3]}}

	duplicate = copy(original)

	original.b = 0

	duplicate.b.c[0]
	// 2


## Dependencies

None


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

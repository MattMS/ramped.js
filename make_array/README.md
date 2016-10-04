# Ramped make array

Build items in an array from functions applied to a single input.

This is the same as [Ramda juxt](http://ramdajs.com/docs/#juxt).


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.make_array --save


## Usage

	make_array = require('ramped.make_array')

	convert = make_array([
		R.prop('a'),
		R.prop('b')
	])

	new_array = convert({a: 1, b: 2})
	// [1, 2]


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

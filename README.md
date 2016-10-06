# Ramped

A collection of functions to make functional programming easier.

I would highly recommend using [Ramda](http://ramdajs.com/) first.
This library implements a small subset of the functions in Ramda using a different approach in naming, parameter ordering, and separating packages.

Each of these functions can be installed individually by prefixing them with `ramped.`, such as `npm i ramped.make_array`.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped --save


## Usage

	ramped = require('ramped')

	convert = ramped.make_array([
		R.prop('a'),
		R.prop('b')
	])

	new_array = convert({a: 1, b: 2})
	// [1, 2]


### Functions

- [make_array](./make_array/)

- [make_object](./make_object/)


## License

[ISC](./LICENSE)

# Ramped

Extra functions for working with [Ramda](http://ramdajs.com/).


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped --save


## Usage

	R = require('ramda')

	ramped = require('ramped')

	convert = ramped.make_object({
		c: R.prop('a'),
		d: R.prop('b')
	})

	new_object = convert({a: 1, b: 2})
	// {c: 1, d: 2}


## License

[ISC](./LICENSE)

# Ramped

Extra functions for working with [Ramda](http://ramdajs.com/).

I recommend playing with Ramda *before* considering this module since this is currently little more than an experiment.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped --save

You will also want Ramda installed:

	npm i ramda --save


## Usage

	R = require('ramda')

	ramped = require('ramped')


### Evolve with input

Same as the [evolve](http://ramdajs.com/docs/#evolve) function, but passes the entire object in, instead of just the value of the key.

	convert = ramped.evolve_with_input({
		a: R.prop('b'),
		b: R.prop('a')
	})

	new_object = convert({a: 1, b: 2})
	// {a: 2, b: 1}


### Make array

	convert = ramped.make_array([
		R.prop('a'),
		R.prop('b')
	])

	new_array = convert({a: 1, b: 2})
	// [1, 2]


### Make object

	convert = ramped.make_object({
		c: R.prop('a'),
		d: R.prop('b')
	})

	new_object = convert({a: 1, b: 2})
	// {c: 1, d: 2}


## License

[ISC](./LICENSE)

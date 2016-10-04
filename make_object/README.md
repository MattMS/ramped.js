# Ramped make object

Build properties of an object from functions applied to a single argument.

Like [Ramda applySpec](http://ramdajs.com/docs/#applySpec), but only accepts a single argument.
Which is similar to [Ramda.evolve](http://ramdajs.com/docs/#evolve) but this passes in the entire object instead of just the value of each key.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.make_object --save


## Usage

	make_object = require('ramped.make_object')

	convert = make_object({
		c: R.prop('a'),
		d: R.prop('b')
	})

	new_object = convert({a: 1, b: 2})
	// {c: 1, d: 2}


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

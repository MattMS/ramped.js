# Ramped pipe

Connect functions into a pipeline: the output of one is the input of the next.

The first function in the `pipe` can accept any number of arguments, but it **cannot be partially-applied**.

Consider the following: `pipe([add, map])(3)([1, 2, 3])`.
If the pipe could be partially-applied, then `add` would receive the Array as the second argument, instead of `map` getting `add(3)` as the first argument.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.pipe --save


## Usage

	curry = require('ramped.curry')
	pipe = require('ramped.pipe')

	add = curry((b, a) => a + b)
	divide = curry((b, a) => a / b)

	get_value = pipe([
		divide(2),
		add(7)
	])

	get_value(30)
	// = 22


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

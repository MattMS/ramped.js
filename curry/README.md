# Ramped curry

Convert a function to allow partial application.

See [currying](https://en.m.wikipedia.org/wiki/Currying)
and [partial application](https://en.m.wikipedia.org/wiki/Partial_application)
on Wikipedia.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.curry --save


## Usage

	curry = require('ramped.curry')

	add_curry = curry (a, b)->
		a + b

	add_4 = add_curry(4)

	add_4(2)
	// 6


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

# Ramped pipe

Connect functions into a pipeline: the output of one is the input of the next.


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

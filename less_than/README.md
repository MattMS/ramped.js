# Ramped less than

Return true if the second value is smaller than the first.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.less_than --save


## Usage

	less_than = require('ramped.less_than')

	is_less_than_4 = less_than(4)

	is_less_than_4(6)
	// false

	is_less_than_4(4)
	// false

	is_less_than_4(2)
	// true


## Dependencies

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

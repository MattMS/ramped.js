# Ramped at most

Return true if the second value is the same as or smaller than the first.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.at_most --save


## Usage

	at_most = require('ramped.at_most')

	is_4_or_less = at_most(4)

	is_4_or_less(6)
	// false

	is_4_or_less(4)
	// true

	is_4_or_less(2)
	// true


## Dependencies

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

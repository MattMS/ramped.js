# Ramped at least

Return true if the second value is the same as or bigger than the first.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.at_least --save


## Usage

	at_least = require('ramped.at_least')

	is_4_or_more = at_least(4)

	is_4_or_more(6)
	// true

	is_4_or_more(4)
	// true

	is_4_or_more(2)
	// false


## Dependencies

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

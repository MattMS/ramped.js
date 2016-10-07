# Ramped more than

Return true if the second value is bigger than the first.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.more_than --save


## Usage

	more_than = require('ramped.more_than')

	is_more_than_4 = more_than(4)

	is_more_than_4(6)
	// true

	is_more_than_4(4)
	// false

	is_more_than_4(2)
	// false


## Dependencies

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

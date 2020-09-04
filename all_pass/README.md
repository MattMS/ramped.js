# Ramped all pass

Return true if all the given tests pass for the given input.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.all_pass --save


## Usage

	all_pass = require('ramped.all_pass')
	at_least = require('ramped.at_least')
	at_most = require('ramped.at_most')

	within_1_to_10 = all_pass([
		at_least(1),
		at_most(10)
	])

	within_1_to_10(6)
	// true

	within_1_to_10(0)
	// false


## Dependencies

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

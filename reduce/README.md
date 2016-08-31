# Ramped reduce

Reduce a list of values into a single value.
Starts by calling the given function with an initial value and the first item of the list.
Then loops the rest of the list, calling the given function with the last returned value and the current item from the list.

The reducer function must accept the current value as the first parameter and the running total as the second parameter.
This is the flipped version of [Ramda.reduce](http://ramdajs.com/docs/#reduce).


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.reduce --save


## Usage

	reduce = require('ramped.reduce')

	subtract = (item, acc) => acc - item

	reduce(subtract, 12, [1, 2, 3])
	// 6


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

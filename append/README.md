# Ramped append

Add an item to the end of another Array, Number, or String.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.append --save


## Usage

	append = require('ramped.append')

	add_text_to_end = append('def')

	add_text_to_end('abc')
	// 'abcdef'

	add_text_to_end([1, 2])
	// [1, 2, 'def']

	add_array_as_item = append([3, 4])
	add_array_as_item([1, 2])
	// [1, 2, [3, 4]]

	append_60 = append(60)
	append_60(12)
	// 1260

The last usage (joining 2 numbers) should only be done with integers, to avoid complications with floating point values.


## Dependencies

- [ramped.copy](https://www.npmjs.com/package/ramped.copy)

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

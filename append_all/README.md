# Ramped append all

Append all items in an Array to another Array.

Part of the [ramped.js](https://github.com/MattMS/ramped.js) collection for functional programming.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.append_all --save


## Usage

	append_all = require('ramped.append_all')

	add_items = append_all([3, 4])

	add_text = append_all(['cd', 'ef'])

	add_text('ab')
	// 'abcdef'

	add_text(['ab'])
	// ['ab', 'cd', 'ef']


## Dependencies

- [ramped.append](https://www.npmjs.com/package/ramped.append)

- [ramped.curry](https://www.npmjs.com/package/ramped.curry)

- [ramped.reduce](https://www.npmjs.com/package/ramped.reduce)


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

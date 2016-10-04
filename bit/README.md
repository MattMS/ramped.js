# Ramped bit

Get the state (0 or 1) of the bit at the given index in a given value.

| Index | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|-------|---|---|---|---|---|---|---|---|
|     1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |
|   128 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
|   'a' | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1 |
|   '1' | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 1 |

If an invalid index or value is given, then `0` is returned.

Will not accept numbers over 255 or below 0.

Will accept a String of 1 or more characters, but only uses the first byte.


## Install

To add as a dependency to a [Node.js](https://nodejs.org/en/) project:

	npm i ramped.bit --save


## Usage

	bit = require('ramped.bit')

	highest_bit = bit(1)
	lowest_bit = bit(8)

	highest_bit(128)
	// 1

	lowest_bit(128)
	// 0

	lowest_bit(1)
	// 1


## License

[ISC](https://github.com/MattMS/ramped.js/blob/master/LICENSE)

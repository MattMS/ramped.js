# Evolve with input

## Imports

	R = require 'ramda'


## Exports

	module.exports = R.curry (evolver, value)->
		o = R.clone value

		for n, v of evolver
			o[n] = v value

		o

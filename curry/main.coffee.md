# Curry package main export

This is the main module for the `ramped.curry` package.


## Argument collecting function

Please note: `all_args` is intentionally named differently to `saved_args`, otherwise it will not copy the Array.
Using the same variable name will cause partially-applied functions to behave incorrectly.

	curry_maker = (actual_function, saved_args)->
		(args...)->
			all_args = saved_args.concat args

Check if we have the required number of arguments to call the proper function, then call it with all the arguments.

			if actual_function.length <= all_args.length
				actual_function all_args...

If we do not have the required number of arguments, then a new collector function is returned, with the arguments.

			else
				curry_maker actual_function, all_args


## Export

Exports a function that accepts a single argument: the function to be curried.

Returns a function that will collect arguments.
This function will proxy calls to the proper (passed-in) function.

	module.exports = (actual_function)->
		(args...)->

Check if we already have been given enough arguments, and then make the call.

			if actual_function.length <= args.length
				actual_function args...

Otherwise, we should start collecting the arguments.

			else
				curry_maker actual_function, args

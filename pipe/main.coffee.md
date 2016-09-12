# Pipe

Cannot use `curry` because the first call may expect any number of arguments.

	module.exports = (calls)->
		(initial_args...)->
			current_value = calls[0] initial_args...

			for call in calls.slice(1)
				current_value = call current_value

			current_value

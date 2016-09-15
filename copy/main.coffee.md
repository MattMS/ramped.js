# Copy main module

## Recursive copy function

	copy = (value)->
		if 'boolean' == typeof value
			value

		else if 'number' == typeof value
			value

		else if 'string' == typeof value
			value

		else if value instanceof Date
			new Date(value.getTime())

		else if Array.isArray and Array.isArray(value)
			for item in value
				copy(item)

		else
			copied = {}

			for key, item of value
				copied[key] = copy item

			copied


## Exports

	module.exports = (value)->
		copy value


## Links

- [Array.isArray() @ MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)

- [Difference between using Array.isArray and instanceof Array @ Stack Overflow](https://stackoverflow.com/questions/22289727/difference-between-using-array-isarray-and-instanceof-array)

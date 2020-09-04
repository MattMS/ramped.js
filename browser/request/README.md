# ramped.browser.request

	request = require('@ramped/browser.request')

	request('get', 'test.json', {}, null).fork(console.error, console.log)

- https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader

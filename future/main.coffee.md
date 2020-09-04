# Ramped future

	future = (fork)->
		empty: ->
			future ->

		fork: fork

		map: (call)->
			future (reject, resolve)->
				fork reject, (value)->
					resolve call value

		reject: (value)->
			future (reject, _)->
				reject value

		resolve: (value)->
			future (_, resolve)->
				resolve value

	future.of = future.resolve

	module.exports = future

const httpGet = url => Future((reject, resolve)=>{
request(url, (err, data)=> err? reject(err) : resolve(data))
})
const myGet = httpGet('http://example.org/something.json')
.map(JSON.parse)
.fork(console.error, console.log)

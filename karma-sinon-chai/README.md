karma-sinon-chai
================

  * [Sinon](http://sinonjs.org/)
  * [Chai](http://chaijs.com)
  * [Sinon-Chai](https://github.com/domenic/sinon-chai)

for [Karma](http://karma-runner.github.io)

Requirements
------------

This Karma plugin requires Karma `>=0.10`

Installation
------------

Install the module via npm

```sh
$ npm install --save-dev karma-sinon-chai
```

Add `sinon-chai` to the `frameworks` key in your Karma configuration:

```js
module.exports = function(config) {
  'use strict';
  config.set({
    frameworks: ['mocha', 'sinon-chai'],
    #...
  });
}
```

Usage
-----

Each of the different Chai assertion suites is available in the tests:

```coffee
describe 'karma tests with chai', ->

  it 'should expose the Chai assert method', ->
    assert.ok('everything', 'everything is ok');

  it 'should expose the Chai expect method', ->
    expect('foo').to.not.equal 'bar'

  it 'should expose the Chai should property', ->
    1.should.not.equal 2
    should.exist 123
```

Sinon and Chai matchers for Sinon are also available:

```coffee
describe 'karma tests with sinon', ->

  it 'can spy on objects', ->
    foo = bar: ->
    sinon.spy foo, 'bar'

    foo.bar 'baz'

    foo.bar.should.have.been.calledWith 'baz'
```


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/kmees/karma-sinon-chai/trend.png)](https://bitdeli.com/free "Bitdeli Badge")


# fastq&nbsp;&nbsp;[![build status](https://secure.travis-ci.org/mcollina/fastq.png)](http://travis-ci.org/mcollina/fastq)

Fast, in memory work queue.

Benchmarks (1 million tasks):

* setImmedidate: 1715ms
* fastqueue: 1824ms
* async.queue: 6158ms

Obtained on node 0.12.3, on a HP Spectre 360 (the Build 2015 edition).

## Install

`npm i fastq --save`

## Usage

```js
'use strict'

var queue = require('fastq')(worker, 1)

queue.push(42, function (err, result) {
  if (err) { throw err }
  console.log('the result is', result)
})

function worker (arg, cb) {
  cb(null, 42 * 2)
}
```

## License

ISC

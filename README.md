# structured-log-seq-sink [![Build Status](https://travis-ci.org/Wedvich/structured-log-seq-sink.svg?branch=master)](https://travis-ci.org/Wedvich/structured-log-seq-sink)

A [structured-log](https://github.com/structured-log/structured-log) plugin that writes log events to [Seq](https://getseq.net/).

**Requires polyfills for `Promise` and `fetch` if those aren't supported in your target platform/browser.**

### Installation

```
npm i structured-log-seq-sink --save
```

### Usage

```js
var structuredLog = require('structured-log');
var seqSink = require('structured-log-seq-sink');

var logger = structuredLog.configure()
  .writeTo(seqSink({ /* ... options ...  */ }))
  .create();

```

##### Available options

|Parameter|Description|
|---|---|
|`apiKey`|(optional) API key to use|
|`compact`|(optional) If true, events be serialized using [Serilog's compact format](https://github.com/serilog/serilog-formatting-compact)|
|`durable`|(optional) If true, events will be buffered in local storage if available|
|`url`|(required) URL to the Seq server|

### Building and testing

To build the modules yourself, check out the code, then install dependencies and run the `build` script:

```
npm i
npm run build
```

Then, you can test the bundled module by running:

```
npm test
```

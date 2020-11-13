# cache-storage-chunk-store

[![npm](https://img.shields.io/npm/v/cache-storage-chunk-store.svg)](https://npm.im/cache-storage-chunk-store)
![downloads](https://img.shields.io/npm/dt/cache-storage-chunk-store.svg)
[![dependencies](https://david-dm.org/mathiasvr/cache-storage-chunk-store.svg)](https://david-dm.org/mathiasvr/cache-storage-chunk-store)
[![license](https://img.shields.io/:license-MIT-blue.svg)](https://mvr.mit-license.org)

#### Browser [CacheStorage](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage) chunk store that is [abstract-chunk-store](https://github.com/mafintosh/abstract-chunk-store) compliant

[![abstract chunk store](https://cdn.rawgit.com/mafintosh/abstract-chunk-store/master/badge.svg)](https://github.com/mafintosh/abstract-chunk-store)

## Install

```
npm install cache-storage-chunk-store
```

or include it directly:
```html
<script src="https://cdn.jsdelivr.net/npm/cache-storage-chunk-store@1.x/dist/cache-storage-chunk-store.min.js"></script>
```

## Usage

``` js
const CacheStorageChunkStore = require('cache-storage-chunk-store')

const chunks = new CacheStorageChunkStore(10)

chunks.put(0, buffer, (err) => console.error(err))

chunks.get(0, (err, buf) => console.log(err, buf))
```

## Known issues
Chrome can stall and never finish if running many `get` calls concurrently.

Specifically this problem occurs when calling the `ReadableStream.getReader.read()` function more than once.

## License

MIT

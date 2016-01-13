# spritezero

[![build status](https://secure.travis-ci.org/mapbox/spritezero.svg)](http://travis-ci.org/mapbox/spritezero)

Small opinionated sprites.

Why is this different than sprite generation libraries like [spritesmith](https://github.com/Ensighten/spritesmith)?
spritezero was initially created to power a sprite API, and thus is geared towards
_performance_, as well as an ability to work with image data in _buffers_
rather than on disk. Also, since version 2.0, spritezero generates sprites
based on SVG graphics alone, therefore making it possible to support @2x
and higher-dpi sprites from the same source.

### `generateLayout(imgs, ratio, format, callback)`

Pack a list of images with width and height into a sprite layout.
Uses bin-pack.

### Parameters

| parameter  | type              | description                                                   |
| ---------- | ----------------- | ------------------------------------------------------------- |
| `imgs`     | Array\.\<Object\> | array of `{ svg: Buffer, id: String }` |
| `scale`    | number | pixel scale. default is 1, retina is 2 |
| `format`   | boolean           | format this layout for mapbox gl                              |
| `callback` | function          | returns two arguments, `err` and `layout` |



**Returns** `Object`, layout


### `generateImage(packing, callback)`

Generate a PNG image with positioned icons on a sprite.

### Parameters

| parameter  | type     | description |
| ---------- | -------- | ----------- |
| `packing`  | Object   |             |
| `callback` | Function |             |


## Installation

Requires [nodejs](http://nodejs.org/).

```sh
$ npm install spritezero
```

## Executable

There is also an executable for bundling and creating your own sprites from a folder of svg's:

```bash
$ npm install -g spritezero
$ spritezero --help
usage: spritezero ./path/to/svgdirectory
option: --json ./path/to/output.json
option: --png ./path/to/output.png
option: --scale 2
```

By default, the output json will be at `sprite@1.json` and the output png will be at `sprite@1.png`. The default scale is `1`.


## Tests

```sh
$ npm test
```

# viktor-nv1-settings-convertor

Utility to help transferring values between ranges used both in the audio engine of the Viktor NV-1 Synth and UI's built for it.

## Install

```shell
$ npm install --save viktor-nv1-settings-convertor
```

## Use

```javascript
var convertor = require( "viktor-nv1-settings-convertor" );
```

## API

#### `convertor.transposeValue( value, originalRange, newRange )`

**Params:**
 * value: `Number`
 * originalRange: `[ Number, Number ]`
 * newRange: `[ Number, Number ]`

**Returns: ** Number

Example:

```javascript
  var value = 0.5;

  console.log( convertor.transposeValue( value, [ 0, 1 ], [ 0, 100 ] ) );
  // prints out: 50
```

#### `convertor.transposeParam( param, newRange )`

**Params:**
 * param: `Object` with this interface `{ value: Number, range: [ Number, Number ] }`
 * newRange: `[ Number, Number ]`

**Returns:** new `Object` with the same structure as the passed param parameter.

Example:

```javascript
  var param = { value: 50, range: [ 0, 100 ] };

  console.log( convertor.transposeParam( param, [ 0, 1 ] ).value );
  // prints out: 0.5
```

#### `convertor.getRangeCenter( range )`

**Params:**
 * range: `[ Number, Number ]`

**Returns:** Number, the center of the range.

Example:

```javascript
  var range = [ 0, 100 ];

  console.log( convertor.getRangeCenter( range ) );
  // prints out: 50
```

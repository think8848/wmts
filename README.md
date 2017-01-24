# WMTS

[![Build Status](https://travis-ci.org/DenisCarriere/wmts.svg?branch=master)](https://travis-ci.org/DenisCarriere/wmts)
[![Coverage Status](https://coveralls.io/repos/github/DenisCarriere/wmts/badge.svg?branch=master)](https://coveralls.io/github/DenisCarriere/wmts?branch=master)
[![npm version](https://badge.fury.io/js/wmts.svg)](https://badge.fury.io/js/wmts)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/DenisCarriere/wmts/master/LICENSE)
<!-- Line Break -->
[![Standard - JavaScript Style Guide](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

> Flexible WMTS scheme for Javascript applications.

## Install

```bash
$ npm install --save wtms
```

## Usage

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### getCapabilities

Get Capabilities

**Parameters**

-   `options` **Options** Options
    -   `options.spaces` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)?** Spaces created for XML output (optional, default `2`)

**Examples**

```javascript
const xml = wmts.getCapabilities({
  url: 'http://localhost:5000/WMTS',
  title: 'Tile Service XYZ',
  identifier: 'service-123',
  abstract: '© OSM data',
  keyword: ['world', 'imagery', 'wmts'],
  format: 'png',
  minzoom: 10,
  maxzoom: 18,
  bbox: [-180, -85, 180, 85]
})
```

Returns **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** XML string

### Capabilities

Capabilities JSON scheme

**Parameters**

-   `options` **Options** Options
    -   `options.url` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** <required>

**Examples**

```javascript
Capabilities({
  url: 'http://localhost:5000'
})
```

Returns **ElementCompact** JSON scheme

### GoogleMapsCompatible

GoogleMapsCompatible JSON scheme

**Parameters**

-   `minzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Minimum zoom level
-   `maxzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Maximum zoom level

**Examples**

```javascript
wmts.GoogleMapsCompatible(10, 17)
```

Returns **ElementCompact** JSON scheme

### TileMatrix

TileMatrix JSON scheme

**Parameters**

-   `minzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Minimum zoom level
-   `maxzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Maximum zoom level

**Examples**

```javascript
wmts.TileMatrix(0, 18)
```

Returns **ElementCompact** JSON scheme

### ServiceIdentification

ServiceIdentification JSON scheme

**Parameters**

-   `options` **Options** Options
    -   `options.title` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** [required] Title
    -   `options.abstract` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Abstract
    -   `options.keywords` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)>** Keywords
    -   `options.accessConstraints` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Access Constraints
    -   `options.fees` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Fees

**Examples**

```javascript
ServiceIdentification({
  title: 'Service name',
  abstract: 'A long description of this service',
  keywords: ['world', 'wmts', 'imagery']
})
```

Returns **ElementCompact** JSON scheme

### Keywords

Keywords JSON scheme

**Parameters**

-   `keywords` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)>?= \[]** 

**Examples**

```javascript
Keywords(['world', 'imagery', 'wmts'])
```

Returns **ElementCompact** JSON scheme

### OperationsMetadata

OperationsMetadata JSON scheme

**Parameters**

-   `url` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URL of Service Provider

**Examples**

```javascript
OperationsMetadata('http://localhost:5000/wmts')
```

Returns **ElementCompact** JSON scheme

### Operation

Operation JSON scheme

**Parameters**

-   `uri` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URI of Service Provider
-   `operation`  
-   `restful`  
-   `kvp`  

**Examples**

```javascript
Operation()
```

Returns **ElementCompact** JSON scheme

### Get

Get JSON scheme

**Parameters**

-   `uri` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URI of Service Provider
-   `value` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Type of Get

**Examples**

```javascript
Get()
//= Get > Constraint > AllowedValues> Value
```

Returns **ElementCompact** JSON scheme

### Contents

Capabilities.Contents JSON scheme

**Parameters**

-   `options` **Options** Options
-   `title` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Title of Service
-   `uri` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URI of Service Provider

**Examples**

```javascript
Contents()
//= Contents > [Layer, TileMatrixSet, TileMatrixSet]
```

Returns **[Element](https://developer.mozilla.org/en-US/docs/Web/API/Element)** 

### Layer

Capabilities.Contents.Layer JSON scheme

**Parameters**

-   `options` **Options** Options
    -   `options.title` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** [required] Title
    -   `options.url` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** [required] URL
    -   `options.format` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** [required] Format 'png' | 'jpeg' | 'jpg'
    -   `options.abstract` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Abstract
    -   `options.identifier` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Identifier
    -   `options.bbox` **BBox** BBox [west, south, east, north]

**Examples**

```javascript
Layer({
  title: 'Tile Service'
  url: 'http://localhost:5000/wmts'
  format: 'jpg'
})
```

Returns **ElementCompact** JSON scheme

## License

MIT © [Denis Carriere](https://twitter.com/DenisCarriere)
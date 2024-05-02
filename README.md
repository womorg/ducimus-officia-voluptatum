# @womorg/ducimus-officia-voluptatum <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Define a data property on an object. Will fall back to assignment in an engine without descriptors.

The three `non*` argument can also be passed `null`, which will use the existing state if available.

The `loose` argument will mean that if you attempt to set a non-normal data property, in an environment without descriptor support, it will fall back to normal assignment.

## Usage

```javascript
var defineDataProperty = require('@womorg/ducimus-officia-voluptatum');
var assert = require('assert');

var obj = {};
defineDataProperty(obj, 'key', 'value');
defineDataProperty(
	obj,
	'key2',
	'value',
	true, // nonEnumerable, optional
	false, // nonWritable, optional
	true, // nonConfigurable, optional
	false // loose, optional
);

assert.deepEqual(
	Object.getOwnPropertyDescriptors(obj),
	{
		key: {
			configurable: true,
			enumerable: true,
			value: 'value',
			writable: true,
		},
		key2: {
			configurable: false,
			enumerable: false,
			value: 'value',
			writable: true,
		},
	}
);
```

[package-url]: https://npmjs.org/package/@womorg/ducimus-officia-voluptatum
[npm-version-svg]: https://versionbadg.es/ljharb/@womorg/ducimus-officia-voluptatum.svg
[deps-svg]: https://david-dm.org/ljharb/@womorg/ducimus-officia-voluptatum.svg
[deps-url]: https://david-dm.org/ljharb/@womorg/ducimus-officia-voluptatum
[dev-deps-svg]: https://david-dm.org/ljharb/@womorg/ducimus-officia-voluptatum/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@womorg/ducimus-officia-voluptatum#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@womorg/ducimus-officia-voluptatum.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@womorg/ducimus-officia-voluptatum.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@womorg/ducimus-officia-voluptatum.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@womorg/ducimus-officia-voluptatum
[codecov-image]: https://codecov.io/gh/ljharb/@womorg/ducimus-officia-voluptatum/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@womorg/ducimus-officia-voluptatum/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@womorg/ducimus-officia-voluptatum
[actions-url]: https://github.com/womorg/ducimus-officia-voluptatum/actions

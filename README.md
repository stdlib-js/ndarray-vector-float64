<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Float64Vector

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Create a double-precision floating-point vector (i.e., a one-dimensional [ndarray][@stdlib/ndarray/ctor]).

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
Float64Vector = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-vector-float64@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var Float64Vector = require( 'path/to/vendor/umd/ndarray-vector-float64/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-vector-float64@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.Float64Vector;
})();
</script>
```

#### Float64Vector( \[options] )

Returns a one-dimensional double-precision floating-point [ndarray][@stdlib/ndarray/ctor].

```javascript
var numel = require( '@stdlib/ndarray-numel' );

var arr = new Float64Vector();
// returns <ndarray>

var len = numel( arr );
// returns 0
```

The function accepts the following options:

-   **order**: specifies whether an [ndarray][@stdlib/ndarray/ctor] is `'row-major'` (C-style) or `'column-major'` (Fortran-style). Default: `'row-major'`.
-   **mode**: specifies how to handle indices which exceed array dimensions (see [`ndarray`][@stdlib/ndarray/ctor]). Default: `'throw'`.
-   **readonly**: boolean indicating whether an array should be **read-only**. Default: `false`.

#### Float64Vector( length\[, options] )

Returns a one-dimensional double-precision floating-point [ndarray][@stdlib/ndarray/ctor] having a specified `length`.

```javascript
var numel = require( '@stdlib/ndarray-numel' );

var arr = new Float64Vector( 5 );
// returns <ndarray>

var len1 = numel( arr );
// returns 5
```

#### Float64Vector( obj\[, options] )

Creates a one-dimensional double-precision floating-point [ndarray][@stdlib/ndarray/ctor] from an array-like object or iterable.

```javascript
var numel = require( '@stdlib/ndarray-numel' );

var arr = new Float64Vector( [ 1.0, 2.0, 3.0 ] );
// returns <ndarray>

var len1 = numel( arr );
// returns 3
```

#### Float64Vector( buffer\[, byteOffset\[, length]]\[, options] )

Returns a one-dimensional double-precision floating-point [ndarray][@stdlib/ndarray/ctor] view of an [`ArrayBuffer`][@stdlib/array/buffer].

```javascript
var ArrayBuffer = require( '@stdlib/array-buffer' );
var numel = require( '@stdlib/ndarray-numel' );

var buf = new ArrayBuffer( 64 );

var arr1 = new Float64Vector( buf );
// returns <ndarray>

var len1 = numel( arr1 );
// returns 8

var arr2 = new Float64Vector( buf, 16 );
// returns <ndarray>

var len2 = numel( arr2 );
// returns 6

var arr3 = new Float64Vector( buf, 16, 1 );
// returns <ndarray>

var len3 = numel( arr3 );
// returns 1
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/blas-ext-sum@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-map@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-vector-float64@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Create a vector containing random values:
var x = new Float64Vector( discreteUniform( 10, 0, 100 ) );

// Compute the sum:
var v = sum( x );
console.log( v.get() );

// Define a function which applies a threshold to individual values:
function threshold( v ) {
    return ( v > 10 ) ? v : 0;
}

// Apply threshold:
var y = map( x, threshold );

// Recompute the sum:
v = sum( y );
console.log( v.get() );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-vector-float64.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-vector-float64

[test-image]: https://github.com/stdlib-js/ndarray-vector-float64/actions/workflows/test.yml/badge.svg?branch=v0.1.0
[test-url]: https://github.com/stdlib-js/ndarray-vector-float64/actions/workflows/test.yml?query=branch:v0.1.0

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-vector-float64/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-vector-float64?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-vector-float64.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-vector-float64/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-vector-float64/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-vector-float64/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-vector-float64/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-vector-float64/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-vector-float64/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-vector-float64/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-vector-float64/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-vector-float64/main/LICENSE

[@stdlib/array/buffer]: https://github.com/stdlib-js/array-buffer/tree/umd

[@stdlib/ndarray/ctor]: https://github.com/stdlib-js/ndarray-ctor/tree/umd

</section>

<!-- /.links -->

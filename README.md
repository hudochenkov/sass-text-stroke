# Text stroke for Sass

<a href="https://www.npmjs.com/package/sass-text-stroke/">![npm package](https://img.shields.io/npm/v/sass-text-stroke?style=flat-square)</a>

[Status of browser support for native CSS text-stroke property.](https://caniuse.com/#feat=text-stroke)

Text stroke polyfill for Sass. You can see why it's better than solutions presented earlier.

![Comparison screenshot](https://rawgit.com/hudochenkov/sass-text-stroke/master/example.png)

[CodePen with example](http://codepen.io/hudochenkov/pen/RPKBoO?editors=110).

[CodePen with example of bad solution](http://codepen.io/hudochenkov/pen/yNgqVg?editors=110).

[CodePen with explanation how it work](http://codepen.io/hudochenkov/pen/BNpxMr?editors=110). Instead of text-shadow for all pixels, function returns only needed text-shadows.


## Tip
This polyfill applies the stroke to the _outside_ of the text compared to native `-webkit-text-stroke` which applies it to the _inside_,
so this polyfill may still be interesting for you even after `-webkit-text-stroke` has become supported by all browsers.


## Usage

````
$ yarn add --dev sass-text-stroke
# or for npm
$ npm install --save-dev sass-text-stroke
````

```scss
// For eyeglass import:
@import "text-stroke";

// ...or for webpack import:
@import "~sass-text-stroke/_text-stroke";


$size: 5;
$color: #bada55;
$correction: 0;

h1 {
    @include text-stroke($size, $color, $correction);
}
p {
    @include text-stroke(4, #369);
}
span {
    text-shadow: text-stroke(4, #369);
}
```

## Options

#### size

Size in pixels (without units).

_Default: **2**_

#### color

Any CSS color.

_Default: **#fff**_

#### correction

Corrects rounding and reduces text-shadows.  For better understanding see [this CodePen](http://codepen.io/hudochenkov/pen/BNpxMr?editors=110).

_Default: **0**_

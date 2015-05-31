# Text stroke for Sass

Text stroke polyfill for Sass. You can see why it's better than solutions presented earlier.

![Comparison screenshot](https://rawgit.com/hudochenkov/sass-text-stroke/master/example.png)

[CodePen with example](http://codepen.io/hudochenkov/pen/RPKBoO?editors=110).

[CodePen with example of bad solution](http://codepen.io/hudochenkov/pen/yNgqVg?editors=110).

[CodePen with explanation how it work](http://codepen.io/hudochenkov/pen/BNpxMr?editors=110). Instead of text-shadow for all pixels, function returns only needed text-shadows.

## Usage

```scss
@import "text-stroke";

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

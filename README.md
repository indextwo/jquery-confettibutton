jQuery Confetti Button
============================

Ever wanted to add some luminosity to your links? Brashness to your buttons? _Clinquant_ to your CTA? Or some glitz & glamour 
to anything else, for that matter? Then you need to get you some **CONFETTI**.

**Confetti Button** is a teeny little (1.02kb minified) plugin that you can call against any DOM element (although smaller things 
like buttons & image containers tend to work best) to instantly add a fizzy flume of confetti.

### Prerequisites

At a minimum, **Confetti Button** requires jQuery 1.6.0 to be included, and the accompanying CSS stylesheet to be included within 
your page:

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
<script src="jquery.vnm.confettiButton.min.js"></script>
<link rel="stylesheet" href="jquery.vnm.confettiButton.css" type="text/css" media="screen" />
```
   

The CSS defines the basics of the confetti and the transitions. It can be modified to adjust the default size & shape of the 
confetti, position of the container, etc. 

## Usage

It's as simple as:

```js
$('.button').confettiButton();
```

Does it have to be a button though? **NOPE**. It can be applied to any DOM element that is a containing element; so you can 
use it on a button, `div`, `a`, `label` or anything else that can contain other elements. The only things you can't immediately 
use it on (without some extra markup, at least) are non-containing or self-closing elements. These include `img`, `input`, 
`hr`, `br` and `embed`.

If you want to use **Confetti Button** on a self-closing element, I recommend wrapping it in a containing element (like a `div`) 
and applying `$.confettiButton()` to that. 

## Parameters

 * `num` _(int)_ The number of confetti bits to generate. Defaults to `60`.
 * `colorArray` _(array)_ Array of background-color values to use. Accepts any CSS-valid value, and they can be mixed. Defaults to `['#FF5566', '#FFFFFF', '#F1C40F', '#2EBFF6', '#2ECC71']`.
 * `minX` _(int)_ The minimum distance, in pixels, of travel on the x-axis for any piece of confetti. As long as this value resolves to a real number (e.g. `$('.element').offset().top`), it will be accepted. Defaults to `5`.
 * `minY` _(int)_ The minimum distance, in pixels, of travel on the y-axis for any piece of confetti. As long as this value resolves to a real number, it will be accepted. Defaults to `5`.
 * `maxX` _(int)_ The maximum distance, in pixels, of travel on the x-axis for any piece of confetti. As long as this value resolves to a real number, it will be accepted. Defaults to `120`.
 * `maxY` _(int)_ The maxmimum distance, in pixels, of travel on the y-axis for any piece of confetti. As long as this value resolves to a real number, it will be accepted. Defaults to `120`.
 * `speed` _(float)_ The base speed of travel for confetti. The speed of any individual piece is calculated randomly with this value as a basis; so, the higher the number, the slower the rate of travel. Defaults to `1`.
 * `rotation` _(bool)_ Whether the pieces will be randomly rotated. Assuming they are square, the rotation is anywhere from 0-90°. Defaults to `true`.
 * `hoverOnly` _(bool)_ Whether the confetti will only appear on a hover event. Defaults to `false`.

## Notes

 As **Confetti Button** is predominantly CSS-based, you can control a lot of how it works simply by modifying the CSS. For 
 example, by default the confetti bits are square. To make them round, you just add:

```css
.vnm-confetti .confetto {
	border-radius: 50%;
}
```

You can also easily adjust the base size; change colour on hover events; change the position of the container so that it 
plumes out of the top of the element instead of the middle... experiment with it and see what you can come up with! 

## Examples

### Confetti only on hover:

```js
$('.button').confettiButton({
	hoverOnly: true
});
```

### Semi-opaque confetti:

```js
$('.button').confettiButton({
	colorArray: ['rgba(0, 0, 0, 0.3)', 'rgba(255, 255, 255, 0.3)'],
});
```

The `colorArray` parameter will accept any valid CSS `background-color` values, including RGBA. 

### Large confetti

```js
$('.button').confettiButton({
	minScale: 200,
	maxScale: 400
});
```

### Slow confetti

```js
$('.button').confettiButton({
	speed: 6
});
```
You can view working demos on [Confetti Button's GitHub page](https://indextwo.github.io/jquery-confettibutton/)
 
 ## Authors

* [Lawrie Malen](https://github.com/indextwo) at [Very New Media&trade;](http://www.verynewmedia.com)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

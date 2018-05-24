DojoJS
====

This library is a 2D Game Development Engine for browser based game development. The main file, dojo.js, contains everything you need to develop a game, such as canvas creation, drawing, frames per second setting, and more. Alternatively, you can use dojo.min.js, wich is not very legible, but the difference is that all unnecessary whitespaces and comments are removed. This does not include the info comment and copyright comment at the top.

Tricks
----

The following below has some neat tricks you can use to minimize how much space your file uses, and increase the legibility!

### Trick 1: Set the background

In a canvas, it may seem that all you can do to set the background is set a specific color, and draw a rectangle. This can be very frustrating if you don't seem to be able to quite remember width, height, or translations. All you need to do is use one of the lines of code below and you will be on your way to not having to explain everything you do!

```javascript
function draw() {
  $.background(0); // Draws a background with a gray scale value of 0.
  
  $.background(0, 127); // Draws a background with a gray scale value of 0 and an alpha value of 127 [0-255].
  
  $.background(255, 0, 255); // Draws a background as a color, using one of the two color modes (RGB, HSB).
  
  $.background(255, 0, 255, 180); // Draws a background as a color, with an alpha value of 180 [0-255].
}
```

The best part of this is that you can set a color before, and it won't effect the background! The background color also won't affect the drawing of future objects!

### Trick 2: Store colors

In DojoJS, when you set a color with `color(args)`, DojoJS stores the color in a color object. To create and manipulate one is as easy at it could possibly be!

```javascript
let myColor = new Color(255, 127, 0, 60); // rgba format

let red = myColor.red;
let green = myColor.green;
let blue = myColor.blue;
let alpha = myColor.alpha;

red = 0; // Does not affect the myColor variable.

myColor.red = red; // Affects the myColor variable's red value.
```

In case you were wondering, to use an HSB color code set, you can use this code.
>Fun Fact: HSB stands for Hue, Saturation, and Brightness. Alpha stays the same. This mode can be used for examples were you want bright, festive colors, and not just have random RGB color values.

```javascript
let hsbColor = new HSBColor(0, 255, 255, 160); // Same as RGBA format: 255, 0, 0, 160 or bright red.

let hue = hsbColor.colorCode;
let saturation = hsbColor.saturation;
let brightness = hsbColor.brightValue;
let alpha = hsbColor.alpha;

saturation = 170; // Again, does not affect myColor's saturation value.

hsbColor.saturation = saturation; // Does, in fact, affect the color's saturation value.
```

You also don't need to worry about color conversions. You can use `RGBtoHSB()` or `HSBtoRGB()`, no prefix needed, with three or four parameters for no alpha vs alpha respectively.

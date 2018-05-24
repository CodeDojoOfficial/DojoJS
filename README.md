# DojoJS
This is the official holding place of the DojoJS JavaScript library and addons. This library is protected under the MIT License. If you wish to use it for things like a custom IDE for you to use and you alone, it is fine. Publicly, just be sure you let your customers know that you did not develop DojoJS.

## Info
**Version:** 0.0.1
**Addons:** There are currently no addons.
**Availability:** Download not required.
**Copyright:** Copyright © 2018 by CodeDojo and/or it's individual developers. All rights reserved.
**License:** MIT License

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
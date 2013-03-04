# dot-colors

Author: Robert Ginda <rginda@google.com>

Port to Node.js: Mike Acton <macton@gmail.com>

The bulk of this file is color palettes.  The rest is a few simple utility functions

- [Install][#install]
- [Questions?][#questions]
- [Contribute?][#contribute]
- [API][#api]

## Install

### node
For [node](http://nodejs.org) with [npm](http://npmjs.org):

```bash
npm install dot-colors
```

And use with `var colors = require("dot-colors")`

## Questions?

If you have questions, the best place to ask is the [chromium-hterm google group](https://groups.google.com/a/chromium.org/forum/?fromgroups=#!forum/chromium-hterm)

## Contribute?

If you want to contribute to the upstream, the best place to ask is the [chromium-hterm google group](https://groups.google.com/a/chromium.org/forum/?fromgroups=#!forum/chromium-hterm)

If you would like to contribute to this port, I have some things in mind:
* Merge in some of the functionality of [colors](https://github.com/harthur/color)
* Figure out a (good) way to automate the generation of this readme file.
* Make some tests.
* Add examples to this readme in the API section.


## API
- [rgbToX11](#rgbtox11)
- [x11ToCSS](#x11tocss)
- [hexToRGB](#hextorgb)
- [rgbToHex](#rgbtohex)
- [normalizeCSS](#normalizecss)
- [arrayToRGBA](#arraytorgba)
- [setAlpha](#setalpha)
- [mix](#mix)
- [crackRGB](#crackrgb)
- [nameToRGB](#nametorgb)
- [stockColorPalette](#stockcolorpalette)

## rgbToX11

### Synopsis

    colors   = require('dot-colors');
    x11Value = colors.rgbToX11( rgbValue );

### Description

Convert a CSS rgb(ddd,ddd,ddd) color value into an X11 color value.
Other CSS color values are ignored to ensure sanitary data handling.
Each 'ddd' component is a one byte value specified in decimal.

### Return Value

The X11 color value or null if the value could not be converted.


<sub><sup>([Return to API)](#api)</sup></sub>


## x11ToCSS

### Synopsis

    colors   = require('dot-colors');
    cssValue = colors.x11ToCSS( x11Value );

### Description

Convert an X11 color value into an CSS rgb(...) color value.

The X11 value may be an X11 color name, or an RGB value of the form
rgb:hhhh/hhhh/hhhh.  If a component value is less than 4 digits it is
padded out to 4, then scaled down to fit in a single byte.

### Return Value

The CSS color value or null if the value could not be converted.


<sub><sup>([Return to API)](#api)</sup></sub>


## hexToRGB

### Synopsis

    colors   = require('dot-colors');
    rgbValue = colors.hexToRGB( hexValue );

### Description

Converts one or more CSS '#RRGGBB' color values into their rgb(...) form.

Arrays are converted in place. If a value cannot be converted, it is replaced 
with null.

### Return Value

The converted value or values.


<sub><sup>([Return to API)](#api)</sup></sub>


## rgbToHex 

### Synopsis

    colors   = require('dot-colors');
    hexValue = colors.rgbToHex( rgbValue );

### Description

Converts one or more CSS rgb(...) forms into their '#RRGGBB' color values.

If given an rgba(...) form, the alpha field is thrown away.

Arrays are converted in place. If a value cannot be converted, it is
replaced with null.

### Return Value

The converted value or values.


<sub><sup>([Return to API)](#api)</sup></sub>


## normalizeCSS

### Synopsis

    colors          = require('dot-colors');
    normalizedValue = colors.normalizeCSS( cssValue );

### Description

Take any valid css color definition and turn it into an rgb or rgba value.

### Return Value

Returns null if the value could not be normalized.


<sub><sup>([Return to API)](#api)</sup></sub>


## arrayToRGBA

### Synopsis

    colors    = require('dot-colors');
    rgbaValue = colors.template( arrayValueValue );

### Description

Convert a 3 or 4 element array into an rgba(...) string.

### Return Value


<sub><sup>([Return to API)](#api)</sup></sub>


## setAlpha

### Synopsis

    colors    = require('dot-colors');
    rgbaValue = colors.setAlpha( rgbValue );

### Description

Overwrite the alpha channel of an rgb/rgba color.

### Return Value


<sub><sup>([Return to API)](#api)</sup></sub>


## mix

### Synopsis

    colors      = require('dot-colors');
    resultColor = colors.template( base, tint, percent );

### Description

Mix a percentage of a tint color into a base color.

### Return Value


<sub><sup>([Return to API)](#api)</sup></sub>


## crackRGB

### Synopsis

    colors    = require('dot-colors');
    rgbaValue = colors.crackRGB( colorValue );

### Description

Split an rgb/rgba color into an array of its components.

On success, a 4 element array will be returned.  For rgb values, the alpha
will be set to 1.

### Return Value


<sub><sup>([Return to API)](#api)</sup></sub>


## nameToRGB

### Synopsis

    colors   = require('dot-colors');
    rgbColor = colors.nameToRGB( colorName );

### Description

Convert an X11 color name into a CSS rgb(...) value.

Names are stripped of spaces and converted to lowercase.  If the name is
unknown, null is returned.

This list of color name to RGB mapping is derived from the stock X11
rgb.txt file.

### Return Value

The corresponding CSS rgb(...) value.


<sub><sup>([Return to API)](#api)</sup></sub>


## stockColorPalette

### Synopsis

    colors   = require('dot-colors');
    palette  = colors.stockColorPalette;

### Description

The stock color palette. in RGB form.

### Return Value

Array of 256 colors, in this order:

* The "ANSI 16"
* The 6x6 color cubes
* The greyscale ramp

<sub><sup>([Return to API)](#api)</sup></sub>


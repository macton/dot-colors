dot-colors
==========

API
---
- [rgbToX11](#rgbToX11)
- [x11ToCSS](#x11ToCSS)
- [hexToRGB](#hexToRGB)
- [rgbToHex](#rgbToHex)
- [normalizeCSS](#normalizeCSS)
- [arrayToRGBA](#arrayToRGBA)
- [setAlpha](#setAlpha)
- [mix](#mix)
- [crackRGB](#crackRGB)
- [nameToRGB](#nameToRGB)
- [stockColorPalette](#stockColorPalette)

# rgbToX11

Synopsis
--------

colors   = require('dot-colors');
x11Value = colors.rgbToX11( rgbValue );

Description
-----------

Convert a CSS rgb(ddd,ddd,ddd) color value into an X11 color value.
Other CSS color values are ignored to ensure sanitary data handling.
Each 'ddd' component is a one byte value specified in decimal.

Return Value
-----------

The X11 color value or null if the value could not be converted.

# x11ToCSS

Synopsis
--------

colors   = require('dot-colors');
cssValue = colors.x11ToCSS( x11Value );

Description
-----------

Convert an X11 color value into an CSS rgb(...) color value.

The X11 value may be an X11 color name, or an RGB value of the form
rgb:hhhh/hhhh/hhhh.  If a component value is less than 4 digits it is
padded out to 4, then scaled down to fit in a single byte.

Return Value
-----------

The CSS color value or null if the value could not be converted.

# hexToRGB

Synopsis
--------

colors   = require('dot-colors');
rgbValue = colors.hexToRGB( hexValue );

Description
-----------

Converts one or more CSS '#RRGGBB' color values into their rgb(...) form.

Arrays are converted in place. If a value cannot be converted, it is replaced 
with null.

Return Value
-----------

The converted value or values.

# rgbToHex 

Synopsis
--------

colors   = require('dot-colors');
hexValue = colors.rgbToHex( rgbValue );

Description
-----------

Converts one or more CSS rgb(...) forms into their '#RRGGBB' color values.

If given an rgba(...) form, the alpha field is thrown away.

Arrays are converted in place. If a value cannot be converted, it is
replaced with null.

Return Value
-----------

The converted value or values.

# normalizeCSS

Synopsis
--------

colors          = require('dot-colors');
normalizedValue = colors.normalizeCSS( cssValue );

Description
-----------

Take any valid css color definition and turn it into an rgb or rgba value.

Return Value
-----------

Returns null if the value could not be normalized.

# arrayToRGBA

Synopsis
--------

colors    = require('dot-colors');
rgbaValue = colors.template( arrayValueValue );

Description
-----------
Convert a 3 or 4 element array into an rgba(...) string.

Return Value
-----------

# setAlpha

Synopsis
--------

colors    = require('dot-colors');
rgbaValue = colors.setAlpha( rgbValue );

Description
-----------

Overwrite the alpha channel of an rgb/rgba color.

Return Value
-----------

# mix

Synopsis
--------

colors      = require('dot-colors');
resultColor = colors.template( base, tint, percent );

Description
-----------

Mix a percentage of a tint color into a base color.

Return Value
-----------

# crackRGB

Synopsis
--------

colors    = require('dot-colors');
rgbaValue = colors.crackRGB( colorValue );

Description
-----------

Split an rgb/rgba color into an array of its components.

On success, a 4 element array will be returned.  For rgb values, the alpha
will be set to 1.

Return Value
-----------

# nameToRGB

Synopsis
--------

colors   = require('dot-colors');
rgbColor = colors.nameToRGB( colorName );

Description
-----------

Convert an X11 color name into a CSS rgb(...) value.

Names are stripped of spaces and converted to lowercase.  If the name is
unknown, null is returned.

This list of color name to RGB mapping is derived from the stock X11
rgb.txt file.

Return Value
-----------

The corresponding CSS rgb(...) value.

# stockColorPalette

Synopsis
--------

colors   = require('dot-colors');
palette  = colors.stockColorPalette;

Description
-----------
The stock color palette. in RGB form.

Return Value
-----------
Array of 256 colors, in this order:
1. The "ANSI 16"
2. The 6x6 color cubes
3. The greyscale ramp

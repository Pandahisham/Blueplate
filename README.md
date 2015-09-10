# Blueplate
A lightweight, responsive CSS layout engine and SASS mixin library.

## Table of Contents

* [Getting Started](#getting-started)
* [SASS Implementation](#sass-implementation)
   * [Animation](#animation)
   * [Arrow](#arrow)
   * [Background](#background)
   * [Background Images](#background-images)
   * [Borders](#borders)
   * [Border Radius](#border-radius)
   * [Border Shades](#border-shades)
   * [Display](#display)
   * [Drop Shadow](#drop-shadow)
   * [Global Setup](#global-setup)
   * [Gradient](#gradient)
   * [iOS](#ios)
   * [Layout](#layout)
   * [Layout Floats](#layout-floats)
   * [Layout Responsive](#layout-responsive)
* [CSS Implementation](#css-implementation)
   * [Background](#background-1)
   * [Display](#display-1)
   * [Layout](#layout-1)
   * [Position](#position)
   * [Sizing](#sizing)
   * [Spacing](#spacing)
   * [Text](#text)
* [Mixins](#mixins)

## Getting Started
You can either download a copy of the source files or install Blueplate via Bower.

```
bower install blueplate
```

## SASS Implementation
Start by importing the necessary file into your own SASS file and include the required mixins.

**SASS**
```
@import "sass/import";

.example {
   @include row();
}
.left, .middle, .right {
   @include span(12); // 100% width
}
@include breakpoint(large) {
   .left {
      @include span-new(6); // 50% width
   }
   .middle {
      @include span-new(4); // 33.33% width
   }
   .right {
      @include span-new(2); // 16.66% width
   }
}
```

**HTML**
```
<div class="example">
   <div class="left"></div>
   <div class="middle"></div>
   <div class="right"></div>
</div>
```

Find the other available mixins below:

### Animation
##### animate($attribute, $transition-speed: 0.2s)
Set the transition animation style of $attribute with all the neccessary prefixes for all the browser types.

### Arrow
##### arrow($position: bottom, $colour: $red, $size: 20px)
Attach a CSS arrow to an element via the after pseudo element.

##### arrow-colour($position: bottom, $colour: $white)
Change the colour of an elements CSS arrow. Note that the arrow position is required.

##### arrow-no($colour: $white)
Remove an elements CSS arrow and reset the background colour. Note that the background colour is required.

### Background

##### background-attachment($attachment: scroll)
Set the background attachment property to $attachment.

##### background-clip($clip: border-box)
Set the background clip property to $clip.

##### background-colour($colour: grey)
Set the background colour to $colour.

##### background-contain()
Set the background size to contain, the position to center and stop it from repeating.

##### background-cover()
Set the background size to cover, the position to center and stop it from repeating.

##### background-origin($origin: padding-box)
Set the background origin property to $origin.

##### background-position($position: center)
Set the background position property to $position.

##### background-repeat($repeat: repeat)
Set the background repeat property to $repeat.

##### background-size($size: auto)
Set the background size property to $size.

##### background-single()
Set the background position to center and stop it from repeating.

### Background Images
**Note** that all the image urls already include the relative image path as per $images-root settings variable.

##### background-image($image-url, $position: center)
Set the background image URL of an element with an optional position property.

##### background-image-contain($image-url, $position: center)
Set the background image URL to be contained within the element with an optional position property.

##### background-image-cover($image-url, $position: center)
Set the background image URL to cover the element with an optional position property.

##### background-image-parallax($image-url)
Set the background image URL of an element with a fixed position property. Used mainly for a parallax style effect.

##### background-image-single($image-url, $position: center)
Set the background image URL of an element with no-repeat and an optional position property.

### Borders

##### border($colour: grey, $size: 1px, $type: solid)
Set the border property of an element.

##### border-top($colour: grey, $size: 1px, $type: solid)
Set the border top property of an element.

##### border-right($colour: grey, $size: 1px, $type: solid)
Set the border right property of an element.

##### border-bottom($colour: grey, $size: 1px, $type: solid)
Set the border bottom property pf an element.

##### border-left($colour: grey, $size: 1px, $type: solid)
Set the border left property of an element.

##### border-horizontal($colour: grey, $size: 1px, $type: solid)
Set the border left and border right property of an element.

##### border-vertical($colour: grey, $size: 1px, $type: solid)
Set the border top and border bottom property of an element.

##### border-no()
Remove all borders from an element.

### Border Radius

##### border-radius($radius: 2px)
Set the border radius property around an element with all the neccessary prefixes for all the browser types.

##### border-radius-top($radius: 2px)
Set the top border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-right($radius: 2px)
Set the right border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-bottom($radius: 2px)
Set the bottom border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-left($radius: 2px)
Set the left border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-top-left($radius: 2px)
Set the top left border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-top-right($radius: 2px)
Set the top right border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-bottom-left($radius: 2px)
Set the bottom left border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-bottom-right($radius: 2px)
Set the bottom right border radius property of an element with all the neccessary prefixes for all the browser types.

##### border-radius-no()
Set the border radius of an element to 0.

### Border Shades

##### border-light($highlight: 0.8, $colour: #fff)
Set a light border all around an element. The border is faded out.

##### border-light-top($highlight: 0.8, $colour: #fff)
Set a light top border on an element. The border is faded out.

##### border-light-right($highlight: 0.8, $colour: #fff)
Set a light right border on an element. The border is faded out.

##### border-light-bottom($highlight: 0.8, $colour: #fff)
Set a light bottom border on an element. The border is faded out.

##### border-light-left($highlight: 0.8, $colour: #fff)
Set a light left border on an element. The border is faded out.

##### border-dark($lowlight: 0.8, $colour: #000)
Set a dark border all around an element. The border is faded out.

##### border-dark-top($lowlight: 0.8, $colour: #000)
Set a dark top border on an element. The border is faded out.

##### border-dark-right($lowlight: 0.8, $colour: #000)
Set a dark right border on an element. The border is faded out.

##### border-dark-bottom($lowlight: 0.8, $colour: #000)
Set a dark bottom border on an element. The border is faded out.

##### border-dark-left($lowlight: 0.8, $colour: #000)
Set a dark left border on an element. The border is faded out.

### Display

##### hide()
Hide an element.

##### hide-visually()
Hide an element but still make it accessible to the DOM. Used for instances where accessibility is needed.

##### show($type: block)
Show an element with an optional display type.

##### opacity($opacity: 0.60)
Set the opacity of an element.

##### overflow($overflow: visible)
Set the overflow of an element.

##### transparency($transparency: 0.60)
Set the transparency of an element. You can also use the opacity mixin as an alternative.

### Drop Shadow

##### drop-shadow($color: fade-out(#000, 0.6), $size: 3px, $vertical-offset: 0px, $horizontal-offset: 0px)
Set the drop shadow of an element with options for colour, size, vertical and horizontal offsets.

##### drop-shadow-inset($color: fade-out(#000, 0.6), $size: 3px, $vertical-offset: 0px, $horizontal-offset: 0px)
Set an inset drop shadow of an element with options for colour, size, vertical and horizontal offsets.

##### drop-shadow-no()
Remove any drop shadow from an element.

### Global Setup

##### global-setup()
Apply the border-box property to all elements to contain dimensions. Set the default colour to a lighter, more readable black, the background colour to white and the default font to Open Sans with an Arial and Helvetica fallback. Note that this setup is automatically called by Webplate already.

### Gradient

##### gradient-horizontal($left-colour, $right-colour)
Apply a linear gradient to the background with the appropriate left to right colours.

##### gradient-vertical($top-colour, $bottom-colour)
Apply a linear gradient to the background with the appropriate top to bottom colours.

### iOS

##### ios-render()
Set some special properties like Webkit's backface visibility and perspective property to help with rendering elements like images.

### Layout

##### box-sizing($option: content-box)
Set the box sizing style of an element with all the neccessary prefixes for all the browser types.

##### center()
Center an element within its container.

##### center-vertical()
Center an element vertically within its container.

##### clearfix()
Clear the zoom and set the clear style to both for the element. No elements will be allowed to float to the left and right of this element.

##### level($index: 1)
Set the z-index of an element to $index. You can also use the z-index mixin as an alternative.

##### vertical-align($align)
Set the vertical alignment of an element to $align.

##### z-index($index: 1)
Set the z-index of an element to $index.

### Layout Floats

##### float($float)
Set the float of an element to $float.

##### float-clear()
Clear the float of an element.

##### float-no()
Clear the float of an element.

### Layout Responsive

##### limit()
Assigns a maximum width to an element based on the $limit-width variable and centers it. Once the screen size is below the limit the element will become fluid and adjust its width to a 100%. Used mainly to contain row elements.

##### offset($x)
If you offset an element then you push it out $x amount of columns from the left (applied to span elements).

##### offset-r($x)
This mixin will push anything to the right of the element by $x amount of columns (applied to span elements).

##### respond-to($x, $y)
A mixin to generate media queries based on the preset Webplate view types or a custom value. The options for $x are large, fluid, small or an em/px value example respond-to(50em). Option $y can be min or max to set the min/max-width of the query.

##### row()
Turns an element into a row which is the basic building block of Blueplate and is needed to wrap any span elements. A row element will default to a 100% width of its container.

##### span($x)
Turns an element into a span which can occupy $x amount of columns within the $column-limit. For example @include span(6) will occupy 6 columns within the default 12 which equates to 50% of a containing row.

##### span-new($x)
Change the span to occupy $x amount of columns within the $column-limit. Apply to already spanned elements.

##### span-reset()
Reset the spanned element to the the $column-limit and remove all offsets.

## CSS Implementation
Start by including the necessary files.

```
<head>
   <link href="css/blueplate.css" rel="stylesheet" type="text/css">
</head>
```

Now class your HTML to manage your layout. For example:

```
<div class="row">
   <div class="span-2">Span 2</div>
   <div class="span-2">Span 2</div>
   <div class="span-2">Span 2</div>
   <div class="span-2">Span 2</div>
   <div class="span-2">Span 2</div>
   <div class="span-2">Span 2</div>
</div>
```

Find the other available classes below:

### Background
Class | Options | Description
---- | ---- | ----
.back-pos-[p] | [p] = t, r, b, l, c | Set the background position of an element to [p] for top, right, bottom, left or center.
.back-repeat-[r] | [r] = no, y, x | Set the background repeat of an element to [r] for no repeating, repeat along y axis or repeat along x axis.
.back-single | | Set the background of an element to not repeat and to be centered.
.back-contain | | Set the background of an element to not repeat and to contain within the element.
.back-cover | | Set the background of an element to not repeat and to cover the element completely.
.back-black | | Set the background colour to black.
.back-grey | | Set the background colour to medium grey.
.back-grey-light | | Set the background colour to light grey.
.back-white | | Set the background colour to white.

### Display
Class | Options | Description
---- | ---- | ----
.hide | | Hide an element.
.hide-large | | Hide an element in large view only.
.hide-small | | Hide an element in small view only.
.show | | Show an element.
.show-large | | Show an element in large view only.
.show-small | | Show an element in small view only.
.transparency-[o] | [o] = 100, 75, 50, 25, 0 | Set the opacity of an element to [o] for 100%, 75%, 50%, 25% or 0%.

### Layout
Class | Options | Description
---- | ---- | ----
.center | | Center an element.
.float-[p] | [p] = l, r | Set the float property of an element to [p] for left or right.
.float-no | | Remove the float property from an element.
.float-clear | | Stop all floating elements from affecting any element following.
.valign-[p] | [p] = t, m, b | Set the vertical alignment of an element to [p] for top, middle or bottom.

### Position
Class | Description
---- | ----
.pos-absolute | Set the position of an element to absolute.
.pos-relative | Set the position of an element to relative.
.pos-static | Set the position of an element to static.
.pos-fixed | Set the position of an element to fixed.

### Sizing
Class | Options | Description
---- | ---- | ----
.block-h-[h] | [h] = 10, 20, 50, 100, 200, 500, 1000 | Set the height of an element to [h] for 10px, 20px, 50px, 100px, 200px, 500px, 1000px.
.block-w-[w] | [w] = 10, 20, 50, 100, 200, 500, 1000 | Set the width of an element to [w] for 10px, 20px, 50px, 100px, 200px, 500px, 1000px.

### Spacing
Class | Options | Description
---- | ---- | ----
.spacing-no | | Remove all padding and margins from an element.
.pad-no | | Remove all padding from an element.
.mgn-no | | Remove all margins from an element.
.pad-[x] | [x] = [integer] | Add [x] amount of padding all around. For example pad-6 will add 6 pixels of padding to the top, right, bottom and left of an element.
.pad-[p]-[x] | [p] = t, r, b, l [x] = [integer] | Add [x] amount of padding to the [p] side of the element for top, right, bottom or left.
.mgn-[x] | [x] = [integer] | Add [x] amount of margin to the top, right, bottom and left of an element.
.mgn-[p]-[x] | [p] = t, r, b, l [x] = [integer] | Add [x] amount of margin to the [p] side of the element for top, right, bottom or left.

### Text
Class | Options | Description
---- | ---- | ----
.hide-text | | Hide the text within an element.
.txt-[a] | [a] = l, c, r | Set the text alignment to [a] for left, center, right.
.txt-size-[s] | [s] = x2s, xs, s, m, n, l, xl, x2l | Set the font size to [s] for extra small, small, medium, normal, large, extra large, extra extra large.
.txt-weight-[w] | [w] = xl, l, n, b, xb | Set the font weight to [b] for extra light, light, normal, bold, extra bold.
.txt-light | | Set the font weight to light.
.txt-bold | | Set the font weight to bold.
.txt-normal | | Set the font weight and style to normal.
.txt-italics | | Set the font style to italics.
.txt-oblique | | Set the font style to oblique.
.txt-white | | Set the font colour to white.
.txt-grey | | Set the font colour to medium grey.

## Author
Created and maintained by Chris Humboldt<br>
Website: <a href="http://chrishumboldt.com/">chrishumboldt.com</a><br>
Twitter: <a href="https://twitter.com/chrishumboldt">twitter.com/chrishumboldt</a><br>
GitHub <a href="https://github.com/chrishumboldt">github.com/chrishumboldt</a><br>

## Copyright and License
Copyright 2015 Webplate Project

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

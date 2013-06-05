# Basic-stylus-grid

A very simple CSS grid system in less than 35 lines of code for [stylus](http://learnboost.github.io/stylus/) with [nib](http://visionmedia.github.io/nib/) extensions.

## Why?

Sometimes simpler is better and you don't need a rich responsive and flexible CSS framework, you just need a plain grid layout and you want to keep your CSS lean, so using a full-fledged system like [twitter bootstrap](http://twitter.github.io/bootstrap/) might be a bit overkill.

You just want those basic CSS layout classes, but aren't in the mood to DIY. Feel free to use these.

## What it does

Gives you the following classes:
- .l-grid
- .l-row
- .l-row.l-compact (for rows without top & bottom margin)
- .l-cell (an .l-row has `gridColumnCount` cells)
- .l-cell.l-span-n (where `n = [2..gridColumnCount]` when you need cells spanning multiple columns)
- .l-cell.l-offset-n (where `n = [1..(gridColumnCount - 1)]` when you need an offset before a cell)

## Usage

Include `grid.styl` in your stylesheets folder and don't forget to `@import` it in your main `styl` file.
You can optionally configure the following variables:

    gridColumnCount =   6  // defaults to 12
    gridColumnWidth = 120  // defaults to 60
    gridPadding     =  20  // defaults to 20

    @import grid           // import must come after optionally configuring the variables above

If you leave `gridColumnCount`, `gridColumnWidth` and `gridPadding` to their default values, you'll end up with the "classic" 960px grid.

Then, in your HTMLs, you can use the generated classes like this:

    <div class="l-grid">
      <div class="l-row">
        <div class="l-cell">
        <div class="l-cell">
        ...
        <div class="l-cell">
      </div>
      <div class="l-row">
        <div class="l-cell l-offset-3">
        <div class="l-cell l-offset-1 l-span-2">
        ...
        <div class="l-cell">
      </div>
    </div>

Rows can also be nested, like this:

    <div class="l-grid">
      <div class="l-row">
        <div class="l-cell">
        <div class="l-cell">
        ...
        <div class="l-cell">
      </div>
      <div class="l-row">
        <div class="l-cell l-offset-3">
        <div class="l-cell l-offset-1 l-span-2">

          <!-- Nested row -->
          <div class="l-row l-compact">
            <div class="l-cell">Nested cell content 1</div>
            <div class="l-cell">Nested cell content 2</div>
            ...
            <div class="l-cell">
          </div>

        ...
        <div class="l-cell">
      </div>
    </div>

## Note
This is not an npm module.

## Suggestion

Since you're reading this, chances are you might also be interested in [ASPA](https://github.com/icflorescu/aspa), a simple, map-file based asset packager for Node.js, capable of compiling, compressing and preping for deployment a wide array of input sources, which:
- Accepts .css, .styl and .less input for stylesheets;
- Accepts .js, .coffee, .iced ([IcedCoffeeScript](http://maxtaco.github.com/coffee-script/)), .co ([Coco](https://github.com/satyr/coco#readme)) and .ls ([LiveScript](http://livescript.net/)) input for scripts;
- Concatenates multiple script/style source files per output file;
- [Fingerprints](http://guides.rubyonrails.org/asset_pipeline.html#what-is-fingerprinting-and-why-should-i-care) and gzips assets in production mode, while correctly handling image and font file URLs in CSS files.

## License

(The MIT License)

Copyright (c) 2013 Ionut-Cristian Florescu &lt;ionut.florescu@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

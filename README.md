css-standards
=============

Structure
---------
Best practice would be to use LESS/SASS, and to create a series of LESS/SASS files to be imported in one primary LESS/SASS file to be served.
In the absense of using a CSS preprocessor, the order of styles in the CSS should reflect the same order. Each section should be separated by a docblock, if LESS/SASS files are not used.

    sitename.less
    -----------
    /**
    * @sitename.css
    * The complete stylesheet for _property.com_
    *
    * Contains all the styling for the site, including any responsive design tweaks
    */
    
    @import "reset.less";
    @import "colour.less";
    @import "mixins.less";
    @import "font.less";
    @import "screen.less";
    @import "print.less";
    @import "generic.less";

This should then be compiled and minified on development, before being commited and pushed back up through the development cycle. Any Stylesheet inclusions should be for the CSS output file _screen.css_.

Comments
--------
All CSS/LESS/SASS files must start with a docblock structured like the one which follows.

    /**
    * @file
    * Short description describing the file.
    *
    * The first sentence of the long description starts here and continues on this
    * line for a while finally concluding here at the end of this paragraph.
    */

Selectors
---------
* Each selector must be on its own line.
* Brackets start after the last selector and end vertically aligned to the start of the selectors.
* Each declaration should be indented one level relative to its selector.
* Unless absolutely essential, ID and class selectors are not prefaced with block elements, there is usually no need to tie to the DOM as tightly, and the rendering and portability is improved.
* ID Selectors are camelCased.
* Classes are all lowercase, and dash separated.
* Nested selectors are indented by 4 spaces.

Selector usage
--------------
To use an ID, like #gameContainer it must be unique, if an area of content to be styled is likely to not be unique on a page, or the style might be of use more globally, then use a class.
Performance of JavaScript is massively affected by the misuse of classes and ID's - so use them correctly.

Properties
----------
* CSS Properties are ordered alphabetically.
* Shorthand CSS is used where possible.
* Every property, even the last is ended by a semi-colon.
* Every property name ends with a colon, then a space before its value e.g. color: #fff; or font-size: 12px;
* There will only be one CSS property per line
* When hex values are used for colors, use lowercase and, if possible, the shorthand syntax, e.g. #aaa. Colors may be expressed with any valid CSS value, such as hex value, color keyword, rgb() or rgba(). Note that IE8 does not support all color syntaxes and will require a fallback value.
* Quote attribute values in selectors, e.g. input[type="checkbox"].
* Where allowed, avoid specifying units for zero-values, e.g. use margin: 0; instead of margin: 0px;.
* Include a space after each comma in comma-separated property or function values.
* Do not use spaces around the parentheses in a function, e.g. color: rgba(0, 0, 0, 0.8);
* Properties are indented by 4 spaces.
* Don't include spaces after commas within rgb(), rgba(), hsl(), hsla(), or rect()

Examples
--------
    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      border-bottom: 1px solid #333;
      color: #333;
      font-weight: bold;
    }
    
    #menuContainer {
      background: #990000;
      color: #fff;
    }

# Using npm 
```
mkdir sass-demo
cd sass-demo
mkdir -p sass css

```
## Initialize the Project Directory: to create package.json
```

npm init -y

```
## Installing node-sass
```

npm install node-sass --save-dev

```
## Add this script inside the script section of the package.json file.
```
"compile-sass": "node-sass sass/main.scss css/style.css"

"compile-sass-watch": "node-sass sass/main.scss css/style.css --watch"

npm run compile-sass
```


# Using only sass
```
gem install sass
```
compiling 

```
sass style.scss style.css
or in watch window
sass --watch style.scss:style.css

default file name

sass --watch style.scss 

```



# Using compass
``
gem install compass
``


# Syntax of SASS

## creating projects from the command line:
```
compass create sass-test

with paramters
compass create --sass-dir "sass" --css-dir "css" --javascripts-dir "js" --images-dir "img"
```
run the project
```
compass watch
```

# SASS Syntax

```
#main
  color: blue
  font-size: 18pt
  a
    font:
      weight: bold
      family: serif
  &:hover
    background-color: #eee

```
# SCSS Syntax

```
#main {
  color: blue;
  font-size: 18pt;
  a {
    font: {
      weight: bold;
      family: serif;
    }
    &:hover {
      background-color: #eee;
    }
  }
}


```
# css Syntax

```
#main {
  color: blue;
  font-size: 18pt;
}
/* line 4, ../sass/ie.scss */
#main a {
  font-weight: bold;
  font-family: serif;
}
/* line 9, ../sass/ie.scss */
#main a:hover {
  background-color: #eee;
}


```

```
variables

arithmetic operators: + - * / %

computed property values

interpolation for computed selectors, property names and property values

additional functions beyond those in CSS

directives
control: @if, @else if, @else, @for, @each, @while
mixin: @mixin, @include
other: @debug, @warn, @function

```


## Use the parent selector to create forks

```
Before

.button {
  height: 25px;
}
.touch .button {
  height: 44px;
}
==============================================
After

.button {
    height: 25px;
    .touch & {
      height: 44px;
    }
  }

```
. another way
```
Before

.button {
  height: 25px;
}
.button .touch {
  height: 44px;
}
=========================================
After

.button {
    height: 25px;
    .touch {
      height: 44px;
    }
  }

```

## Extend existing rules

```
Before

.first-selector, .second-selector {
  height: 44px;
}
.second-selector {
  width: auto;
}
==============================================
After

  .first-selector {
    height: 44px;
  }
  .second-selector {
    @extend .first-selector;
    width: auto;
  }

```

## Placeholder selectors

```
.warning-box, .success-box {
  padding: 2em;
  color: #123045;
  background-color: #123045;
}

.warning-box {
  border: 2px dotted #123233;
}

.success-box {
  border: 2px dotted #111111;
}

======================================

$color10: #123045 ;
$color11 : #123045 ;
$color1 : #123233;
$color4: #111111;

%box {
    padding: 2em;
    color: $color10;
    background-color: $color11;
  }
  .warning-box {
    @extend %box;
    border: 2px dotted $color1;
  }
  .success-box {
    @extend %box;
    border: 2px dotted $color4;
  }


```

# Variables

```
$red: #dd0000;

.alert-box {
color: $red;
border: 1px solid $red; }

```
# The variables into a list as follows:
```
$pages: $red, $home, $about, $news, $links;

```
a range of built-in Sass functions – nth() – to retrieve the value in
our list
```
nth($pages, 0)
```

# Sass map variable
A Sass map is where we declare our list as a set of key:value pairs

```
$pages: (
home: #F7E900,
about: #FF5F09,
news: #A0005E,
links: #41004B);

```

# Nesting
```
ul.nav {
  list-style: none;
  li {
    padding: 0;
  }
}

=================

ul.nav {
  list-style: none;
}
ul.nav li {
  padding: 0;
}

```
# (&). The parent selector 
This serves as a way of accessing a selector that has already been
defined in our nesting.

```
ul {
  padding: 20px;
  &.slim {
    padding: 10px;
  }
}

=========
ul {
  padding: 20px;
}
ul.slim {
  padding: 10px;
}


```
2) example
```
ul {
  padding: 20px;
  &.slim {
    padding: 10px;
    &.slimmer {
      padding: 5px;
    }
  }
}
=============

ul {
  padding: 20px;
}
ul.slim {
  padding: 10px;
}
ul.slim.slimmer {
  padding: 5px;
}


```
3) define hover and focus states:
```
a {
  text-decoration: none;
  &:hover,
  &:focus {
    text-decoration: underline;
  }
}

===============================
a {
  text-decoration: none;
}
a:hover, a:focus {
  text-decoration: underline;
}
```
4) nested selector to override

```
p {
  font-size: 1em;
  .article & {
    font-size: 1.2em;
  }
}

===================

p {
  font-size: 1em;
}
.article p {
  font-size: 1.2em;
}
```
5) if we wanted to style a certain element based on its location within a site and we used different classes on the
body element for each section
```
.article h1 {
  background-color: #ffafa5;
  .home & {
    background-color: #bbfca2;
  }
  .about {
    background-color: #a0adf1;
  }
}
=================================
.article h1 {
  background-color: #ffafa5;
}
.home .article h1 {
  background-color: #bbfca2;
}
.article h1 .about {
  background-color: #a0adf1;
}
```
# Object Oriented CSS and approaches like SMACSS and BEM

BEM stands for Block Element Modifier and involves
defining our CSS classes by a block (the parent object), an element (a
descendent object) and a modifier (variations to that object). Let us
say that we have an article and want to provide styles for an image
in that article but also an alternative styling if we want that image to
be smaller

## double underscore __ 
as a separator for elements


## double hyphen -- 
as a separator for modifiers

```
.article {
  margin: 20px 0;
  &__image {
    width: 40%;
  }
  &--small {
    width: 20%;
  }
}
===========================

.article {
  margin: 20px 0;
}
.article__image {
  width: 40%;
}
.article--small {
  width: 20%;
}

```

# Namespaces in CSS tend to be reserved for
those properties that can be specified as shorthand – e.g. font – or
broken down into specific sub-properties – e.g. font-family, fontsize,
etc.

## Nesting CSS properties
namespaced properties in CSS include background, list, margin, padding and border

```
body {
  background: {
    color: #a1ff7f;
    image: url(tile.png);
    repeat: no-repeat;
    position: center;
  }
}

========================
body {
  background-color: #a1ff7f;
  background-image: url(tile.png);
  background-repeat: no-repeat;
  background-position: center;
}

```
# Extends

Parent selector (&) this is very much tied to the scope of the particular parent 
Variables, but these are only really for reusing small values such as a pixel size or colour value; 
they cannot be used for reproducing large chunks of code.

@extend command – to reuse already declared code snippets

```
.form {
  border: 1px solid #219fe3;
  background: #7cc6ef;
}
.quote {
  @extend .form;
  color: #000;
}

================
.form, .quote {
  border: 1px solid #219fe3;
  background: #7cc6ef;
}
.quote {
  color: #000;
}

```

# Placeholder selectors  a percent symbol (%)
Extends can be incredibly useful for creating resuable blocks of CSS.
in the above example, if we end up writing lots of styles specific to our .form element these will then be applied to our .quote
placeholder selectors through the use of a percent symbol (%)

```
%list-style {
  list-style: none;
  padding: 0;
}
.list-group {
  @extend %list-style;
  margin: 2.5em 0 0.75em;
}
=======================

.list-group {
  list-style: none;
  padding: 0;
}

.list-group {
  margin: 2.5em 0 0.75em;
}

```
# Logical Sass
```
.heading {
  font-size: (24 / 2) + px;
}
=================
.heading {
  font-size: 12px;
}

```
## Mixins
Mixins provide a way of creating reusable chunks of code but offer the ability to modify parts of that code as and when we need them.

```
$base-font-size: 16;
@mixin font-size($size) {
  font-size: $size + px;
  font-size: ($size / $base-font-size) + rem;
}
.box {
  @include font-size(24);
}

=========================================

.box {
  font-size: 24px;
  font-size: 1.5rem;
}

```
2 )

```
$base-font-size: 16;
@mixin font-size($size, $line-height) {
  font-size: $size + px;
  font-size: ($size / $base-font-size) + rem;
  line-height: ($line-height / $size);
}
.box {
  @include font-size(24, 32);
}

===============================================
.box {
  font-size: 24px;
  font-size: 1.5rem;
  line-height: 1.33333;
}


```

# set a default line-height using the colon separator when defining our arguments:
```
$base-font-size: 16;
@mixin font-size($size, $line-height: 32) {
  font-size: $size + px;
  font-size: ($size / $base-font-size) + rem;
  line-height: ($line-height / $size);
}
.box {
  @include font-size(24);
}
```
2) set a default line-height using the colon separator when defining our arguments using parameter:
```
$base-font-size: 16;
@mixin font-size($size, $line-height: (24/ $size)) {
  font-size: $size + px;
  font-size: ($size / $base-font-size) + rem;
  line-height: ($line-height / $size);
}
.box {
  @include font-size(24);
}


```
3) a clearfix mixin to use every time we want to clear an element:

```
@mixin clearfix {
  &:before,
  &:after {
    display: table;
    content: '';
    line-height: 0;
  }
  &:after {
    clear: both;
  }
}
form {
  @include clearfix;
}


===========================================

form:before, form:after {
  display: table;
  content: '';
  line-height: 0;
}
form:after {
  clear: both;
}


```
4) Passing properties as parameter

```
$red: #123423;
@mixin rgbaify($property, $colour, $opacity: 1) {
  #{$property }: $colour;
  #{$property }: rgba($colour, $opacity);
}
.alert {
  @include rgbaify(background-color, $red, 0.75);
}
===========================================
.alert {
  background-color: #123423;
  background-color: rgba(18, 52, 35, 0.75);
}

```
# Functions
A function is like a mixin but instead of returning code blocks, it can only be used to return values
The @return command is specifying the value.

```
@function squared($number) {
  @return ($number * $number);
}
.text {
  padding: squared(10) + px;
}
========================
.text {
  padding: 100px;
}

```
2) With Sass is that we can apply mathematics to variables featuring unit values
```
@function double($number) {
  @return ($number + $number);
}
.text {
  width: double(10px);
}
===========================================
.text {
  width: 20px;
}

```
3) declare as few or as many arguments as we want for our functions and also set default values:
```
@function line-height($font-size, $line-height: 1.5) {
  @return ($font-size * $line-height);
}
.text {
  line-height: line-height (18px);
}
====================================
.text {
  line-height: line-height 18px;
}

```

# Conditionals
Conditionals give us the chance to limit what we return to our CSS, avoid repeating ourselves, and ultimately make our Sass more extensible

```
Operator Tests against
==        Equal to
!=        Not equal to
>         Greater than
<         Less than
>=        Greater than or equal to
<=        Less than or equal to

```

## @if and @else conditions
we use @if and @ else to say that we’d like to test a set of conditions:
Syntax
```
@if $font == bold {
font-family:'Avenir-Demi'; }

@if ($font == bold) {
font-family:'Avenir-Demi'; }

```
1) 
```
@mixin font-type($font: 'base') {
  @if ($font == bold) {
    font-family: 'Avenir-Demi';
  } @else if ($font == italic) {
    font-family: 'Avenir-LightItal';
  } @else {
    font-family: 'Avenir-Light';
  }
}
.heading {
  @include font-type(bold);
}


=================================
.heading {
  font-family: 'Avenir-Demi';
}

```
2) 
```
$weather: sunny;
p {
  @if ($weather == overcast) {
    color: grey;
  } @else if ($weather == sunny) {
    color: yellow;
  } @else {
    color: blue;
  }
}
=====================
p {
  color: yellow;
}

```
## @for loops and lists
Another conditional we can use is @for.
we are setting an initial value for $i (1),
the hash character (#) in our loop followed by curly brackets
1) 
```
@for $i from 1 through 3 {
  .col-#{$i} {
    width: (10% * $i);
  }
}

========================
.col-1 {
  width: 10%;
}

.col-2 {
  width: 20%;
}

.col-3 {
  width: 30%;
}
```
2)
```
$home: #111111;
$about: #222222;
$news: #333333;
$links: #444444;
$pages: $home, $about, $news, $links;

@for $i from 1 through length($pages) {
  body.section-#{$i} {
    background: nth($pages, $i);
  }
}
===============================
body.section-1 {
  background: #111111;
}
body.section-2 {
  background: #222222;
}

body.section-3 {
  background: #333333;
}

body.section-4 {
  background: #444444;
}
```
# @each loops and Sass maps
The index() method used here is the reverse of nth() used above.

```
$home: #111111;
$about: #222222;
$news: #333333;
$links: #444444;
$pages: $home, $about, $news, $links;

@each $item in $pages {
  body.section-#{ index($pages, $item)} {
    background: $item;
  }
}
======================================
body.section-1 {
  background: #111111;
}

body.section-2 {
  background: #222222;
}

body.section-3 {
  background: #333333;
}

body.section-4 {
  background: #444444;
}
```
## the @each conditional to access these key:value pairs:
```
$pages: (
  home: #f7e900,
  about: #ff5f09,
  news: #a0005e,
  links: #41004b,
);
@each $key, $value in $pages {
  body.section-#{ $key} {
    background: $value;
  }
}

========================================
body.section-home {
  background: #f7e900;
}

body.section-about {
  background: #ff5f09;
}

body.section-news {
  background: #a0005e;
}

body.section-links {
  background: #41004b;
}

```

# @import and partials
This lets us break our CSS into different files and then request them as we need them in our CSS.
each @import, our browser has to make another HTTP request and using lots of @imports can really slow down our page load time

```
@media screen and (min-width: 640px) {
@import url(tablet.css) }

```

# Media query bubbling
the practicalities of writing and maintaining CSS that supports both approaches can rapidly become very complicated. However, Sass makes this much more straightforward through the concept of media query bubbling.
Media query bubbling then provides a way of keeping our media queries much more focussed.

```
.aside {
  width: 100%;
  @media screen and (min-width: 800px) {
    float: right;
    width: 35%;
  }
}

=======================================
.aside {
  width: 100%;
}
@media screen and (min-width: 800px) {
  .aside {
    float: right;
    width: 35%;
  }
}

```
2) 
```
$break-small: 640px;

@mixin responsify($breakpoint) {
  @media (min-width: $breakpoint) {
    @content;
  }
}
.article {
  @include responsify($break-small) {
    float: left;
  }
}


===============================

@media (min-width: 640px) {
  .article {
    float: left;
  }
}
```

3) 

```
$break-small: 640px;

@mixin responsify($min, $media: screen, $max: false) {
  @if $max {
    @media #{ $media} and (min-width: $min) and (max-width:
    $max) {
      @content;
    }
  } @else {
    @media #{$media} and (min-width: $min) {
      @content;
    }
  }
}
.article {
  @include responsify($break-small) {
    float: left;
  }
}

=============================================

@media screen and (min-width: 640px) {
  .article {
    float: left;
  }
}

```
4) 
```
$break-small: 640px;
$break-medium: 800px;
$break-large: 1024px;
@mixin responsify($min, $media: screen, $max: false) {
  @if $max {
    @media #{ $media} and (min-width: $min) and (max-width:
    $max) {
      @content;
    }
  } @else {
    @media #{$media} and (min-width: $min) {
      @content;
    }
  }
}
.article {
  @include responsify($break-small, screen, $break-medium - 1) {
    float: left;
  }
}

===============================================


@media screen and (min-width: 640px) and (max-width: 799px) {
  .article {
    float: left;
  }
}

```

# Built in function examples

```
.icon {
  // round produces 26px (rounds to nearest integer)
  width: round(25.5px);
  // ceil produces 3px (rounds up to nearest integer)
  width: ceil(25px / 10);
  // floor produces 2px (rounds down to nearest integer)
  width: floor(25px / 10);
}

====================

.icon {
  width: 26px;
  width: 3px;
  width: 2px;
}

```

# Working with map

```
$pages: (
  home: #f7e900,
  about: #ff5f09,
  news: #a0005e,
  links: #41004b,
);
.news {
  background-color: map_get($pages, news);
}
===============================================
.news {
  background-color: #a0005e;
}

```
# Sass’ darken() and lighten() functions

```
$pages: (
  home: #f7e900,
  about: #ff5f09,
  news: #a0005e,
  links: #41004b,
);
.news {
  background-color: map_get($pages, news);
  border-color: darken(map_get($pages, news), 25%);
  font-color: lighten(map_get($pages, news), 25%);
}

=========================

.news {
  background-color: #a0005e;
  border-color: #210013;
  font-color: #ff21a3;
}

```

# creating a nested colour palettes map.

```
$palettes: (
  blue: (
    light: #9cb9c8,
    base: #669db3,
    dark: #f5814d,
  ),
  red: (
    light: #9cb9c8,
    base: #669db3,
    dark: #f5814d,
  ),
  orange: (
    light: #9cb9c8,
    base: #669db3,
    dark: #f5814d,
  ),
);
@function palette($palette, $tone: base) {
  @return map-get(map-get($palettes, $palette), $tone);
}
.box {
  color: palette(blue);
  &-border {
    border: 1px solid palette(blue, dark);
  }
}

================================================================


.box {
  color: #669db3;
}
.box-border {
  border: 1px solid #f5814d;
}

```
# Accessing paramter 

```
$class-name: my-great-class;
$attribute: border;
p.#{$class-name} {
  // Correct
  #{$attribute}-color: blue; // Correct
}


==================================
p.my-great-class {
  border-color: blue;
}
```


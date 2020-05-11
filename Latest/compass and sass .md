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

# Functions
A function is like a mixin but instead of returning code blocks, it can only be used to return values

# Explain what is Sass? How it can be used?
Sass focuses on how to create awesome stylesheets, not what goes into them.tools like Compass that provide you with CSS best practices.
Sass stands for Syntactically Awesome Stylesheets and was created by Hampton Catlin. SCSS, or Sassy CSS, was introduced in Sass 3.0 and is a superset or extension of CSS3. SCSS files havea .scss file extension it
adding nested rules, mixins, variables, selector inheritance, etc.
Sass can be used in three ways

•As a command line tool

•As a standalone Ruby module

•As a plugin for any Rack-enabled framework

# List out alternatives against LESS?
•SASS: Syntactically Awesome Stylesheets

•SCSS: Version.2 of SASS

•Stylus

# Keywords and declaration in Sass
variables

$company-blue: #1875e7;

Mixins: help you remove redundant styles

@mixin horizontal-list {
li {float: left;
margin-right: 10px;
}
}

Mixins with variables
```
@mixin horizontal-list($spacing: 10px) {
li {
float: left;
margin-right: $spacing;
}
}

calling it
#footer ul.nav {
@include horizontal-list(20px);
margin-top: 1em;
}
```
Selector inheritance with the placeholder selector
```
%button-reset {
margin: 0;
padding: .5em 1.2em;
text-decoration: none;
cursor: pointer;
}
.save {
@extend %button-reset;
}
```
# What is Compass?
Compass is a collection of helpful tools to write smarter stylesheets and battle-tested best practices for Sass, 
it made up of three main components.
> a library of Sass mixins and utilities.

> a system for integrating with application environments.

> a platform for building frameworks and extensions.

# List out the key features for Sass?
Key features for Sass include

•Full CSS3-compatible

•Language extensions such as nesting, variables, and mixins

•Many useful functions for manipulating colors and other values

•Advanced features like control directives for libraries

•Well-formatted, customizable output

# List out the Data Types that SassScript supports?
SassScript supports seven main data types
1.Numbers ( eg; 1,5 ,10px)

2.Strings of texts ( g., “foo”, ‘bar’, etc.)

3.Colors (blue, #04a3f9)

4.Booleans (true or false)

5.Nulls (e.g; null)

6.List of values, separated by space or commas (g., 1.5em, Arial, Helvetica etc.)

7.Maps from one value to another (g., ( key 1: value1, key 2: Value 2))

# Explain how to define a variable in Sass?
Variables in Sass begin with a ($) sign and variable assignment is done with a colon(:).

# Explain what is the difference between Sass and SCSS?
The difference between Sass and SCSS is that,

•Sass is a CSS pre-processor with syntax advancements and an extension of CSS3

•Sass has two syntax

•The first syntax is “SCSS” and it uses the .scss extension

•The other syntax is indented syntax or just “Sass” and it uses the .sass extension

•While Sass has loose syntax with white space and no semicolons, the SCSS resembles more to CSS

Any CSS valid document can be converted to Sass by simply changing the extension from.CSS to.SCSS.

# What Selector Nesting in Sass is used for?
In Sass, selector nesting offers a way for stylesheet authors to compute long selectors by nesting shorter selectors within each other.

# Explain what is a @extend function used for in Sass?
In Sass, the @EXTEND directive provides a simple way to allow a selector to inherit the styles of another one. 
It aims at providing a way for a selector A to extend the styles from a selector B. When doing so, 
the selector A will be added to selector B so they both share the same declarations.  @EXTEND prevents code bloat 
by grouping selectors that share the same style into one rule.

# Explain what is the use of the @IMPORT function in Sass?
The @IMPORT function in Sass

•Extends the CSS import rule by enabling import of SCSS and Sass files

•All imported files are merged into a single outputted CSS file

•Can virtually mix and match any file and be certain of all your styles

•@IMPORT takes a filename to import


# Why Sass is considered better than LESS?
•Saas allows you to write reusable methods and use logic statements, e., loops, and conditionals

•Saas user can access Compass library and use some awesome features like dynamic sprite map generation, 
legacy browser hacks and cross-browser support for CSS3 features
•Compass also allows you to add an external framework like Blueprint, Foundation or Bootstrap on top

•In LESS, you can write a basic logic statement using a ‘guarded mixin’, which is equivalent to Sass if statements

•In LESS, you can loop through numeric values using recursive functions while Sass allows you to iterate any kind of data

•In Sass, you can write your own handy functions

# Explain what is the use of Mixin function in Sass? What is the meaning of DRY-ing out a mixin?
Mixin allows you to define styles that can be re-used throughout the stylesheet without needing to resort 
to non-semantic classes like .float-left.
DRY-ing out of a mixing means splitting it into dynamic and static parts.  
The dynamic mixin is the one that the user actually going to call, and the static mixin is 
the pieces of information that would otherwise get duplicated.

# Explain what Sass Maps is and what is the use of Sass Maps?
Sass map is a structured data in a hierarchical way and not just a bunch of variables. 
It can help in organizing the code. Some great use of Sass are

•It is very useful when dealing with layers of elements in your project

•It can be helpful in color management when there is long list of different color and shade

•Use icon map for various social media icons for example: facebook: ‘\e607’ or twitter: ‘\e602’

•Unlike other programming libraries, Sass map will consist only of code that is going to be used

# Explain how Sass comments are different from regular CSS?
Syntax for comments in regular CSS starts with /* comments…*/, while in SASS there are two type of comment, 
the single line comments // and the multiline CSS comments with /* */.

# Does Sass support inline comments?

Single line comments // will be removed by the .scss pre-processor and won’t appear in your .css file
While the comment */ are valid CSS, and will be preserved between the translation from .scss to your .css file

# How interpolation is used in Sass?
In Sass, you can define an element in a variable and interpolate it inside the Sass code.  
It is useful when you keep your modules in separate files.

# Explain when can you use the %placeholders in Sass?
%placeholders in Sass is useful when you want to write styles that were meant to be extended, 
but you don’t want the base styles to be seen in output CSS styles

# Is it possible to nest variables within variables in Sass?
Interpolation of variables names is not possible currently in Sass. However, you may use interpolation of placeholders.

# What are Sass cons and pros?
Pros:

•Sass is easy to learn especially for them who has a background of Python, Ruby or Coffescript and place using functions, 
writing mixins
•CSS can be easily converted to Sass

•Throughout the project, you don’t have to repeat similar CSS statements using @extend attribute

•It allows to define variables that are usable throughout the entire project

•It keeps your responsive project more organized

# Explain what is LESS?
LESS is dynamic style sheet producing language. LESS is a CSS pre-processors and extends CSS with dynamic behaviour. 
It allows for variables, mixins, operations and functions. LESS runs on server side and client side both.

# Explain how to create LESS file and where to store it and compile it?
Creating or storing LESS file is similar to creating/storing CSS file. A new LESS file can be created with a .less extension, 
or you can rename existing .css file to .less file. You can write LESS code with existing CSS code.

The best way of creating it inside ~/content/ or ~/Styles/ folder

# In what ways LESS can be used?
•Via npm LESS can be used on the command line

•Download as a script file for the browser

•For third party tools, it is used

# How variable is represented in LESS?
LESS allows variables to be defined. In LESS, the variable is represented as @sing. While, 
variable assignment is done with a: (colon) sing. The values of the variables are inserted into 
the CSS output file as well as minified file.

# Explain how Mixins is useful?
Mixins enable embedding all the properties of a class into another class by including the class name as one of its properties. 
It is just like variables but for whole classes.

# Explain how can set code in a watch mode when you run LESS.js in an HTML5 browser?

If you run LESS.js in an HTML5 browser, it will use local storage to cache the generated CSS. However, 
from the developer point of view they cannot see the changes they made instantly. In order to see your changes instantly, 
you can load program in development and watch mode by following JavaScript
```
<script type= “text/javascript”>

less.env = “development “ ;

less.watch () ;

</script>
```
# Explain what is the meaning of nesting in LESS programming?
Nesting in LESS is clustering of statements inside other statements, so it forms a group of related code. 
In other words when we add a code snippet and add another code inside it, then that code snippet is called nesting.

# Mention what are the color channel functions used in LESS?
•hue
•saturation
•hsvhue
•saturation
•hswalue
•red
•green
•blue
•alpha
•luma
•luminance

# Explain what is data-uri in LESS?
In CSS, Data URI’s is one of the best technique, it allows developers to avoid external image referencing and 
instead embed them directly into a stylesheet. Data URIs are the excellent way to reduce HTTP requests

# Explain what “Source Map Less Inline”?
The “ Source Map Less Inline” option indicates that we should include all of the CSS files into the sourcemap. 
Which means that you only need your map file to get to your original source.

# Explain what is the use of Extend “all” in LESS?
When you specify all keyword last in an extend argument, it tells LESS to match that selector as part of another selector.

# Explain what is “StrictImports” in LESS?
The strictImports controls whether the compiler will allow a @import inside of either @media blocks or other selector blocks

# List out the differences between LESS and Sass?
Each style-sheet language is good in their perspective and use; however there are few differences in their usage.
LESS
– LESS uses JavaScript and processed at client-side
– Variable names are prefaced with the @symbol
– LESS does not inherit multiple selectors with one set of properties
– LESS does not work with “unknown” units neither it returns syntax error notification for incompatible units or maths related syntax error

Sass
– Sass is coded in Ruby and thus processed to server-side
– Variable name are prefaced with $ symbol
– Sass inherits multiple selectors with one set of properties
– Sass allows you to work with “unknown” units also returns a syntax error notification for incompatible units

# What are the similarities between LESS and Sass?
Between LESS and Sass the similarities are

•Namespaces

•Color functions

•Mixins and parametric mixins

•Nesting capabilities

•JavaScript evaluations


# Explain what is the use of &combinator ?
&combinator concatenates nested selector with the parent selector. It is useful for Pseudo classes such as :hover and :focus

# Explain what is the use of operations in LESS?
Operations can be used for performing functions like

•Simple Mathematical operators: +, – , *, /

•Color functions

•Math functions

•Any size or colour variable can be operated upon

# Explain what is the use of Escaping?
The use of escaping in LESS

•When you need to output CSS that is not valid CSS syntax

•Proprietary syntax not recognized by LESS

•LESS compiler will throw an error if not used

•Simple prefix with ~ symbol and put in quotes


# What does LESS elements contains?
Less elements contain commonly used mixins like

•.gradient

•.rounded

•.opacity

•.box-shadow

•.inner-shadow



# Explain how you can invoke the compiler from the command line?
You can invoke the compiler from the command line in LESS as

$ lessc styles.less

This will output the compiled CSS to stdout; you may then redirect it to a file of your choice

$ lessc styles.less > styles.css

# What is the use of e () function?
With the help of e() function you can escape a value so that it passes straight through to the compiled CSS, 
without being noticed by the LESS compiler.

# Explain how you can pre-compile LESS into CSS?
To pre-compile LESS into CSS you can use
•Run less.js using Node.js : By using the Node.js JavaScript framework you can run the less.js script outside the browser
•Use lessphp: For the implementation of the LESS compiler written in PHP, lessphp is used
•Use online Compiler: Use online compiler for quick compilation of LESS code without installing a compiler
•Less. app (for Mac users): Less.app is a free tool for Mac users, this tool auto compiles them into CSS files

# Explain how merge function is used in LESS?
For aggregating values from multiple properties into a space or comma separated list under a single property LESS is used. 
It is useful for properties such as transform and background

# How can you create a loop structures in LESS?
A mixin can call itself in LESS. Such recursive mixins, when combined with Pattern matching and Guard Expressions, 
can be used to create various iterative/loop structures.

# Why do we need parametric mixins in LESS?
Parametric mixins are same like standard mixins. The only difference is that parametric mixins take parameters 
like functions in JavaScript. After determining parameters to the mixins, you get more control over mixins.

Cons:
•White space sensitive
•No inline rules

# What is CSS ?
The full form of CSS is Cascading Style Sheets. It is a styling language which is simple enough for HTML elements. 
It is popular in web designing, and its application is common in XHTML also.

# What is the origin of CSS ?
Standard Generalized Markup Language marked the beginning of style sheets in 1980s

# What are the different variations of CSS ?
 The variations for CSS are:
•CSS 1
•CSS 2
•CSS 2.1
•CSS 3
•CSS 4

# What are the limitations of CSS ?
Limitations are:
• Ascending by selectors is not possible
•Limitations of vertical control
•No expressions
•No column declaration
•Pseudo-class not controlled by dynamic behavior
•Rules, styles, targeting specific text not possible

# What are the advantages of CSS ?
Advantages are:
•Bandwidth
•Site-wide consistency
•Page reformatting
•Accessibility
•Content separated from presentation

# What are CSS frameworks?
It is a pre-planned libraries, which allows easier and more standards-compliant webpage styling, using CSS language.

# How block elements can be centered with CSS1?
Block level elements can be centered by:
The margin-left and margin-right properties can be set to some explicit value:
```
width: 40em; 
background: fluorescent; 
}
 
P { 
width: 30em; 
margin-right: auto; 
margin-left: auto 
}
```
In this case, the left and right margins will be each, five ems wide since they split up the ten ems left over from (40em-30em). 
It was unnecessary for setting up an explicit width for the BODY element; it was done here for simplicity.

# Who maintains the CSS specifications?

World Wide Web Consortium maintains the CSS specifications.

# In how many ways can a CSS be integrated as a web page?

CSS can be integrated in three ways:
•Inline: Style attribute can be used to have CSS applied HTML elements.
•Embedded: The Head element can have a Style element within which the code can be placed.
•Linked/ Imported: CSS can be placed in an external file and linked via link element.

# What benefits and demerits do External Style Sheets have? 
 Benefits:
•One file can be used to control multiple documents having different styles.
•Multiple HTML elements can have many documents, which can have classes.
•To group styles in composite situations, methods as selector and grouping are used.

Demerits:
•Extra download is needed to import documents having style information.
•To render the document, the external style sheet should be loaded.
•Not practical for small style definitions.

# Discuss the merits and demerits of Embedded Style Sheets?
 Merits of Embedded Style Sheets:
•Multiple tag types can be created in a single document.
•Styles, in complex situations, can be applied by using Selector and Grouping methods.
•Extra download is unnecessary.

Demerits of Embedded Style Sheets:
•Multiple documents cannot be controlled.

# What does CSS selector mean?
A string equivalent of HTML elements by which declarations or a set of it, is declared and is a link that 
can be referred for linking HTML and Style sheet is CSS selector.

# Enlist the media types CSS allows?
The design and customization of documents are rendered by media. By applying media control over the external style sheets, 
they can be retrieved and used by loading it from the network.

# Differentiate logical tags from physical tags?
•While physical tags are also referred to as presentational mark-up, logical tags are useless for appearances.
•Physical tags are newer versions while logical tags are old and concentrate on content.

# Differentiate Style Sheet concept from HTML?
While HTML provides easy structure method, it lacks styling, unlike Style sheets. Moreover, style sheets have 
better browser capabilities and formatting options.

# Describe ‘ruleset’?
Ruleset : Selectors can be attached to other selectors to be identified by ruleset.

It has two parts:
•Selector, e.g. R and
•declaration {text-indent: 11pt}

# Comment on the Case-sensitivity of CSS ?
Although, there are no case-sensitivity of CSS, nevertheless font families, URL’s of images, etc is. 
Only when XML declarations along with XHTML DOCTYPE are being used on the page, CSS is case -sensitive.

# Define Declaration block?
A catalog of directions within braces consisting of property, colon and value is called declaration block.
 e.g.: [property 1: value 3]

# Enlist the various fonts’ attributes?
They are:
•Font-style
•Font-variant
•Font-weight
•Font-size/line-height
•Font-family
•Caption
•Icon

 

# Why is it easy to insert a file by importing it?
Importing enables combining external sheets to be inserted in many sheets. Different files and sheets can be used to 
have different functions. Syntax:

```
@import notation, used with <Style> tag.
```
# What is the usage of Class selector?
Selectors that are unique to a specific style, are called CLASS selectors. Declaration of style and association 
with HTML can be made through this. Syntax:
```
Classname
 it can be A-Z, a-z or digits.
 .top {font: 14em ;}, class selector
 <Body class= “top”> this class is associated with element </body>

```
# Differentiate Class selector from ID selector?

While an overall block is given to class selector, ID selector prefers only a single element differing   from other elements.

# Can more than one declaration be added in CSS?

Yes, it can be achieved by using a semicolon.

# What is Pseudo-elements ?

Pseudo-elements are used to add special effects to some selectors.  CSS in used to apply styles in HTML mark-up. 
In some cases when extra mark-up or styling is not possible for the document, then there is a 
feature available in CSS known as pseudo-elements. It will allow extra mark-up to the document without disturbing the actual document.

# How to overrule underlining Hyperlinks?
Control statements and external style sheets are used to overrule underlining Hyperlinks.

E.g.:
```
B { 
text-decoration: none; 
} 
<B href="career.html" style="text-decoration: none">link text</B>
```

# What happens if 100% width is used along with floats all across the page?
While making the float declaration, 1 pixel is added every time it is used in the form of the border, 
and   even more float is allowed thereafter.

# Can default property value be restored through CSS? If yes, how?
In CSS, you cannot revert back to old values due to lack of default values. 
The property can be re- declared to get the default property.

# Enlist the various Media types used?
Different media has different properties as they are case insensitive.

They are:
•Aural – for sound synthesizers and speech
•Print – gives a preview of the content when printed
•Projection- projects the CSS on projectors.
•Handheld- uses handheld devices.
•Screen- computers and laptop screens.

# What is CSS Box Model and what are its elements?
This box defines design and layout of elements of CSS. The elements are:

Margin: the top most layer, the overall structure is shown
Border: the padding and content option with a border around it is shown.  Background color affects the border.
Padding: Space is shown. Background colour affects the border.
Content: Actual content is shown.

# What is contextual selector?
Selector used to select special occurrences of an element is called contextual selector. A space separates the individual selectors. 
Only the last element of the pattern is addressed in this kind of selector. For e.g.: TD P TEXT {color: blue}

# Compare RGB values with Hexadecimal color codes ?
A color can be specified in two ways:
•A color is represented by 6 characters i.e. hexadecimal color coding. It is a combination of numbers and letters and is preceded by #.      
 e.g.: g {color: #00cjfi}
•A color is represented by a mixture of red, green and blue. The value of a color can also be specified.
 e.g.: rgb(r,g,b): 
 In this type the values can be in between the integers 0 and 255. rgb(r%,g%,b%):  red, green and blue percentage is shown.

# Define Image sprites with context to CSS ?
When a set of images is collaborated into one image, it is known as ‘Image Sprites’. As the loading every image on a webpage consumes time, using image sprites lessens the time taken and gives information quickly.

CSS coding:
```
img.add { width: 60px; height: 55px; background: url (image.god) 0 0; }
```
In this case, only the part needed is used. The user can save substantial margin and time through this.

# Compare Grouping and Nesting in CSS ?
Grouping:  Selectors can be grouped having the same values of property and the code be reduced.
 E.g. :
 ```
h1 { 
color: blue; 
} 
h2 { 
color: blue; 
} 
p { 
color: blue; 
}
 ```
It can be seen from the code that every element shares the same property. Rewriting can be avoided 
by writing each selector separated by a comma.
Nesting: Specifying a selector within a selector is called nesting.
```
P 
{ 
color: red; 
text-align: left; 
} 
.marked 
{ 
background-color: blue; 
} 
.marked p 
{ 
color: green; 
}

```
# How can the dimension be defined of an element ?
Dimension properties can be defined by:
•Height
•Max-height
•Max-width
•Min-height
•Min-width
•Width

# Define float property of CSS?
By float property, the image can be moved to the right or the left along with the text to be wrapped around it. 
Elements before this property is applied do not change their properties.

# How does Z index function?
Overlapping may occur while using CSS for positioning HTML elements. 
Z index helps in specifying the overlapping element. 
It is a number which can be positive or negative, the default value being zero.

# What is graceful degradation?
In case the component fails, it will continue to work properly in the presence of a graceful degradation. 
The latest browser application is used when a webpage is designed. As it is not available to everyone, 
there is a basic functionality, which enables its use to a wider audience. In case the image is unavailable for viewing, 
text is shown with the alt tag.

# What is progressive enhancement?
It’s an alternative to graceful degradation, which concentrates on the matter of the web. The functionality is same, 
but it provides an extra edge to users having the latest bandwidth. It has been into prominent use recently 
with mobile internet connections expanding their base.

# How can backward compatibility be designed in CSS?
HTML sheet methods is collaborated with CSS and used accordingly.

# How can the gap under the image be removed?
As images being inline elements are treated same as texts, so there is a gap left, which can be   removed by:
CSS
```
img { display: block ; }
```

# Why is @import only at the top?
@import is preferred only at the top, to avoid any overriding rules. Generally, ranking order is followed in 
most programming languages such as Java, Modula, etc. In C, the # is a prominent example of a @import being at the top.

# Which among the following is more precedent: CSS properties or HTML procedures?
CSS is more precedent over HTML procedures. Browsers, which do not have CSS support, display HTML attributes.

# What is Inline style?
The Inline style in a CSS is used to add up styling to individual HTML elements.

# How comments can be added in CSS?
The comments in CSS can be added with /* and */.

# Define Attribute Selector ?
It is defined by a set of elements, value and its parts.

# Define property?
A style, that helps in influencing CSS. E.g. FONT. They have corresponding values or properties within them, 
like FONT has different style like bold, italic etc.

#  What is Alternate Style Sheet?
Alternate Style Sheets allows the user to select the style in which the page is displayed using the view>page style menu. 
Through Alternate Style Sheet, user can see a multiple version of the page on their needs and preferences.

# Are quotes mandatory in URL’s?
Quotes are optional in URL’s, and it can be single or double.

# What is at-rule?
Rule, which is applicable in the entire sheet and not partly, is known as at-rule. It is preceded by @ followed by A-Z, a-z or 0-9.

# How can CSS be cascaded to mix with user’s personal sheet?
Properties can be a set in recommended places and the document modified for CSS to mix with user’s   personal sheet.

# Adjacent sibling selector

To say look for the element next to it that has the CSS class of invalid applied to it.

input:valid+ .invalid{
visibility:hidden;
}

# Why CSS is painful
- The "color Problem": css doesnt allow to have named color, we have to repeat color throughout the CSS.

- Duplication Issues: There is no way to create reusable section in the CSS.

- Cascading Avalanches: It is impossible to see from where cascading role is coming from.

- Lack of Calculations: CSS doesnt allow its values to be arbitarary formulas.

- The Problem with Imports: How imports, Browser cache make css harder to manage long term.


# Why to use LESS or SASS
- Improve on the lack of common colors, by allowing us create the variables at top level and shared among the files
- Allow reusable components of CSS, and plug them in the css.
- Bring clarity to how rules cascade, allow them to nest.
- Allow do to calculations in CSS.
- Allow you to comibe CSS as needs dictate.

# What is LESS?
Its Dynamic Style Sheet Language, which compiles down to CSS. This is normally a Transform operation whether it is on the client  or server to produce CSS which browser is expecting.
It introduces these programming features to CSS but the language looks and feels like CSS.
. Note: All CSS is valid LESS, just replace CSS with .LESS

# Using LESS on the Client

[less.js](https://github.com/less/less.js.git)
```
<head>
// your referenced Less stylesheet (i.e. styles.less)
 <link href="styles.less" type="text/css" rel="stylesheet/less"/>
 <script src="less.js" type="text/javascript"></script>
 </head>

```
# Using LESS on the Server

- NPM: 
```
$ npm install less
var less=require('less');
```

- ASP.net vai Nuget: 
```
install-package dotless
or 
>Manage Nuget package> search dotless.
```

```
$ npm install server-less-loader --save-dev
```
How to use

add server-less-loader before any js-related loader
```
{
    test: /\.babel$/,
    loader: "babel!server-less-loader"
},
```

add serverLessLoader option in webpack.config.js
```
serverLessLoader: {
    loader: 'importLess' // use any word except for 'require' 
}

```
# LESS Basics
. LESS is meant to feel like CSS but better

  . All CSS is valid 

  	. Renaming your .css to .less works

  . LESS adds to CSS
	

# Variables in LESS

@myColor: #ffeedd; // They don’t need to have quote
@myColor2: Red;
- Variable are constants, manipulation won’t work like below
```
@myColor: @myColor + 5%; // This will not work
// still it represent
@myColor: #ffeedd;
// But we can do this
color: @myColor + 5%; // This will work
color: @myColor2 + 5%; // This will not work

```
# Different values to variable
```
@a: Black;                    	 	// Color
@b: 4px;			//Units
@c: 1.0em;			//Units
@d: Helvectica, sans serif;	//Strings
@e: 1px #000 Solid 0 0;		//Complex Type


```
# Operations
The operation that work
```
font-size: 4px + 4;   		// 8px
font-size: 20px * .8 		//16px;

color: #FFF/4;			// #404040;
width: (100% / 2) + 25%; 	// 75%

```
# Color Function

```
color: lighten(@color, 10%);
color: darken(@color, 10%);

color: saturate(@color, 10%);
color: desaturate(@color, 10%);

color: fadein(@color, 10%);
color: fadeout(@color, 10%);
color: fade(@color, 50%);

color: spin(@color, 10%);
color: mix(@color, 246%);

// Getting color values
@hue: hue(@color);
@sat: saturation(@color);
@light: lightness(@color);
@alpha: alpha(@color);
@color: hsl(20%, 30%, 40%);

// Typical Math
@rnd: round(3.14);
@top: ceil(3.14);
@bot: floor(3.14);
```


# Nesting

Nesting is one of the Less's coolest features. Nesting let's you do more and write less. Nesting allows you to cascade your css properties with inheritting children.

- Less Code 
```

h1 {
    color: rgb(255, 123, 123);
    font-weight: 300;

    span {
        font-weight: 600;
        color: rgb(255, 69, 69) ;
    }

    &:hover {
        color: rgb(200, 0, 0);
    }

    &:hover span {
        color: rgb(50, 50, 58);
    }
}


```
- Compiled CSS code


```
h1 {
    color: #ff7b7b;
    font-weight: 300;
}
h1 span {
    font-weight: 600;
    color: #ff4545;
}
h1:hover {
    color: #c80000;
}
h1:hover span {
    color: #32323a;
}


```
# Nested Rules
-	 Allows you to structure rules in a logical way
. Hierarchies imply the cascading/specificity
. LESS than deconstructs it into CSS for you 
CSS
```
nav {
	font-size: 14px;
	font-weight: bold;
	float: right;
}
nav ul {
list-style-type: none;
}
nav ul li {
float: left;
margin: 2px;
}
```
LESS Nested Rules
```
nav {
font-size: 14px;
font-weight: bold;
	ul { 	// Makes “nav ul {…}”
	list-style-type: none;
	li {	// Makes “nav ul li {…}”
	     float: left;
	     margin: 2px;
	}
       }
}
```

# Combinator (&) to mix with parent:
```
a { 
    text-decoration: none;
    &:hover  {
text-decoration: underline;
}
}
// Results in
a {text-decoration: none;}
a: hover { text-decoration: underline; }
```

# Namespaces 
Namespacing for organizational grouping

```
#my-froms {
  .set-button  {
font-size: 14px;
text-align: center;
}
}

# submit-button {
#my-forms > .set-button;  // This will say go and find set-button inside my-froms 
}

````

# String Interpolation
Can use Ruby style string insertion
```
@root: “/images/”;
#form {
background: url(“@{root}background.jpg”);
// Becomes url(“/images/background.jpg”)
}
```

# Using Javascript directly in Less
Embed with back-quotes to execute JS
```
@root: “/images”;
@app-root: `”@{root}”.toUpperCase()`;
#form {
// Becomes url(“/IMAGES/back.jpg”);
Background: url (“@{app-root}/back.jpg”);
}
```

# Variables
CSS variables will be a thing of the future. There's already a spec for them. With Less, you can start using this concept now.

- Less Code 
```

@heading-color: rgb(99, 200, 200);
h1 {
    color: @heading-color;
    font-weight: 300;
}
```
- Compiled CSS code  

```
h1 {
    color: #63c8c8;
    font-weight: 300;
}

```

# Importing

Importing works very similar to regular CSS importing. With Less, it's actually really smart to treat them like includes. Some of the benefits:
•Easier to collaborate with others 
•Variables are shared across imports 
•Creates (almost forces) a modular and dry approach to front-end development 

```
// Core variables and mixins
@import "variables.less";
@import "mixins.less";

// Reset and dependencies
@import "normalize.less";
@import "print.less";
@import "glyphicons.less";

// Core CSS
@import "scaffolding.less";
@import "type.less";
@import "code.less";
@import "grid.less";
@import "tables.less";
@import "forms.less";
@import "buttons.less";

// Components
@import "component-animations.less";
@import "dropdowns.less";
@import "button-groups.less";
@import "input-groups.less";
@import "navs.less";
@import "navbar.less";
@import "breadcrumbs.less";
@import "pagination.less";
@import "pager.less";
@import "labels.less";
@import "badges.less";
@import "jumbotron.less";
@import "thumbnails.less";
@import "alerts.less";
@import "progress-bars.less";
@import "media.less";
@import "list-group.less";
@import "panels.less";
@import "responsive-embed.less";
@import "wells.less";
@import "close.less";

// Components w/ JavaScript
@import "modals.less";
@import "tooltip.less";
@import "popovers.less";
@import "carousel.less";

// Utility classes
@import "utilities.less";
@import "responsive-utilities.less";

```

# Mixins

- CSS way of mixing classes
```
<a href="https://scotch.io" class="btn btn-success btn-lg btn-block">

```

LESS way of Mixins
```
.big-sexy-button {
    .btn;
    .btn-success;
    .btn-lg;
    .btn-block;
}


```



- Mixins are exactly what they sound like. You can literally mix and match CSS classes with each other. 

-	Repeatable sections
o	Feel like functions
o	But insert more than one name/value pair
o	Can accept parameters, defaults and overloads
o	It start with “.”
```
.round-corners-all(@size){
boarder-radius: @size;
-webkit-border-radius: @size;
-moz-border-radius: @size;
}
#form
{
.rounded-corners-all(5px);
}
// It can have Default values
.round-corners-all(@size: 5px){
}
#form
{
.rounded-corners-all;
}

```
-	Using overloads
```
.color(@color) {
color: @color;
}

.color(@color, @factor) {
color: lighten(@color, @factor);
}

#form
{
. color(#888, 20%); // Uses 2nd overload
}
```
-	Using value based guards
```
.color(@color)  when (alpha (@color) >= 50%) {
color: Black;
}
.color(@color)  when (alpha (@color) < 50%) {
color: transparent;
}
#form
{
. color(@mainColor); 
}


```
-	Type based Guards
```
.width(@size) when (isnumber(@size)){
Width: @size * 2;
}
.width(@size) when (ispercentage(@size)){
Width: @size;
}

#form
{
. width(50%);  // uses 2nd overload
}

```




# Mixins as a Function
Mixins can also be functions. This way you can pass a variable or parameter to your added mixin.

- Less Code 

```
div {
    .border-top-radius(125px);

    background: rgb(255, 255, 255);
    display: inline-block;
    padding: 50px;
}
.border-top-radius(@radius) {
    border-top-right-radius: @radius;
    border-top-left-radius: @radius;
}

```

- Compiled CSS code 

```
div {
    border-top-right-radius: 125px;
    border-top-left-radius: 125px;
    background: #ffffff;
    display: inline-block;
    padding: 50px;
}
```

# Examples
[LESS HAT](http://lesshat.madebysource.com/)

# Operations

Operations bring math and calculations to your CSS. You can do operations on the following data types:
•A Number 
•A Color 
•A Variable 

```
/* Number */
h1 {
    margin-bottom: 10px - 5px;
    margin-bottom: 10px - 5;
}

/* Color */
h1 {
    color: #888888 / 2;
}

/* Variable */
@h1-default-margin-bottom:  25px;
h1.tight {
    margin-bottom: @h1-default-margin-bottom - 10px
}



```
Scope

In layman terms, scope is a fancy way of saying that you can override variables on a per class basis without messing up all your global variable settings.

```
@default-color: black;

/* Makes a tags red */
a {
    color: @default-color;
    @default-color: red;
}

/* h1s are still black */
h1 {
    color: @default-color;
}


```
# What is Sass?

Sass (Syntactically Awesome Style Sheets) is a CSS preprocessor.

# Whats the deal with .sass vs .scss?

When .Sass first came out, the main syntax was noticably different from CSS. It used indentation instead of braces, didn't require semi-colons and had shorthand operators.

In version 3 Sass changed it's main syntax to .scss. SCSS is a superset of CSS, and is basically written the exact same, but with all the fun new Sass features.


# Why would I use Sass?

Sass makes writing maintainable CSS easier. You can get more done, in less code, more readably, in less time.

# Variables in sass
Sass brings variables to CSS. Acceptable values for variables include numbers, strings, colors, null, lists and maps.

Variables in Sass are scoped using the $ symbol.
```

//If you tried to compile this and didn't see anything in your CSS
$primaryColor: #eeffcc;


// It will generate body with background

$primaryColor: #eeffcc;

body {
    background: $primaryColor;
}



```
# Sass variable scope

if you declare a variable within a selector, it is then scoped within that selector. 

```
$primaryColor: #eeccff;

body {
  $primaryColor: #ccc;
  background: $primaryColor;
}

p {
  color: $primaryColor;
}

// When compiled, our paragraph selector's color is #eeccff


```
# Global Scope variable

Sass provides a !global flag that comes to our rescue.

```
$primaryColor: #eeccff;

body {
  $primaryColor: #ccc !global;
  background: $primaryColor;
}

p {
  color: $primaryColor;
}

// When compiled, our paragraph selector's color is #ccc



```
# What is SASS(Syntactically Awesome StyleSheets)?
-	Dynamic Style Sheet Language.
-	Compiles to CSS
-	Introduces programming features to CSS
# What is SASS?(2)
It has two syntaxes 
1.	SASS
```
$baseFontSize: 14px

#main
h1
    font-size: $baseFontSize


```


2.	SCSS
```
$baseFontSize: 14px;
#main
{
     h1
	{
	font-size: $baseFontSize;
	}
}
```

# SASS on the server
-	Support for server-side
. 	Node.js
```
npm install sass


var less = require(‘sass’);

sass.render(sassContents, function(e, css){
console.log(css);
});

```
. 	ASP.NET

```
1.	# Chirpy
//It does Design time compilation
// Files should be name “foo.chirpy.sass”

2.	# Nuget
Install-package SassAndCoffe

```
.	Otherr ways for Rails, JSP etc.


# Variables
```
$myColor: #ffeedd;

$a: Black;			// Color
$b: 4px;				//Units
$c: 1.0em;			//Units
$d: Helvetica, sans-serif;	//Lists
$e: 1px #000 Solid 0 0;		//Lists

```
# Operations 
```
font-size:  4px + 4;		//8px
font-size:  20px * .8;		//16px
color:  #FFF / 4;			//#404040;
width: (100% / 2) + 25%;	//75%
```
# Color Functions
```
color: lighten($color, 10%);
color: darken($color, 10%);

color: saturate($color, 10%);
color: desaturate($color, 10%);

color: fade_in($color, .1);
color: fade_out($color, .1);

color: invert($color);
color: complement($color);

$quoted: quote($sometext);
$unquoted: unquote($sometext);

$value: if(true, $color1, $color2);
```


# default value for a variable

when writing mixins, is the !default flag. This allows us to make sure there is a default value for a variable in the event that one is not provided. If a value is provided, it is overwritten.

```
$firstValue: 62.5%;

$firstValue: 24px !default;

body {
    font-size: $firstValue;
}

// body font size = 62.5%


```

# Math

Unlike CSS, Sass allows us to use mathematical expressions! This is super helpful within mixins, and allows us to do some really cool things with our markup.

```
+  Addition  
-  Subtraction  
/  Division  
*  Multiplication  
%  Modulo  
==  Equality  
!=  Inequality  
```
- Before moving forward, I want to note two potential "gotchas" with Sass math.

1. First, because the / symbol is used in shorthand CSS font properties like font: 14px/16px, if you want to use the division operator on non-variable values, you need to wrap them in parentheses like:

```
$fontDiff: (14px/16px);

```
2. Second, you can't mix value units:as it needs to be interpereted at render time.

```
// This wont work and compiled to same.
$container-width: 100% - 20px;


// Right way to do calculation with different unit

$container-width:calc(100% - #{20px})


$container-width:calc(100% - #{$body_padding})


```
# dynamic column declaration, based upon a base container width.

```
$container-width: 100%;

.container {
  width: $container-width;
}

.col-4 {
  width: $container-width / 4;
}

//  Compiles to:
//  .container {
//   width: 100%;
//  }
//
//  .col-4 {
//      width: 25%;
//  }

```
# Functions

The best part of Sass is it has built in functions.

```
- (Sass::Script::Value::Number) abs($number)   
Returns the absolute value of a number.
 

- (Sass::Script::Value::Color) adjust_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])   
Increases or decreases one or more properties of a color.
 

- (Sass::Script::Value::Color) adjust_hue($color, $degrees)   
Changes the hue of a color.
 

- (Sass::Script::Value::Number) alpha($color)   
Returns the alpha component (opacity) of a color.
 

- (Sass::Script::Value::List) append($list, $val, $separator:auto)   
Appends a single value onto the end of a list.
 

- (Sass::Script::Value::Number) blue($color)   
Gets the blue component of a color.
 

- call($function, $args...)   
Dynamically calls a function.
 

- (Sass::Script::Value::Number) ceil($number)   
Rounds a number up to the next whole number.
 

- (Sass::Script::Value::Color) change_color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha])   
Changes one or more properties of a color.
 

- (Sass::Script::Value::Bool) comparable($number1, $number2)   
Returns whether two numbers can added, subtracted, or compared.
 

- (Sass::Script::Value::Color) complement($color)   
Returns the complement of a color.
 

- (Sass::Script::Value::Bool) content_exists   
Check whether a mixin was passed a content block.
 

- (Sass::Script::Value::String) counter($args...)   
This function only exists as a workaround for IE7's content: counter bug.
 

- (Sass::Script::Value::String) counters($args...)   
This function only exists as a workaround for IE7's content: counter bug.
 

- (Sass::Script::Value::Color) darken($color, $amount)   
Makes a color darker.
 

- (Sass::Script::Value::Color) desaturate($color, $amount)   
Makes a color less saturated.
 

- (Sass::Script::Value::Bool) feature_exists($feature)   
Returns whether a feature exists in the current Sass runtime.
 

- (Sass::Script::Value::Number) floor($number)   
Rounds a number down to the previous whole number.
 

- (Sass::Script::Value::Bool) function_exists($name)   
Check whether a function with the given name exists.
 

- (Sass::Script::Value::Function) get_function($name, $css:false)   
Returns a reference to a function for later invocation with the call() function.
 

- (Sass::Script::Value::Bool) global_variable_exists($name)   
Check whether a variable with the given name exists in the global scope (at the top level of the file).
 

- (Sass::Script::Value::Color) grayscale($color)   
Converts a color to grayscale.
 

- (Sass::Script::Value::Number) green($color)   
Gets the green component of a color.
 

- (Sass::Script::Value::Color) hsl($hue, $saturation, $lightness)   
Creates a Color from hue, saturation, and lightness values.
 

- (Sass::Script::Value::Color) hsla($hue, $saturation, $lightness, $alpha)   
Creates a Color from hue, saturation, lightness, and alpha values.
 

- (Sass::Script::Value::Number) hue($color)   
Returns the hue component of a color.
 

- (Sass::Script::Value::String) ie_hex_str($color)   
Converts a color into the format understood by IE filters.
 

- (Sass::Script::Value::Base) if($condition, $if-true, $if-false)   
Returns one of two values, depending on whether or not $condition is true.
 

- (Sass::Script::Value::Number, Sass::Script::Value::Null) index($list, $value)   
Returns the position of a value within a list.
 

- (Sass::Script::Value::String) inspect($value)   
Return a string containing the value as its Sass representation.
 

- (Sass::Script::Value::Color) invert(color, weight = number(100))   
Returns the inverse (negative) of a color.
 

- (Sass::Script::Value::Bool) is_bracketed($list)   
Returns whether a list uses square brackets.
 

- (Sass::Script::Value::Bool) is_superselector($super, $sub)   
Returns whether $super is a superselector of $sub.
 

- (Sass::Script::Value::List) join($list1, $list2, $separator:auto, $bracketed:auto)   
Joins together two lists into one.
 

- (Sass::Script::Value::Map) keywords($args)   
Returns the map of named arguments passed to a function or mixin that takes a variable argument list.
 

- (Sass::Script::Value::Number) length($list)   
Return the length of a list.
 

- (Sass::Script::Value::Color) lighten($color, $amount)   
Makes a color lighter.
 

- (Sass::Script::Value::Number) lightness($color)   
Returns the lightness component of a color.
 

- (Sass::Script::Value::String) list_separator($list)   
Returns the separator of a list.
 

- (Sass::Script::Value::Base) map_get($map, $key)   
Returns the value in a map associated with the given key.
 

- (Sass::Script::Value::Bool) map_has_key($map, $key)   
Returns whether a map has a value associated with a given key.
 

- (List) map_keys($map)   
Returns a list of all keys in a map.
 

- (Sass::Script::Value::Map) map_merge($map1, $map2)   
Merges two maps together into a new map.
 

- (Sass::Script::Value::Map) map_remove($map, $keys...)   
Returns a new map with keys removed.
 

- (List) map_values($map)   
Returns a list of all values in a map.
 

- (Sass::Script::Value::Number) max($numbers...)   
Finds the maximum of several numbers.
 

- (Sass::Script::Value::Number) min($numbers...)   
Finds the minimum of several numbers.
 

- (Sass::Script::Value::Color) mix($color1, $color2, $weight:50%)   
Mixes two colors together.
 

- (Sass::Script::Value::Bool) mixin_exists($name)   
Check whether a mixin with the given name exists.
 

- (Sass::Script::Value::Base) nth($list, $n)   
Gets the nth item in a list.
 

- (Sass::Script::Value::Color) opacify($color, $amount)  (also: #fade_in)  
Makes a color more opaque.
 

- (Sass::Script::Value::Number) opacity($color)   
Returns the alpha component (opacity) of a color.
 

- (Sass::Script::Value::Number) percentage($number)   
Converts a unitless number to a percentage.
 

- (Sass::Script::Value::String) quote($string)   
Add quotes to a string if the string isn't quoted, or returns the same string if it is.
 

- random(limit = nil)   


- (Sass::Script::Value::Number) red($color)   
Gets the red component of a color.
 

- (Sass::Script::Value::Color) rgb($red, $green, $blue)   
Creates a Color object from red, green, and blue values.
 

- rgba(*args)   
Creates a Color from red, green, blue, and alpha values.
 

- (Sass::Script::Value::Number) round($number)   
Rounds a number to the nearest whole number.
 

- (Sass::Script::Value::Color) saturate($color, $amount)   
Makes a color more saturated.
 

- (Sass::Script::Value::Number) saturation($color)   
Returns the saturation component of a color.
 

- (Sass::Script::Value::Color) scale_color($color, [$red], [$green], [$blue], [$saturation], [$lightness], [$alpha])   
Fluidly scales one or more properties of a color.
 

- (Sass::Script::Value::List) selector_append($selectors...)   
Return a new selector with all selectors in $selectors appended one another as though they had been nested in the stylesheet as $selector1 { &$selector2 { ... } }.
 

- (Sass::Script::Value::List) selector_extend($selector, $extendee, $extender)   
Returns a new version of $selector with $extendee extended with $extender.
 

- (Sass::Script::Value::List) selector_nest($selectors...)   
Return a new selector with all selectors in $selectors nested beneath one another as though they had been nested in the stylesheet as $selector1 { $selector2 { ... } }.
 

- (Sass::Script::Value::List) selector_parse($selector)   
Parses a user-provided selector into a list of lists of strings as returned by &.
 

- (Sass::Script::Value::List) selector_replace($selector, $original, $replacement)   
Replaces all instances of $original with $replacement in $selector.
 

- (Sass::Script::Value::List, Sass::Script::Value::Null) selector_unify($selector1, $selector2)   
Unifies two selectors into a single selector that matches only elements matched by both input selectors.
 

- (Sass::Script::Value::List) set   
Return a new list, based on the list provided, but with the nth element changed to the value given.
 

- (Sass::Script::Value::List) simple_selectors($selector)   
Returns the simple selectors that comprise the compound selector $selector.
 

- (Sass::Script::Value::Number, Sass::Script::Value::Null) str_index($string, $substring)   
Returns the index of the first occurrence of $substring in $string.
 

- (Sass::Script::Value::String) str_insert($string, $insert, $index)   
Inserts $insert into $string at $index.
 

- (Sass::Script::Value::Number) str_length($string)   
Returns the number of characters in a string.
 

- (Sass::Script::Value::String) str_slice($string, $start-at, $end-at:-1)   
Extracts a substring from $string.
 

- (Sass::Script::Value::String) to_lower_case($string)   
Convert a string to lower case,.
 

- (Sass::Script::Value::String) to_upper_case($string)   
Converts a string to upper case.
 

- (Sass::Script::Value::Color) transparentize($color, $amount)  (also: #fade_out)  
Makes a color more transparent.
 

- (Sass::Script::Value::String) type_of($value)   
Returns the type of a value.
 

- (Sass::Script::Value::String) unique_id   
Returns a unique CSS identifier.
 

- (Sass::Script::Value::String) unit($number)   
Returns the unit(s) associated with a number.
 

- (Sass::Script::Value::Bool) unitless($number)   
Returns whether a number has units.
 

- (Sass::Script::Value::String) unquote($string)   
Removes quotes from a string.
 

- (Sass::Script::Value::Bool) variable_exists($name)   
Check whether a variable with the given name exists in the current scope or in the global scope.
 

- (Sass::Script::Value::List) zip($lists...)   
Combines several lists into a single multidimensional list.
 
```


[Examples](http://sass-lang.com/documentation/Sass/Script/Functions.html)

# Nesting
Basic nesting refers to the ability to have a declaration inside of a declaration.


```
.container {
    width: 100%;
    h1 {
        color: red;
    }
}


// After compile
.container {
    width: 100%;
}

.container h1 {
    color: red;
}



```

# Reference the parent "&" ?

This is achieved by using the & symbol. Check out how we can leverage this to add pseudo selectors to anchor elements:

```
a.myAnchor {
    color: blue;
    &:hover {
        text-decoration: underline;
    }
    &:visited {
        color: purple;
    }
}



```

# de-nest

if we want to de-nest, we have to use the @at-root directive.




# @at-root

The @at-root directive, introduced with Sass 3.3, emits a collection of nested rules at the top-level root of the document. 
```
.container {
  &-inner { color: black
    @at-root .no-touchevents #{&}:hover { color: grey }
  }
}

// Which compiles to (awesome):

.container-inner { color: black }
.no-touchevents .container-inner:hover { color: grey }


```

# Imports
imports allow you to break your styles into separate files and import them into one another. 

We can import a .scss file using the @import directive:

```
@import "grids.scss";
or

@import "grids";

```

# Extends @extend
In Sass, the @extend directive is an outstanding way to inherit already existing styles.

Lets use an @extend directive to extend an input's style if it has an input-error class:

```
.input {
  border-radius: 3px;
  border: 4px solid #ddd;
  color: #555;
  font-size: 17px;
  padding: 10px 20px;
  display: inline-block;
  outline: 0;
}

.error-input {
  @extend .input;
  border:4px solid #e74c3c;
}




```

# Placeholder selector by prefixing a class name with a %

If we want to extend a declaration with a set of styles then we can use Placeholder

```


%input-style {
    font-size: 14px;
}

input {
    @extend %input-style;
    color: black;
}




``` 

# Mixins

The mixin directive allows you to include styles the same way @extend would, but with the ability to supply and interperet arguments.

Sass uses the @mixin directive to define mixins, and the @include directive to use them. Lets build a simple mixin that we can use for media queries!

first step is to define our mixin:
```
@mixin media($queryString){

}


```
Notice we are calling our mixin media and adding a $queryString argument. When we include our mixin, we can supply a string argument that will be dynamically rendered.

```
@mixin media($queryString){
    @media #{$queryString} {
      @content;
    }
}


```
Because we want our string argument to render where it belongs, we use the Sass interpolation syntax, #{}. When you put a variable in between the braces, it is printed rather than evaluated.

Another piece of our puzzle is the @content directive. When you wrap a mixin around content using braces, the wrapped content becomes available via the @content directive.

Finally, lets use our mixin with the @include directive:

```
.container {
    width: 900px;
    @include media("(max-width: 767px)"){
        width: 100%;
    }
}


```
Example

```
@mixin flex {
    // write the css here
    display: -webkit-flex;
    display: flex;
}

// Calling

.row {
    @include flex;
}
```
Example 2

$values doesn't get treated as a list but rather a normal variable.
```
@mixin padding($values...) {    
    @each $var in $values {
        padding: #{$var};
    }
}

a {
    @include padding(2px 4px 6px);
}
// After Compile
a {
    padding: 2px 4px 6px;
}


```
Example 3
Default Mixin Arguments
```
@mixin grid($flex) {
    @if $flex {
        @include flex;
    } @else {
        display: block;
    }
}

@mixin grid($flex: true, $max-width) {
    // code here
}

```


# Function Directives
Function directives in Sass are similar to mixins, but instead of returning markup, they return values via the @return directive.

```
@function getColumnWidth($width, $columns,$margin){
    @return ($width / $columns) - ($margin * 2);
}


$container-width: 100%;
$column-count: 4;
$margin: 1%;

.container {
  width: $container-width;
}

.column {
  background: #1abc9c;
  height: 200px;
  display: block;
  float: left;
  width: getColumnWidth($container-width,$column-count,$margin);
  margin: 0 $margin;
}



```


# cascading stylesheet/CSS execution order
The browser encounters these rules, whichever one is interpreted last gets the highest precedent.
So if you have multiple class to same elements the last one will be present applied.

Sass in the real world (Book 1 of 4)  
http://anotheruiguy.gitbooks.io/sassintherealworld_book-i/ 

Sass in the real world (Book 2 of 4)  
 http://anotheruiguy.gitbooks.io/sass-in-the-real-world-book-2-of-4/  

 Sass for web designers  
 http://www.abookapart.com/products/sass-for-web-designers  

 Sass & Compass for web designers  
http://sassandcompass.com/ 

 Pragmatic Guide to Sass  
 https://pragprog.com/book/pg_sass/pragmatic-guide-to-sass

 Sass and Compass in Action  
 http://www.manning.com/netherland/ 

Sass and Compass Resources

Book collection

https://github.com/wikisoft/collection/tree/master/public

https://github.com/imkrimerman/javascript-ebooks
=====================================================

***ONLINE***

> Official: http://sass-lang.com
> Official: http://compass-style.org
> http://thesassway.com


***TUTORIALS***

> http://fuelyourcoding.com/35-great-resources-for-compass-and-sass/
> http://net.tutsplus.com/tutorials/other/mastering-sass-lesson-1/
> http://net.tutsplus.com/tutorials/html-css-techniques/mastering-sass-lesson-2/
> http://net.tutsplus.com/tutorials/html-css-techniques/mastering-sass-lesson-3/
> http://sonspring.com/journal/sass-for-designers
> http://www.netmagazine.com/tutorials/code-smarter-css-sass
> http://net.tutsplus.com/tutorials/html-css-techniques/using-compass-and-sass-for-css-in-your-next-project/
> http://www.netmagazine.com/tutorials/faster-button-styling-sass
> http://www.netmagazine.com/tutorials/improve-your-responsive-design-workflow-sass

>> For WordPress: http://technosailor.com/2011/11/02/tutorial-using-sass-and-compass-for-managing-css-in-wordpress/


***BOOKS***

> Sass and Compass in Action: http://www.manning.com/netherland/
> Pragmatic Guide to Sass: http://pragprog.com/book/pg_sass/pragmatic-guide-to-sass

***COMPASS & SASS RELATED PROJECTS***

> Foundation: http://foundation.zurb.com/
> Sencha Touch: http://www.sencha.com/products/touch/

***VIDEOS, PRESENTATIONS, SLIDES***

> Kicking Ass & Taking Names with Sass and Compass: http://vimeo.com/24278115
> Drupal & Compass: https://speakerdeck.com/u/nathansmith/p/drupal-compass
> Compass, Sass & the Enlightened Developer: http://www.slideshare.net/pengwynn/compass-sass-and-the-enlightened-css-developer
> Authoring Stylesheets with Sass and Compass: http://www.slideshare.net/chriseppstein/authoring-stylesheets-with-compass-sass

***HANDY ADD-ONS, AND OTHER MISCELLANY***

> Compass Recipes: https://github.com/MoOx/compass-recipes
> Breakpoint (easy media queries in Compass): https://github.com/canarymason/breakpoint

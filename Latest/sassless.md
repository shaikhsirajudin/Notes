# Explain what is Sass? How it can be used?
Sass stands for Syntactically Awesome Stylesheets and was created by Hampton Catlin. It is an extension of CSS3, 
adding nested rules, mixins, variables, selector inheritance, etc.
Sass can be used in three ways
•As a command line tool
•As a standalone Ruby module
•As a plugin for any Rack-enabled framework

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
•Sass is easy to learn especially for them who has a background of Python, Ruby or Coffescript and place using functions, writing mixins
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

# List out alternatives against LESS?
•SASS: Syntactically Awesome Stylesheets
•SCSS: Version.2 of SASS
•Stylus

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

# What is HTML5?
HTML5 is a markup language used for structuring and presenting content on the web.
e.g.
```
<html>
	<body>
		<header>.... </header>
		<main>.... </main>
		<footer>... </footer>

	</body>
</html>

```
Before HTML5, all we had to work with was general containers and this was a problem for search engines.
```
<html>
	<body>
		<div id="header">.... </div>
		<div id="main">.... </div>
		<div id="footer">.... </div>

	</body>
</html>

```
By only have generic elements like div for division, or a span which is used to use for displaying content, but seach engines couldnt be as accurate to find most important parts of the page to index.
Big part of HTML5 is the addition of containers or HTML elements those are very specific about the purpose and intent of the content describing.

# So HTML5 is the combination of

- New Elements
- New Attributes to existing elements 
- New Javascript APIs implemented in the browser.

# History of HTML5
- Proposal for HTML in 90 by TIM Berners-Lee along with first broswer and first server software.
- After evolution and development of HTMl as formalized in the foundation of World Wide Web consortium or W3C. This is the first HTML specification
- As the development continue the first malor changes to HTML comes in the form of HTML4. With this it was possible to build animation and true interactivity in web application.
- XHTML, this turned out to be a bit of a mistake, The whole aim of XHTML was to make HTML more strict. Therefore its harder for people and machines to work with. This is the first sign heade towards wrong path.

- HTML WG(HTML working group) was formed but this proved to be a short-lived endeavor.
- WHAT WG(web hypertext application technology working group) was formed with the express intent of continuing to push HTML forward, and it helps to push the web forward, while at the same time ensuring quality and standardization of the spec.
The WHATWG decide to do is work and collaborate on whta we now think of as HTML5.

- HTML5:  WHATWG announces that it will not work on named versions of HTML, it means instead of planning for HTML6..7 , the HTML spec is now a living standard, this move makes a lot of sense if you think about it.Browser will develop new feature as they pan, With HTML5 you have a set of functionality . HTML5 no longer exists means that the latest and greatest version of HTML is simply not numbered.


# Standards Bodies
There are number of different standards bodies involved in creating the specification of HTML/5
- W3C
- WHATWG
- ECMAScript.

[HTML5 Platform](https://platform.html5.org/)

[HTML5 Migration](https://www.w3schools.com/html/html5_migration.asp)


![New Semantic/Structural Elements](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/html5-semantic.PNG)


Tag Description
```
<article> Defines an article in a document 
<aside> Defines content aside from the page content 
<bdi> Isolates a part of text that might be formatted in a different direction from other text outside it 
<details> Defines additional details that the user can view or hide 
<dialog> Defines a dialog box or window 
<figcaption> Defines a caption for a <figure> element 
<figure> Defines self-contained content 
<footer> Defines a footer for a document or section 
<header> Defines a header for a document or section 
<main> Defines the main content of a document 
<mark> Defines marked/highlighted text 
<menuitem>  Defines a command/menu item that the user can invoke from a popup menu 
<meter> Defines a scalar measurement within a known range (a gauge) 
<nav> Defines navigation links 
<progress> Represents the progress of a task 
<rp> Defines what to show in browsers that do not support ruby annotations 
<rt> Defines an explanation/pronunciation of characters (for East Asian typography) 
<ruby> Defines a ruby annotation (for East Asian typography) 
<section> Defines a section in a document 
<summary> Defines a visible heading for a <details> element 
<time> Defines a date/time 
<wbr> Defines a possible line-break 
```

# New Form Elements
```
<datalist> Specifies a list of pre-defined options for input controls 
<output> Defines the result of a calculation

```
# New Input Types
```
•color
•date
•datetime
•datetime-local
•email
•month
•number
•range
•search
•tel
•time
•url
•week
```


# New Input Attributes

```
•autocomplete
•autofocus
•form
•formaction
•formenctype
•formmethod
•formnovalidate
•formtarget
•height and width
•list
•min and max
•multiple
•pattern (regexp)
•placeholder
•required
•step

```
# New Attribute Syntax
HTML5 allows four different syntaxes for attributes.
```
Empty: <input type="text" value="John" disabled> 
Unquoted: <input type="text" value=John> 
Double-quoted: <input type="text" value="John Doe"> 
Single-quoted: <input type="text" value='John Doe'> 


```
# HTML5 Graphics
```
<canvas> Draw graphics, on the fly, via scripting (usually JavaScript) 
<svg> Draw scalable vector graphics 


```
# New Media Elements
```
<audio> Defines sound content 
<embed> Defines a container for an external (non-HTML) application 
<source> Defines multiple media resources for media elements (<video> and <audio>) 
<track> Defines text tracks for media elements (<video> and <audio>) 
<video> Defines video or movie 
```
# Structural Elements
## main
The main element is used to wrap the main content of the page. By way of contrast, navigation links in the header,copyright information, and other such secondary content wrould not be in the main element.

## article
Inside the main element you may find the article element.
It can be use to group together information signaling to the search engine that the content inside is really important as opposed to content that might be surrounding it.
We can have more than one article element on the page. This doent not change look, feel or the behavior of the content in the browser, but it gives the semantic meaning to the content.

## aside

It is used to flag content that might be important, but maybe not as necessary as the rest of the content of the page.

## section
Content can be logically grouped together using section, Its bit like the div element to group related content.

## nav
one of the most common element found in the header and footer element is nav element, the nave element is a logical container for site navigation.

* Examples

```
<body>
<header>
	<h1>Monday Times</h1>
</header>
<nav>
	<ul>
		<li>News</li>
		<li>Sports</li>
		<li>Weather</li>
	</ul>
</nav>
<main>
<article>
	<section>
		<h2>News Section</h2>
		<article>
			<h2>News Article</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque in porta lorem. Morbi condimentum est nibh, et consectetur tortor feugiat at.</p>
		</article>
		<article>
			<h2>News Article</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque in porta lorem. Morbi condimentum est nibh, et consectetur tortor feugiat at.</p>
		</article>
	</section>
	<aside>
	...
	</aside>
</article>
</main>
<footer>
<nav>
....
</nav>
<p>&copy; 2014 Monday Times. All rights reserved.</p>
</footer>

</body> 

```
## time
Can be used to specify just a time, just a date, or a specific datetime, this element includes the optional pubdate attribute.
Single web page may only have one time element with the "pubdate" attribute present.
* syntax
```
<time date="2016-08-12" pubdate>
August 12,2016
</time>
```

## figure , figcaption
These elements are meant to provide semantic meaning to search engines for images and diagrams. As you can associate a caption with an image, search engine has better understanding  as what in the image as the caption is logically linked to the figure.

syntax
```
<figure>
	<figcaption>
	Screenshot of Menu
	<figcaption>
	<img src="screenshot.png">
</figure>

```
## details, summary

This is a no-Javascript way of adding just a little bit of interactivity to the page. When user click on Events it will toggle contents.

syntax
```
<details>
	<summary>Events</summary>
	<p>Come join us.</p>
</details>
```
## mark
The mark element is intended to be used to wrap text in search reasult to highlight the matched term, it provides semantic meaning to the matched term.

syntax
```
<mark>
Highlighted text
</mark>

```
## bdi
Bidirectional isolated element, it is used for content when you need to change the horizontal direction from the surrounding text.


syntax
```
<bdi>
arbic text you want to show
</bdi>

```
## wbr(wordbreak)
If you have really long word then we can use it, this element tells the browser where to hyphenate. 

e.g. Honorificabili....
syntax
```
Honorificabili<wbr>tudinitatibus
```
## output
To display the results of some sort of calculation. e.g calculator.
syntax
```
<output>
</output>
```
## embed
It is to be a host container for external plugins

syntax
```
<embed src="intro.mov"  >
```

# Elements with APIs

## canvas
It is use for drawing on the page.
e.g. Drawing shapes, Charts, and more.

## video, source, track

now a day its commonly used for smart devices


syntax 
```
--<audio>
<video>
 <source src="vid.mp3">
 <source src="vid.ogg">
 <source src="vid.webm">
 <track

kind ="subtitles"
label="spanish subtitles"
src="es.vtt"
 srclng="eng">

<video>

```
# Form Elements

## meter

It is used to demonstrate the value between a threshold of values.
we can use it to represent battery power, oroduct ratings...

syntax
```
<meter min="0" min="100" min="70">
70 0ut of 100
</meter>

```

## progress

It depict to show how far along you are in an applicattion process.

syntax
```
<progress max="100" value="50">
</progress>

```

## math

This allow formulas or math elements to render them on the page as you might expect them to look in a text book.

syntax
```
<math>
<!-- mathML elements -->
</math>
```

## datalist

This shows as options in an input field. This provide users with an editable drop-down list.

syntax

```
<input type="text" list="colors" min="70">

<datalist id="colors" >
<option id="yellow">
<option id="green">
<option id="red">

</datalist>
```


# New Javascript APIs
In HTML5 much of advancements are found on webplatform are found in Javascript APIs.

## Graphics and Typography

- Canvas
html canvas is a combination of both HTML and the javascript API.It give full control to draw on an HTML page

## Interaction, Events and Messaging.
It makes big difference in the functionality in user experience of your applications.

- Barrery Status: 
this give us to opportunity how our application behaves at different levels of power.

- Clipboard API & Events: 
It provide programmatic access to the clipboard. 

- Cross Document Messaging:
In some cases we want to send message froma page on site A to a page on site B. The cross document messaging API will allow you to do it.


- Device and Screen Orientation:
In smart devices some time you want application to be able to respond to changes in the orientation of the device or screen.
This provide events to respond to recognized movement.

- Fullscreen API
Game,kiosk app or just want to a clean user experience. This API give you the control to make your app fill the entire client screen.

- Geolocation:
We can find the users location by using geolocation API in mobile or smart devices.

- Media Capture:
This API grants you programmatic access to antive devices to capture media.

- Notification API:
It give you ability to create toast-like pop-up notifications on the desktop 
- Touch Events
in mobile devices you can get access to touch events so you can respond to different types of gestures.
- Vibration
This group is a way to control the vibration capabilities of the device.





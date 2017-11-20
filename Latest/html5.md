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

![HTML5 Platform](https://platform.html5.org/)

![HTML5 Migration](https://www.w3schools.com/html/html5_migration.asp)


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


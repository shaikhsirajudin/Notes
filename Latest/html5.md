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
- After evolution and development of HTML as formalized in the foundation of World Wide Web consortium or W3C. This is the first HTML specification
- As the development continue the first major changes to HTML comes in the form of HTML4. With this it was possible to build animation and true interactivity in web application.
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

- Canvas: 
html canvas is a combination of both HTML and the javascript API.It give full control to draw on an HTML page

## Interaction, Events and Messaging.
It makes big difference in the functionality in user experience of your applications.

- Battery Status:  
this give us to opportunity how our application behaves at different levels of power.

- Clipboard API & Events:  
It provide programmatic access to the clipboard. 

- Cross Document Messaging: 
In some cases we want to send message froma page on site A to a page on site B. The cross document messaging API will allow you to do it.


- Device and Screen Orientation: 
In smart devices some time you want application to be able to respond to changes in the orientation of the device or screen.
This provide events to respond to recognized movement.

- Fullscreen API: 
Game,kiosk app or just want to a clean user experience. This API give you the control to make your app fill the entire client screen.

- Geolocation: 
We can find the users location by using geolocation API in mobile or smart devices.

- Media Capture: 
This API grants you programmatic access to antive devices to capture media.

- Notification API: 
It give you ability to create toast-like pop-up notifications on the desktop 
- Touch Events: 
in mobile devices you can get access to touch events so you can respond to different types of gestures.
- Vibration: 
This group is a way to control the vibration capabilities of the device.

# Storage and Files
Number of different APIs availabe this.

- Blob URLs: 
Blobs represent data in chunks of bites. So blobs are a very low-level way of representing data in the browser.
- File API
Instances of the File class represent actual files in the browser's file system.
- File Reader: 
This class provides a way for you to read in-browser file data that can come in a few different forms.
- IndexedDB: 
The IndexedDB API is a sophisticated object where document database is implemented entirely in the broswer.If you have large sets of datta that you need to store and query on the client then IndexedDB is a great.
- Local Storage: 
If you needs is little bit more basic then Local Storage is good.With this we have the option to store data for long periods of time or just for the session and sessions are determined by the lifespan of a browser tab. Each API uses same interface so working with local storage is very easy.

# Real-Time Communication APIs.

- Push API: 
This API gives you the opportunity to push data from the server to client it also give other flexibility. Data can be pushed to the broswer even when it's running in the background on the computer. This will improves the performance of application that need real-time data from the server.

-  Server-Sent Events: 
It also similar in nature to Push but distinct technologies and address the need for the client to receive messages directly from the server but achieve it in different ways.
It work with a one-way channel of communication from the server to the client and messages are sentt via HTTP, which means there's no specialized server technology required.

- Web Sockets: 

It also similar in nature to Push but distinct technologies and address the need for the client to receive messages directly from the server but achieve it in different ways.
It facilitate two-way communications and work under custom communications protocol.


# Web Components

It enables developer to take control over the markup created for a website.

- Custom Elements: 
Custom elements gives you the chance to change a series of nested generic elements like a div and span and turn that into custom named elements that better represent the meaning and intent of the markup.


General
```
<div id="comment-container">
<div class="comment">
 <div class="user-info-container">
<div class="user-name">Criag Shoemakerr</div>
<div class="avatar"><img src=cs.png" alt="Craig shoemaker" /></div>
</div>
<div class="content-container">
<div class="publish-date">12/01/2016</div>
<div class="content">HTML is the set of markup enhancements and  new Javascript APIs</div>
</div>
</div>
</div>

```
Similar result you might achieve using Custom Elements.

```
<comments>

<comment author="Craig Shoemaker" avatarUrl="cs.png" publishDate="12/01/2016" >
HTML is the set of markup enhancements and  new Javascript APIs
</comment>
</comments>

```
This customization of elements begins to provide encapsulation of not only content but also the underlying DOM elements that make up this custom element.

- Shadow DOM: 

When we talk about creating boundaries around the DOM tree, we are actually talking about is the Shadow DOM.
The Shadow DOM is simply a way to encapsulate element trees in the DOM. What this means is that you can apply CSS and Javascript to elements contained in the Shadow DOM. It won't leak out the affect to the rest of the page. 
This is the heart of web components, in that you have Custom Elements with a self-contained structure,style, and javascript logic.

- Templates: 
There are different forms of templates are present since long through the use of javacript library or other. This make templates common in the browser. 
The way to create a pattern of HTML and easily fill it with data before displaying it on the screen.


# Perfromance Optimization and Analysis APIs

We can performance using 

- High Resolution Time API: 
The High resultion time API gives you the opportunity to measure time with sub-millisecond accuracy. This is great for measuring operations and calculations.

- User Timing: 
If you are using this API then High Resolution Time API pay OFF.
In this API we have a simple interface available to create timing boundaries inside your code giving you an easy way to measure at a high resolution how your application performs.

- Navigation Timing API: 
The page load time can be measure by using it, you can find out how the user navigated to your page and are able to respond to custom events related to the page load lifecycle.

- Page Visibility API: 
If you want your page to behave differently when it isnt the active tab in the broswer e.g. pause music or video etc. 
This API allow you to respond to changes in the page's visibility based on the tab state.


- Web Workers: 
In this you have a chance to get huge performance gains by using different threads in the browser. When you create a web worker, the execution context is in an entirely separate thread in the browser. These extra threads are completely independent of the UI thread.


# Security and Privacy
One of the most basic attacks on a website is the cross-site scripting attach where foreign scripts are introduced into a page that compromises the security of a web application. To mitigate these attacks.

- Content Security Policy: 
It allows you to create a whitelist for sources of a page including scripts and styles.

- Referrer Policy: 
It gives you tighter control over the amount of data that's transmitted through the HTTP refferrer.

- Web Cryptography API: 
This API provides a way to encrypt and decript datta entirely on the client.

# Miscellaneous API

- Scripts: async & defer

 For script elements, there are two new Boolean attributes available.
 
 . async: 
  The async feature allows a cript to run in an asynchronous manner so that it won't block the execution of the page.
 
 .defer: 

The defer slices it a little bit differently. The attribute ensures that the script execution is deferred to after the page load.

- contentEditable: 

The contentEditable attribute, which allows any element to be switched into an edit mode so that virtually any part of your page can be an eidtor.

- Drag & Drop: 
The Drag and Drop API makes it easy to implement drag and drop behaviors with a native broswer API.

- History: 
This API allows you to take control of the browser's location by giving you a chance to make changes to it without requiring a tip back to the server.
It also allow you to make changes to the actual browser history by using additions to the History API.


- Promises: 
Promises is a huge win for web developers. By having a native Promises API available, you can easily write asynchronous code in a clean and clear manner.

- Service Workers: 
Its relative new comer to the HTML5 family of APIs,It replaced the previous Application Cache API. The intent around Application Cache was that you could create an offline web application by maintaining a list of all the files needed to run while offline. But that implementation proved to be too brittle in just about everry browser. Therefore, the service worker API was created to address many of the shortcomings of the application cache with an entirely new API and implementation.

Note: If you need your website to work offline, you are looking for service workers.

# HTML4 vs HTML5
# HTML4 page

- DOCTYPE: 
In HTML4 uses a Transitional DOCTYPE to interpret html in the browsers.
- XHTML: 
It uses xmlns namespace to direct the broswer how to interpret the markup and what sort of rules to enforce as it's interpreting the page.

- style / script tags: 

For style and script tag we need to specify the content type to text/css or text/javascript

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">

    <head>
        <title>HTML4 Example</title>
        
        <link rel="icon" type="image/png" href="img/favicon.png">
        
        <link rel="stylesheet" href="css/bootstrap.css" type="text/css" />
        <link rel="stylesheet" href="css/site.css" type="text/css" />
        
        <style type="text/css">
            body {
                background-color: #fff;
            }
        </style>
        
        <script type="text/javascript">
            console.log('HTML4 Example loaded');
        </script> 
    </head>
	<body>

        <div id="header">
        <!-- Fixed navbar -->
            <div class="navbar navbar-inverse navbar-fixed-top">
            <div class="container">
                <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="index.html">
                    <img src="img/html5-fundamentals.png" title="HTML5 Fundamentals" class="hidden-sm" />
                    <img src="img/html5.png" title="HTML5 Fundamentals" class="visible-sm" />
                </a>
                </div>
                <div id="navbar" class="navbar-collapse collapse">
                <ul class="nav navbar-nav">
                    <li><a href="example.html" class="nav-link">Example</a></li>
                    <li class="separator visible-md visible-lg">|</li>
                    <li><a href="selection.html" class="nav-link">Selection</a></li>
                    <li>
                        <div class="dropdown">
                            <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                            Forms<span class="caret"></span>
                            </span>
                            <ul class="dropdown-menu" aria-labelledby="dLabel">
                                    <li><a href="forms-markup.html">Forms</a></li>
                                    <li><a href="forms-pseudo-classes.html">Pseudo Classes</a></li>
                                    <li><a href="forms-validation.html">Native Validation</a></li>
                                    <li><a href="forms-validation-custom.html">Custom Validation</a></li>
                                    <li><a href="forms-validation-bootstrap.html">Bootstrap Module</a></li>
                            </ul>
                        </div>
                    </li>
                    <li>
                        <div class="dropdown">
                            <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                            Media<span class="caret"></span>
                            </span>
                            <ul class="dropdown-menu" aria-labelledby="dLabel">
                                    <li><a href="media-basics.html">Basics</a></li>
                                    <li><a href="media-scripted.html">Scripted Controls</a></li>
                                    <li><a href="media-dynamic.html">Dynamic Load</a></li>
                            </ul>
                        </div>
                    </li>
                    <li>
                        <div class="dropdown">
                            <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                            Canvas<span class="caret"></span>
                            </span>
                            <ul class="dropdown-menu" aria-labelledby="dLabel">
                                    <li><a href="canvas-basics.html">Basics</a></li>
                                    <li><a href="canvas-manipulation.html">Manipulation</a></li>
                                    <li><a href="canvas-clipping.html">Clipping</a></li>
                                    <li><a href="canvas-charts.html">Charts</a></li>
                                    <li><a href="canvas-video.html">Video</a></li>
                            </ul>
                        </div>
                    </li>
                    <li>
                        <div class="dropdown">
                            <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                            Drag &amp; Drop<span class="caret"></span>
                            </span>
                            <ul class="dropdown-menu" aria-labelledby="dLabel">
                                    <li><a href="dd-basics.html">Basics</a></li>
                                    <li><a href="dd-datatransfer.html">Data Transfer Types</a></li>
                                    <li><a href="dd-files.html">Files</a></li>
                                    <li><a href="dd-effects.html">Effects</a></li>
                                    <li><a href="dd-dragimage.html">Drag Image</a></li>
                                    <li><a href="dd-dragimage-canvas.html">Drag Image (canvas)</a></li>
                            </ul>
                        </div>
                    </li>
                    
                    
                </ul>
                </div><!--/.nav-collapse -->
            </div>
            </div>
        </div>

        <div id="content-container" class="container">
            <div class="container example-layout">
                <h1>4768 Jupiter Drive</h1>
                <h2>Anytown, CA 90210</h2>
                
                <div>
                    
                    <div>
                        <img src="img/home.jpg" class="thumbnail img-responsive push-down-top " />
                        <div>Brand new build at the end of a cul-de-sac in the north end of town</div>
                    </div>
                    
                    <div class="row push-down-top-sm">
                        <div class="col-sm-8">
                            <p>A beautiful home on a quiet street featuring an open floor plan with 5 bedrooms 
                                and 3 full baths accented by a breathtaking view. After walking in the extra-tall 
                                double-door entry way, you are greeted by the family-oriented kitchen which includes 
                                a walk-in pantry, granite countertops, a double oven next to a granite topped 
                                oversized arrow island with tons of storage underneath.</p>
                                
                            <div class="aside">
                                <div>
                                    <div>Features</div>
                                    <ul>
                                        <li>Luxurious sized Master Suite</li>
                                        <li>Oversized walk-in closet</li>
                                        <li>Frameless Beech cabinetry with concealed hinges</li>
                                        <li>Elegant slab White Quartz countertops with 4″ backsplash</li>
                                        <li>Dual china sinks with Moen faucets</li>
                                        <li>Clear frameless shower enclosures</li>
                                        <li>Hand set 6″ x 6″ ceramic tile at Shower Walls</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <p>Adjacent to the kitchen is a 
                                breakfast area overlooking a forest landscape through a sliding glass door. 
                                The downstairs bedroom includes a full wardrobe. The living room includes a recessed 
                                entertainment area complete with canned lighting with dimmer switch highlighted by a 
                                charming dual-sided fireplace.</p>
                            <p>Next is formal dining room and front sitting room. The 
                                winding staircase leads you upstairs to the huge master suite featuring a sunk-in tub, 
                                large shower, walk-in closet and an additional over-sized walk-in closet. The master 
                                bath features split sinks with granite countertops.</p>
                            <p>Also includes:</p>
                            <ul>
                                <li>two car garage</li>
                                <li>high ceilings throughout</li>
                                <li>huge bonus room with two closets</li>
                                <li>wired for spa in backyard</li>
                                <li>dual pane windows</li>
                                <li>upstairs laundry room</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <script src="js/jquery.min.js" type="text/javascript"></script>
        <script src="js/bootstrap.js" type="text/javascript"></script>
        <script src="js/highlight/highlight.pack.js" type="text/javascript"></script>    
        <script src="js/app.js" type="text/javascript"></script>
    </body>
</html>


```
# HTML5


- DOCTYPE: 
It has DOCTYPE but just html.This flags the broswer that it can interpret this page as an HTML5 page.
It gives you the ability to access all the new elements and Javascript API on the page.
It remove some of the very strict rules that were in force with XHTML.
- html tag:
it only require lang attribute which we set to en.

- meta: 
This is just for i.e to make browser uses latest IE version.
```
 <meta http-equiv="x-ua-compatible" content="ie=edge">

```

For mobile devices to set width and setting the initial zoom level or the initial scale to 1.
```
  <meta name="viewport" content="width=device-width, initial-scale=1">


```

- style/script inline:
inline sytle and script tag doesnt require type attribtue, For style default language is CSS,
For scripts javascript has been the default standard there was very earlier we used to have VBScript but now it no more in for adding interactivity to the page but now its not required.

- main:
we can have only one main element on each of HTML5 page. Inside of that of that we wrap header then  nav and other content.


- article: 

The article wraps up the primary content for the page. It doesnt have the same restrictions as the main element. We can have more than one article on the page.

- h1: 
Earlier we used to have only one h1 element but now we can have more than one h1 elements. Since  elements have a semantic meaning to their parent, you could have an h1 inside the header and insdie the article and perhaps even inside the footer.
Now you are not stuck with saying that this is the heading , the main heading for the entire page, So depending on the container that it's in you can say that this is the main heading for that specific container.


- section:
Section is used to create logical grouping of content that's on the page. 
Section can have nested section. Before html5 we used to use "div" the practical application of div and section are the same things.

. So if you need to a container to attach some style rules to, then you would use a div.
. Now you use a section when you want to create a logical group between elements but id doesnt have any sort of change on the final UI.

- anchor:
earlier you can't use block level of element for provide link. Now you can use anchors to provide links to block level items, as well as inline items.

```
<a href="#link-to-details">

  <figure>
            <img src="img/home.jpg" class="thumbnail img-responsive push-down-top " />
            <figcaption>Brand new build at the end of a cul-de-sac in the north end of town</figcaption>
        </figure>

</a>
```

- aside: 
The aside element  is used for features.

- detail:
Can use some interaction by using the details and summary elements. 

. Set attribute Open to keep open details on first load.

```

<aside>
                    <details open>
                        <summary>Features</summary>
                        <ul>
                            <li>Luxurious sized Master Suite</li>
                            <li>Oversized walk-in closet</li>
                            <li>Frameless Beech cabinetry with concealed hinges</li>
                            <li>Elegant slab White Quartz countertops with 4″ backsplash</li>
                            <li>Dual china sinks with Moen faucets</li>
                            <li>Clear frameless shower enclosures</li>
                            <li>Hand set 6″ x 6″ ceramic tile at Shower Walls</li>
                        </ul>
                    </details>
                </aside>


```

- video: 
Here you can see the attributes that dont requie values within the element. which is right code in html.
so i'm saying to display the controls on the page, to loop the media when it gets to the end, and then preload.
Preload does take a value because therre are predefined values that ou can add in to the preload attribute.

```
 <video controls loop preload poster="img/kitchen.png" width="900">
                <source src="media/kitchen.mp4"><!-- Serve first for iPad -->
                <source src="media/kitchen.ogv">
                <source src="media/kitchen.webm">
                <p>This browser does not support native video</p>
            </video>


```

- time:

```
<time datetime="2016-07-27t13:23-8:00" pubdate>Julu 27<sup>th</sup>, 2016</time>


```
The time is et, and also added is the pubdate attribute. which tells the browser this is the publication datte for the document itself. 
datetime which provide the date, the time, and all the way down to the time zone offset.


```
<!doctype html>
<html lang="en">
	<head>
		<meta charset="utf-8">
		<meta http-equiv="x-ua-compatible" content="ie=edge">
		<title>HTML5 Example</title>
		<meta name="viewport" content="width=device-width, initial-scale=1">

		<link rel="icon" type="image/png" href="img/favicon.png">
		<link rel="stylesheet" href="css/bootstrap.css" type="text/css" />
		<link rel="stylesheet" href="css/site.css" type="text/css" />
		
		<script src="js/modernizr.min.js" type="text/javascript"></script>

		<style>
			body {
				background-color: #fff;
			}
		</style>

		<script>
			console.log('HTML5 Example loaded');
		</script> 
	</head>
	<body>

		<main>

		    <header>
		    <!-- Fixed navbar -->
			    <nav class="navbar navbar-inverse navbar-fixed-top">
			    <div class="container">
				    <div class="navbar-header">
				    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
					    <span class="sr-only">Toggle navigation</span>
					    <span class="icon-bar"></span>
					    <span class="icon-bar"></span>
					    <span class="icon-bar"></span>
				    </button>
				    <a class="navbar-brand" href="index.html">
					    <img src="img/html5-fundamentals.png" title="HTML5 Fundamentals" class="hidden-sm" />
					    <img src="img/html5.png" title="HTML5 Fundamentals" class="visible-sm" />
				    </a>
				    </div>
				    <div id="navbar" class="navbar-collapse collapse">
				    <ul class="nav navbar-nav">
					    <li><a href="example.html" class="nav-link">Example</a></li>
					    <li class="separator visible-md visible-lg">|</li>
					    <li><a href="selection.html" class="nav-link">Selection</a></li>
					    <li>
						    <div class="dropdown">
							    <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
							    Forms<span class="caret"></span>
							    </span>
							    <ul class="dropdown-menu" aria-labelledby="dLabel">
									    <li><a href="forms-markup.html">Forms</a></li>
									    <li><a href="forms-pseudo-classes.html">Pseudo Classes</a></li>
									    <li><a href="forms-validation.html">Native Validation</a></li>
									    <li><a href="forms-validation-custom.html">Custom Validation</a></li>
									    <li><a href="forms-validation-bootstrap.html">Bootstrap Module</a></li>
							    </ul>
						    </div>
					    </li>
					    <li>
						    <div class="dropdown">
							    <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
							    Media<span class="caret"></span>
							    </span>
							    <ul class="dropdown-menu" aria-labelledby="dLabel">
									    <li><a href="media-basics.html">Basics</a></li>
									    <li><a href="media-scripted.html">Scripted Controls</a></li>
									    <li><a href="media-dynamic.html">Dynamic Load</a></li>
							    </ul>
						    </div>
					    </li>
					    <li>
						    <div class="dropdown">
							    <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
							    Canvas<span class="caret"></span>
							    </span>
							    <ul class="dropdown-menu" aria-labelledby="dLabel">
									    <li><a href="canvas-basics.html">Basics</a></li>
									    <li><a href="canvas-manipulation.html">Manipulation</a></li>
									    <li><a href="canvas-clipping.html">Clipping</a></li>
									    <li><a href="canvas-charts.html">Charts</a></li>
									    <li><a href="canvas-video.html">Video</a></li>
							    </ul>
						    </div>
					    </li>
					    <li>
						    <div class="dropdown">
							    <span class="nav-link" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
							    Drag &amp; Drop<span class="caret"></span>
							    </span>
							    <ul class="dropdown-menu" aria-labelledby="dLabel">
									    <li><a href="dd-basics.html">Basics</a></li>
									    <li><a href="dd-datatransfer.html">Data Transfer Types</a></li>
									    <li><a href="dd-files.html">Files</a></li>
									    <li><a href="dd-effects.html">Effects</a></li>
									    <li><a href="dd-dragimage.html">Drag Image</a></li>
									    <li><a href="dd-dragimage-canvas.html">Drag Image (canvas)</a></li>
							    </ul>
						    </div>
					    </li>
					
					
				    </ul>
				    </div><!--/.nav-collapse -->
			    </div>
			    </nav>
		    </header>

		    <article id="content-container" class="container example-layout">
			    <h1>4768 Jupiter Drive</h1>
			    <h2>Anytown, CA 90210</h2>
				
			    <section>
				    <a href="#link-to-details">
					    <figure>
						    <img src="img/home.jpg" class="thumbnail img-responsive push-down-top " />
						    <figcaption>Brand new build at the end of a cul-de-sac in the north end of town</figcaption>
					    </figure>
				    </a>
					
				    <section class="row push-down-top-sm">
					    <div class="col-sm-8">
						    <p>A beautiful home on a quiet street featuring an open floor plan with 5 bedrooms 
							    and 3 full baths accented by a breathtaking view. After walking in the extra-tall 
							    double-door entry way, you are greeted by the family-oriented kitchen which includes 
							    a walk-in pantry, granite countertops, a double oven next to a granite topped 
							    oversized arrow island with tons of storage underneath.</p>
								
						    <aside>
							    <details open>
								    <summary>Features</summary>
								    <ul>
									    <li>Luxurious sized Master Suite</li>
									    <li>Oversized walk-in closet</li>
									    <li>Frameless Beech cabinetry with concealed hinges</li>
									    <li>Elegant slab White Quartz countertops with 4″ backsplash</li>
									    <li>Dual china sinks with Moen faucets</li>
									    <li>Clear frameless shower enclosures</li>
									    <li>Hand set 6″ x 6″ ceramic tile at Shower Walls</li>
								    </ul>
							    </details>
						    </aside>
							
						    <p>Adjacent to the kitchen is a 
							    breakfast area overlooking a forest landscape through a sliding glass door. 
							    The downstairs bedroom includes a full wardrobe. The living room includes a recessed 
							    entertainment area complete with canned lighting with dimmer switch highlighted by a 
							    charming dual-sided fireplace.</p>
						    <p>Next is formal dining room and front sitting room. The 
							    winding staircase leads you upstairs to the huge master suite featuring a sunk-in tub, 
							    large shower, walk-in closet and an additional over-sized walk-in closet. The master 
							    bath features split sinks with granite countertops.</p>
						    <p>Also includes:</p>
						    <ul>
							    <li>two car garage</li>
							    <li>high ceilings throughout</li>
							    <li>huge bonus room with two closets</li>
							    <li>wired for spa in backyard</li>
							    <li>dual pane windows</li>
							    <li>upstairs laundry room</li>
						    </ul>
					    </div>
						
				    </section>
					
				    <video controls loop preload="auto" poster="img/kitchen.png" width="900">
					    <source src="media/kitchen.mp4"><!-- Serve first for iPad -->
					    <source src="media/kitchen.ogv">
					    <source src="media/kitchen.webm">
					    <p>This browser does not support native video</p>
				    </video>
			    </section>
				
			    <time datetime="2016-07-27T13:25:23-8:00" pubdate>July 27<sup>th</sup>, 2016</time>
		    </article>
		
			<footer>
				<div class="container">
					<div class="row push-down-top-lg">
						<div class="col-sm-offset-2 col-sm-3">
							<img src="img/html5-fundamentals.png" title="HTML5 Fundamentals" />
							<p>by <a href="http://craigshoemaker.net">Craig Shoemaker</a></p>
							<p class="lead">
								<a href="http://twitter.com/craigshoemaker">Craig Shoemaker</a> is a
								<a href="http://www.infragistics.com">developer</a>,
								<a href="http://www.pluralsight.com/author/craig-shoemaker">instructor</a>,
								<a href="http://code-magazine.com/SearchResults.aspx?search=craig%20shoemaker">writer</a>,
								<a href="http://polymorphicpodcast.com">podcaster</a>, and a man of many hats at
								<a href="http://www.infragistics.com">Infragistics</a>.
							</p>
							<div class="push-down-top-md">
								<a href="https://www.pluralsight.com/courses/html5-fundamentals"><img src="img/pluralsight.png" title="HTML5 Fundamentals" /></a>
							</div>
						</div>
						<div class="col-sm-offset-1 col-sm-3">
							<a href="http://craigshoemaker.net"><img src="img/craig-shoemaker.png" title="Craig Shoemaker" /></a>
						</div>
					</div>
				</div>
			</footer>

		</main>
		
		<script src="js/jquery.min.js" type="text/javascript"></script>
		<script src="js/bootstrap.js" type="text/javascript"></script>
		<script src="js/highlight/highlight.pack.js" type="text/javascript"></script>    
		<script src="js/app.js" type="text/javascript"></script>
	</body>
</html>

```
[html5 boilerplate](https://html5boilerplate.com/)

[Can I use Features](https://caniuse.com)

# Modernizr

Its a lightweight Javascript library that takes care of all of the heavy lifting when it comes to feature detection.

- Want to know if the current broswer supports a paticular feature?
To use Modernizr, you have to reference it in your page and as the page loads, Modernizr inspects the user's browser and reports back what it's capabilities are.

Goto [Modernizr download](https://modernizr.com/download?setclasses) tab, you'll notice there're number of different features that it supports detection upon inside the browser. If you wnated to use canvas, you could come over herre and click on exmaples it shows you some CSS you can use to display elements with or without canvas and in Javascript yo simply use the boolean value, Modernizr.canvas then you can write your won custom code to decide what to do if support exists or not.
If you  reference it in your page on the page loads Modernizr inspects the user's browser and reports back what it's capabilities are.
Detecting Features
```
css

.no-canvas .box{color:red;}

.convas .box{color:green;}

js

if (Modernizr.canvas){
// supported
}else{
// not-supported
}

```

# Fallbacks and Polyfills

If you are developing an application and you really need a certain API, and it's not supported by all broswers, or maybe its not supporrted by some at all.
The second line of defense other than Moderniz is to turn to fallbacks and polyfills.

- Fallback: 
As the name suggests, a fallback is an implementation that you can fall back to that's usually done by a third party with a different API than what you night find natively implemented in the browser.
e.g
Popular library called Q which provides an implementation for Promises, which is an API that's used to deal with asynchronous processing and it was available far before any browser supported promises natively.The functions in your code calls was different than whta was spec-ed out for the native broser implementation, but you generally got the same functionality.
In-short, it provide similar functionality as a native feature but maybe just with different API.

- Polyfill:
Is is meant to replicate the exact same interface as well as functionality as how the native implementation would be built in to the browser. The benefit to using a polufill is that once broswer support is ubiquitous, the idea is that you can simply remove the polyfill from your application and the functionality will remain unchanged, although it would still recommend some rigorous testing during this time.

Note: There is the web website [to find out about fallbacks and polyfills](https://html5please.com). This is a good website that gives you a pretty good handle on what's available as far as APIs and which one needs to be used with a fallback or a polyfill, and which is not available at all.
e.g

WebSQL DB
It initially found favor as a clientside database API,now been abandoned in favor of IndexedDB.

# Modernizr vs Polyfills
- Modernizr does is, very simply, tell you whether the current browser has this feature natively implemented or not. 
- Modernizr is a small JavaScript library that you can use for feature detection.

- Once you do the feature detection for your browser, you can then do polyfill.
- polyfills is for browser compatibility.
- polyfills replicate the standard API found in native features of new browsers for those without such features.


Traditional DOM Selection
In the past traditional DOM selection API is limited and it lacks some of the basic functions needed to be truly useful.In fact some of the libraries like JQuery initially came from the need to be able to select agianst the DOM in an easy, reliable and speedy fashion.
In HTML5 there's a host of new selectors that make it not only easy to work with the DOM but also super-fast.

# Examples

## Selection API

- getElementsByClassName :
it returns an array of elements that match that selection of class.
This will return live result

```
document.getElementsByClassName('img-responsive')

```

- querySelector: 
If you want little more robust compareto getElementsByClassName e.g a CSS3 selector, then querySelector is the one.
The elements that you want to select against the page arent simply availabe through a class name or a tag name, and your needs are a little more sophisticated.

. To get first match that it finds the document.

```
document.querySelector('.img-responsive')

document.querySelector('#example-container li:first-child')
```

- querySelectorAll:
Pass a selector .img-responsive, It will get back an array of all the matche to my selector.
This will return static result set.

querySelectorAl returns that appears to be array of elements. But in fact, it's not. It's actually a node list. when you do toString against the items it returns a tyoe of NodeList. So technically its not an array so cant simply iterate over it using  the foreach function. 


. Find all matches to that selector.

```
document.querySelectorAll('.img-responsive')

---
var container = document.getElementById('example-container');
var items=container.querySelectorAll('.img-responsive')

items.toString()// [object NodeList]

```

- How to iterate through NodeList: 
There are two way to iterate through NodeList. 

. Standard for loop.

for Iteration
```
var items = document.querySelectorAll('#example-container li');

for (var i = 0, len = items.length; i < len; i++) {
	console.log(items[i].innerText);
}

```

. Foreach method off of the array prototype.

forEach Iteration
```
var forEach = Array.prototype.forEach;
var items = document.querySelectorAll('#example-container li');

forEach.call(items, function(item){
console.log(item.innerText);
});

```- "Live" Result from getElementsByClassName:
Now once you make a selection against an element on the page, depending on whether or not you have a live connection to it or static connection to it will determine how it behaves as it changes throughout the lifecycle of the page. 
If we were to take a look at the exmple-container and get access to the unordered list element, so that would be the parent element of each one of there list items and then change the number of list items inside that unordered list when you are working with a live result you will be able to recognize that change programmatically as it happens.

```
var list = document.querySelector('#example-container ul');
var items = document.getElementsByClassName('feature');

console.log(items.length);

var newItem = document.createElement('LI');
newItem.className = 'feature';
newItem.innerText = 'new live feature';
list.appendChild(newItem);

console.log(items.length);

```

- Static Result  querySelectorAll
if you access elements by using querySelectorAll then you will end up with a static result.
It mean that it still give old count even if we add dynamically.

```
var list = document.querySelector('#example-container ul');
var items = document.querySelectorAll('#example-container li');

console.log(items.length);

var newItem = document.createElement('LI');
newItem.className = 'feature';
newItem.innerText = 'new static feature';
list.appendChild(newItem);

console.log(items.length);


```

# The datalist element gets associated with what other type of element?

- input

# The querySelector and querySelectorAll functions take _________________ as input. 

- CSS3 selectors 

# A typeMismatch validation rule is broken when: 

- The input's value does not match the type defined in the input element 

# Which video format has the most widespread browser support? 

- MP4 

# What is HTML5? 

- New semantic markup and JavaScript APIs 

# The video and audio APIs are largely the same except for the following distinction: 

- The audio API does not have methods for controlling video. 

# What does the moveTo method do? 

- Places the drawing tool at a specific place on the canvas 


# What function is used to render text on the canvas? 

- fillText 

# As an element is dropped, what is the last event that is fired? 

- dragEnd 

# What event continually fires on the drag source? 

- drag 





# What's mean  by Accessibility?

Accessibility is the word used to describe product can be used by people of all abilities. 

# What is Web Accessibility?

The W3C say's that Web Accessibility means that people with disabilities can use the web. which make life easier for everyone and few people has to struggle.
In general developer consider WCAG nice to have requirement and keep it in the phase two. Which when start they find themselves have to do redo lots of existing work its pretty frustrating process. It takes lot of time. 
If we consider WCAG at the start we will reduce the work significantly.


# To make Application with Web accessibility compatible the things need to keep in mind

1) Keyboard Accessibility

Web Form contents should be keyboard accessible with using the mouse.

2) Work with a Screen 

Should be readable and navigatable through screen reader e.g NVDA, ChromeVOX.

3) ARIA for Context

Its the HTML enhancement which will make our form even easier to understand for screen reader to use.

4) Form validation

The Web form does have client-side validation but its not very accessible

5) Final Improvements.

Address the usability issues accross the application.

# What kind of disabilities shoud we accommodate for?

1) Physical Disabilities.
. Various disabilities, long-term and temporary.
 
e.g user may have limitations of muscular control, joint problems or paralysis with short-term issues too,like broken limbs or even someone trying to user website while holding a baby.This is the result which require people. 

. Navigate websites using a keyboard alone or device that simulates keyboard use.

. Lack of fine motor control - don't put buttons too close together

e.g Often applied to elderly users we can help the by not putting button and link too close to prevent accidental clicks.

2) Color Blindness

. Difficulty to differentiate between colors : It means we shouldn't use color alone to convey the information.
e.g Labels in red indicate required fields.

3) Deafness 

. Need captions on videos : This is also useful to those who work in noisy enviromnents

4) Visual Disabilities

. Mild vision impairment to total blindness

e.g some with minor impairment want to increase font size or use the  magnifying tools 

. Sever bimpairment and blindness lot of users use a screen reading tool or refreshable Braille display.

Screen reader doesnt read web pages from start to end, There are sophisticated pieces of software that read out content and allow the user to navigate and interact with the page using keyboard commands

# What is Web Content Accessibility Guidelines(WCAG)?
# How do you know whether your site is accessible or not?

The W3C's web accessibility initiative  has put together a set of web content accessibility guidelines that is refer to WCAG. The guidelines are made up of several "Tesable success criteria", which give clear set of objectives to make site compatible with WCAG. All we can do is to make site more accessible, its not really possible to claim that the site is 100% accessible because just it meets the WCAG guidelines but it has reached an acceptable standard.

# What are the different levels of conformance to the WCAG guidelines?

There are actually three levels of confromance to the guidelines
1) Level A: Which is the lowest.

2) Level AA: Which is the middle.

3) Level AAA: which is the highest.

Each of the success criteria in the WCAG is associated with the level. So to be level A conformant of a site has to meet every one of the level A success criteria. 
To be level AA conformant, a site has to meet all level A and level AA success criteria and so on.

Typically when we make a site accessible we aim to meet the scritera for level AA.

The criteria for AAA can be really tricky and in some cases impossible to meet depending on your site. Though of course we should try to meet AAA if we can.

# What are different principles of WCAG?

The WCAG success criteria are grouped into four principles.

* Perceivable:

Contents should be perceivable e.g providing text alternatives for images, captions for video.

* Operable: 

It should be operable with a keyboard and easy to navigate.

* Understandable:

Site should be understandable and behave in predicatble ways helping the user to avoid mistakes.

* Robust:

Site should be robust and well structured the maximizing compatibility with current and future technologies.

# Common misconception that the site must work without Javasdcript to meet WCAG

* A common misconception amongst developers is that if a site requires Javascript to function, it cant meet WCAG.

A common misconception amongst developers is that if a site requires Javascript to function, it cant meet WCAG.
Which is simply not true.

* WCAG 2.0 says it's fine to rely on Javascript, as long as the sucess criteria are meets.

The previous version require the site to function without Javascript, but since the second version's publication in 2008 use of Javascript is fine as long as the success criteria are still met.


# Section 508
This is another set of accessibility guidelines from the US government. Any software used by federal agencies must comply to it.
It has just single Level of complaince. 
The majority of guidelines are very similar to the WCAG.

# WCAG is a technical standard not an introduction to accessibility.

This is essentially them saying this is really stunningly complex, so proceeed with caution. Now guideline are little daunting at first because each criterion has to be completely testable. They list out several different ways it's possible to meet each criterion and also some aspects that would cause a failure to meet one. saying that once you use the structure of the guidelines, it's really not that bad. it's actually useful that they go into a high level of detail because it helps you to make technical decisions.

# What are the Web Content Accessibility Guidelines?
The Web Content Accessibility Guidelines(WCAG), Produced by the World Wide Web Consortium (W3C), the WCAG are the best means of making your website useful to all of your users.
They are not an all-inclusive list of issues facing web users with disabilities, these are internationally recognised and adopted standards. The guidelines explain how to solve many of the problems that your users with disabilities face.
There are two version of WCAG .
1) WCAG 1.0 in 1999
2) WCAG 2.0 in 2008
3) WCAG 2.1 is currently in development and is scheduled to be published as a standard in 2018.

Both the WCAG 2.0 and the older WCAG 1.0 are further organized into priority levels, ranging from most important (A) to least important (AAA). At Penn State, Web sites should fulfill levels A and AA to be considered compliant.


# Web Content Accessibility Guidelines 1.0
The Web Content Accessibility Guidelines 1.0 had 14 guidelines and divided them into 3 priority levels:
◾Priority 1 – the most basic level of web accessibility
◾Priority 2 – addressed the biggest barriers for users with disabilities
◾Priority 3 – significant improvements to web accessibility

# Web Content Accessibility Guidelines 2.0
WCAG 2.0 is a stable, referenceable technical standard. It has 12 guidelines that are organized under 4 principles: perceivable, operable, understandable, and robust. For each guideline, there are testable 61 success criteria, which are at three levels: A, AA, and AAA.
The guidelines are more technologically neutral than WCAG 1.0, allowing them to stay useful for longer.By designing WCAG 2.0 around principles and not technology, the W3C created an ethical statement as well as useful guidance.
The principles of WCAG 2.0 are:
 * Perceivable
 * Operable
 * Understandable
 * Robust

# Web Content Accessibility Guidelines 2.1
WCAG 2.1 is designed to be "backwards compatible" so websites that conform to WCAG 2.1 will also conform to WCAG 2.0 — which means that a website that meets WCAG 2.1 will meet the requirements of policies that reference WCAG 2.0.


# Perceivable
Web content should be made available to the senses - sight, hearing, and/or touch
Examples of Principle 1
```
•Visually impaired users must be able to receive information via sound or touch
•Hearing impaired users must be able to receive information via sight 
•Low vision users must be able to receive information with alternative formatting or zoomed to larger sizes
•Color deficient users must be able to receive information without use of color

```

# Operable
interface components/forms, controls, and navigation are operable
Examples of Principle 2:
```
•Functions triggered via mouse or gesture are also available via a keyboard
•All users are given sufficient time to read and use content.
•Content does not induce seizures.
•Users are given mechanisms to skip repetitive content.
•Landmarks are provided to assist in screenreader navigation (e.g. meaningful page title, semantic headings,
 ARIA landmarks) meaningful headers and meaningful and unique link text.
•Multiple paths are provided to navigate Web site structure.
```
# Understandable
Information/Content and the operation of user interface must be understandable.

Examples of Principle 3:
```
•Site is free of unannounced pop up windows.
•Separate Submit or Go buttons/links are provided to initiate page changes (versus autosubmit upon selection).
•Navigation and labels are consistent across a Web site or application.
•Mechanisms are available to detect errors and provide clear instructions to users on fixing errors.
•Language of text or subsection of text is identified.

```

# Robust
Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.


# JAWS (screen reader)
JAWS ("Job Access With Speech") is a computer screen reader program for Microsoft Windows that allows blind and visually impaired users to read the screen either with a text-to-speech output.

# [WAI-ARIA](https://github.com/filipelinhares/WAI-ARIA-cheatsheet)
[Example](http://lab.abhinayrathore.com/aria-cheatsheet/)

[Example2](http://karlgroves-sandbox.com/CheatSheets/ARIA-Cheatsheet.html)

# The WAI-ARIA is a technical documents developed by the Accessible Rich Internet Applications Working Group (ARIA WG), 
which is part of the World Wide Web Consortium (W3C), Web Accessibility Initiative (WAI). 

WAI-ARIA provides Web authors with the following:
```
• Roles to describe the type of widget presented, such as "menu", "treeitem", "slider", and "progressmeter"
• Roles to describe the structure of the Web page, such as headings, regions, and tables (grids)
• Properties to describe the state widgets are in, such as "checked" for a check box, or "haspopup" for a menu.
• Properties to define live regions of a page that are likely to get updates (such as stock quotes), 
as well as an interruption policy for those updates—for example, critical updates may be presented in an 
alert dialog box, and incidental updates occur within the page.
• Properties for drag-and-drop that describe drag sources and drop targets
• A way to provide keyboard navigation for the Web objects and events, such as those mentioned above
```

# Keyboard Navigation

. Arrow keys to scroll up and down.
. Tab and Shift-Tab to navigate forth and back through the controls.
. Enter to click a focused link or button.
. Space to check boxes for selecting and deselecting.

Keyboard related issues.


. Focus Visible: Keyboard /Tab key focus, in some cases its not clear to identify where the focus of the control.

. Focus Order: Components should receive the focus in a "meaningful" order, Focus shouldn't jump around unexpectedly. This specially helpful those who are using a magnifier they no need to search focus where it gone.common cause When you set the tabindex attribute on the control. Dont set the tabindex to control focus order.

. Select Box Options:Organize the selection option correctly or Info and relationships, information should laidout correctly as clearly as possible.

![Select Option Group](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/Select_Grouping.PNG) 

# What is a Screen Reader?

. Its a software to allow users with severe visual impairments to use a computer.
. Outputs speech or braille
. Allow the user to navigate and enter data with the keyboard


When a user has a severe visual impairment, they aren't going to be able to rely on magnification and contrast tools to use a computer. A screen reader interrprets what is on the screen and outputs it to the user, either using a text-to-speech engine or a refreshable braille display. They also allow the user to interact with the computer, navigating around and entering data on forms using the keyboard.those will have wide array of keyboard shortcuts to make interactions simple.

# Speech and/or Braille Outputs
. Text to Speech is synthesized and can be quite fast.
. Refreshable braille displays can raise dots to form characters.

There are two types of output from a screen reader, speech and braille. Some people will use both. The speech is synthesized from the text and can sound stangely robotic. New users of screen readers typically find that the speech is way too fast by default, but experienced users often speed it up even more. A refreshable braille display, like the one shown here contains a row of cells


# How Screen reader page Context is Output?

. Can't glance around context like sighted user.
. Process text line by line.
. Can jump between headers, links and different regions to make it easier.

When a sighted user views a web page, they can glance over the contents of the whole screen and immediately get a sense of what content there is on the page. Screen readers process content line from top to bottom. You can imagine this can be really frustrating for a user. Thankfully, screen readers have a lot of features that allow the user to sort of skim the content to see what's there. They can jump between links and headings and also different areas of the page, but this only works well if the website has been designed with this consideration. If headings aren't defined properly, for example,the user is ldft just listening fo the content from top to bottom. There are a lot of screen readers available. The Mac OS actally has a screen reader built in called VoiceOver.

# Popular Screen Readers.

. Mac built-in: VoiceOver.

. Window has few popular options.
1) JAWS by Freedom Scientific.

2) Window-Eyes by GW Micro: It comes with bundled in with the Microsoft Office Suite.

3) NVDA(http://www.nvaccess.org/): NonVisual Desktop Access: its an open source solution.

# Screen reader modes.
There are two modes
. Browse :(EScape key to get back from focus to browse) Browse is for reading the content.
. Focus:(when pressed space bar after reading the text befor the text) Focus is for entering data on forms.

NVDA sometimes switches to focus mode automatically.

# Easy Access Key

H: heading key
K: Links
B: Buttons
L: Lists
D: Landmarks

SPACE: Enter focus mode from control.
TAB: Jump focus to next control.
SHIFT+TAB: Jump focus to previous control.
ESC: Exit foucs mode.

# Making Content Readable
1.1.1 : Non-text content(e.g. image)
. All non-text content should have a text equivalent.
. A few exceptions, like CAPTCHAs
. Purely decorative content should be identified as such, 
e.g. Empty alt attributes identify an iamge as purely decorative.

```
<imag scr="som.png" alt="" />
```

# Link Purpose

The link text should be sdlf-explanatory else can confuse to the user like (click here or read more).

# Images used for buttons
Possible avoid using image for button if it cant achieve through the CSS and you have to use image then provide alt text.

# Labels for Form Fields

3.3.2 Labels or Instructions: 
. When content requires user input, labels or instructions are provided.
. Labels in close proximity to inputs. os that if someone is using magnifier relationship should be clear.

```
<label for="details-name">Name * </label>
<input type="text" id="details-name" />

```

# Labels for Checkboxes

When we use label with checkboxes group them together.

![Select Option Group](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/checkbox-group.PNG)

# Setting Keyboard Focus.
Try not to set focus using Javascript on page load, It can be really disorientating for screen reader users.

# What is ARIA?
It's stands for Accessible Rich Internet Applications, As website getting more and more complex with interactions such as drag and drop, widgets like tree controls and expandable menus. You can imagine that it's difficult for screen reader users to interact with this kind of control. That's where ARIA comes in. Its the framework that allows us as a developers to provide this rich functionality in a way that screen reader users can still understand and use.

Typically ARIA referred to as "WAI-ARIA". Thats because its developed by the W3C's web accessibility initiative. They put together the WCAG guidelines. ARIA helps us to describe things that sighted users would just be able to figure out from the context by adding ARIA attributes to the HTML.

ARIA is just for exposing information to screen reader doesn't influence browser behaviour.

# Different Categories of ARIA Attributes
Aria attributes fall into three categories.

1) Roles: 
You can state what role an element has by using role attribute.

 role="menuitem"

2) State:
You can describe its current state like expanded or selected

aria-selected="true"

3) Properties

We can describe other properties the item has, e.g when you activate it, a popup will appear.

aria-haspopup="true"

# Some clashes between HTML5 and aria roles
HTML 5  button  and ARIA role="button"
Screan reader already knows that it's a button when use button tag it doesnt require button role. We can use ARIA role="button" when we plan to use some other element as a button like image or anchor tag in those case role play important role, as HTML is becoming more expressive role are becoming redudant.

# ARIA Labelling Attributes
we can yse the ARIA label attribute to give a control some lavel text without having to put actual label element on the page.


* Define the label text for a control
```
<input type="text" ariabe-label="Name" />

```
* States that the control is labelled by another contorl

```
<input type="text" ariabe-labelledby="lblFirstName lblLastName" />

```

If control has more than one label ID's in the attribute value put those IDs separated by a space to show that the control has two labels.
e.g.

For checkbox we can use multiple labels one is question and other is their answer, or we can go with fields in our ealier example we did it.

# Aria Described By

```
<label for="txtCont" > short description <label>
<input id="txtCont" type="text" aria-describedby="ControlId" />

<p id="ControlId" >
Long description which is displayed on the page
</p>
```
References an element ID that has furtherr description for the control.
Used in addition to a label.

# Announcing Updates

Sites can have elements that update , appear without the page reloading or auto correct the text.
e.g 
Chat windows, status bars, errors and countdown times.
. Before ARIA, there was no simple way to alert the screen reader users of these updates.

# ARIA Live Importance.

To state that an area maybe udpating client side , you can add the ARIA live attribute that contain the element. (e.g div upate using javascript or text box changing their values)

There are two levels of importance

1) polite
When set aria-live to polite, we are basically saying that when an update happens to this region, the user does need to be informed but it shouldn't interrupt what they're currently doing. Screen tend to implement this when user finished there work like after completion of typing.

2) assertive
Update to this region is really critical and the user needs to be informed right away. this is rearly used situation like when user lost the internet connection or so on.

# ARIA Atomic

. Controls which aspects of the live region are read out
You can actually control what aspects of the ARIA live labeled region are read out with another attribute, ARIA Atomic.

False means only the elements that changed to be read out.

True means all the child elements of that the region has to be read out.

```
<div  aria-live="polite" aria-atomic="true"   > 

<span id="pricelabel" > Total Price</span>
<span id="priceValue" > 8.0 </span>
</div>
```

# ARIA Busy

. With several updates, the screen reader may notify user before fully complete.

. Setting aria-busy to true during the updates forces it to wait.

One thing to note about the ARIA Live regions is that sometimes when you are developing a complex widget the screen reader can try to notify the user before you're done udpating all the elements, in that case we can set aria-busy="true" and when we complete set is to flase.

```
<div  aria-live="polite" aria-atomic="true"  aria-busy="true"  > 

<span id="pricelabel" > Total Price</span>
<span id="priceValue" > 8.0 </span>
</div>

```
When we use screen read it describe it as a link. 

# Semantic HTML
1.3.1 : info and relationships:
Information conveyed through presentation can be programmatically determined

. Instead of a link pretending to be a button, use a button
where as link should be used for linking to other page.
. Choose the right HTML element for the job.

e.g If you have headline dont put paragraph elemnt and style it, use a heading element.

. Browsers and screen readers can make them work as you would expect.
e.g Button would expect keyboad focus but a span syled to be a button would not by default.
. Use the new HTML5 landmark elements like <nav> and <main> instead of using dive elements for a sites navigation menu and main content area.

which help to work with screen reader.


# Be Careful with ARIA Roles
. We could add a role of button to our link to change screen reader behavior which fix the issue but this is not the right rix to sematic HTML.

. ARIA roles are primarily for custom widgets, use HTML5 elements atmost.

# Validations are required fields.

There are two way to make required field either by using * and putting aria-required="ture" attibute in the control, and on page sumittion validating using javascript and providing error summary .
To make summary read by screen using you can go with either route using aria-live arttribute or by focusing using javascript to div like below with tabindex=-1.

```
<div id="error-summary"  tabindex="-1" >

</div>

if (!valid)
{
    $("#validation-summary").prepend("<p>There were in valid data please correct it.</p>");
    $("#validation-summary").focus();
}
```

* We can provide control name in the javascript alert like below. include error message in a link so when you click it will take you to the control.

```

function addValidationIssue(errorMessage, $input)
{

$input.addClass("invalid");
$input.attr("arria-invalid", true);
$("#validation-summary").append("<a href='"+$input.attr('id')+
"' id='error-"+$input.attr('id')+"'>"+errorMessage+"</a>");
$input.attr("aria-labelledby","error-"+$input.attr("id"));

}
```

# WCAG 1.4.4 Resize Text

- Text can be resized up to 200% without loss of content or function.

- Browsers provide built in zoon and scaling, shouldnt provent this.
- User shouldnt have to use assistive technology to read the text.
- Two permitted exceptions; images of text and captions.

- change font size from pixel to relative unit so that if we increase the font size it will take affect.
e.g.
 font-size:20px  to => font-size:1.1em;

# Error Prevention
- Provide javascript validation and confirmation or alert.
- Provide validation for each submitted values to makesure all values are enter corretly.
- Provide checkbox as a comfirmation before sumitting some important transaction.
- Provide the cancellation option if some order is booked.
- Give space between different controls specially links.
- Multi selection list box is alway confusing to user or very rare user know that they can select multiple items and it also difficult for select form the keyboard so its better to which this to series of checkbox.

# Important issues which need to address.
1: Focus indicator

Make it clear that which control actually has a keyboard focus.

2: Focus Order

The controls focus order in order to make more sensible.

3: Select Box Options

The select box option make in proper order, or reirdered them and add goruping if require.

4: Image Alt Text

Provide images alt text os that the screen reader knew what they are.

5: Link purpose

ensure that links didnt just say click here or read more so that they could be underrstood out of context.

6: Images for Buttons

Try to replace images used for the Buttons and styled them with css instead.

7: Form Field Labels

Make form more accessible by associating the labels with the input fields, which means screen reader users know what the inputs are.

8: Checkbox Labels

Introduce a field set around the checkbox options so that the question text was read out, as well as the label for the checkbox itself.

9: Setting Keyboard Focus

Remove the javascript focus setting it would cause screen reader users to miss the remaining checkboxes when it skipped ahead.

10: Improving Labelling

Improve the labelling using aria-label and aria-labelledby.

11: Instructions

use aria-describedby to associate the instruction text with the imput box.

12: Arai Live Regions

Aria live regions to announce the changes when the user modify on the form.

13: Buttons and Semantic HTML.

Make the buttons actually use button elements instead of links or other controlls, Semantic HTML which is all about using the right element for the job.

14: Required Fields

Add a message tp explain that the asterisks demoted required fields and add aria-required attribute.

15:  Invalid Controls

Tweak the CSS so it should be more obvious which fields had invalid entries and add the aria-invalid attribute to the input controls.

16: Error Messaging

Make sure that the error messages accurately described what the issue was with the input and how to correct it.

17: Informing user of Errors

 set the focus to the error summary when the button was pressed so that screen reader users knew what therre were issues.

18: Linking Errors to inputs

Change the error messages into links to jump to the input control in question and also associate the error message withe the control so that screen reader users could hear what the issue was.

19: Scalable Text

Use relative font units so that text scales properly.

20: Error Prevention

Prevent errors with confirmation or undo functions.

21: Simplify Inputs

Reduced the chance for mistakes by simplifying the imput controls and making it much easier to use.

22: Multi Select Boxes

replacing multi-select box with checkboxes or give enough space between two controls

# Accessibility Testing Tools
* WAVE
* aChecker
* Chrome > f12 > Audit> Check Accessibility
* TENON (https://tenon.io/): Full featured accessibility testing application.

# Accessibility Blogs

* Marco's Accessiblity blog
https://www/marcozehe.de/

* Accessibility Wins

https://allywins.tumblr.com

* THEPACIELLOGROUP
https://www.paciellogroup.com/blog/

* WUHCAG
https://www.wuhcag.com/

* my accesible website
http://myaccessible.website

g 

# What Is Accessibility and why is it important?

It is the practice making web application usable for wide range of people, this includes those with disabilities and it’s estimated that 20% of population has some sort of disabilities. It’s easy for web developer and designer to assume that everyone uses the web as we do and this is simply not the case. Some people partially for fully blind or have color blindness some people use screen reader, other navigate the web using only keyboard or assistive technologies that mimic the keyboard behavior. Some have cognitive issue that affect the learning, memory perception and problem solving. Some has temporary issues like broken arm, broken hand or broken finger that prevent using the mouse. Some have changing abilities due age. Other may have emergence or urgency situations and it’s our job as a developer make it easy as possible. It also help for search engine optimization. Even the site built by using Web accessibility in mind with help to everyone.

- Making sites and apps usable for everyone.
- Not just those with disabilities.
- People with vision impairments
- People using assistive technologies
- People with cognitive issues.

# Planning for Accessibility.

Most of accessibility issues stand for lack of awareness, designer and developers aren’t intending for building an inaccessible site. Just they are unaware of what they are doing so. It also believe it cost more money and take more time to design and build accessible site, But most of the time it’s simply not true when working with the team who understand the topic. Part of issue is accessibility tends to be after thought.
Here are the few things we can do at beginning
- Identify the accessibility Goals for project: this will bring everyone on the same page. Set the clear target: which provide the clear target to shoot.
- Put Someone in Charge of Accessibility issue. Everyone should be responsible for accessibility and that having one person in charge help ensure that everyone is following through and meeting the project goal.
- Evaluate Tools and Frameworks. Plan for tools and framework accessible. If it’s not accessible we can choose other and we can avoid them.
- Research current tools and best practices regarding web accessibility every time we begin a project. This help us best practices and stay top of all. New tool discovery may help us in efficiency.
- Create Personas: creating user type personas with user type disabilities and refer to that throughout the design and development process. This keep the accessibility in everyone’s mind and make easier to test. It provide common way to discussed accessibility.
Responsive Design is an Accessible Design Practice.

- Responsive Design & Accessibilities

- Color & Accessibility

- Typography & Accessibility

- Accessible Form Design

- Touch Targets

- Focus & Active Indicators

- Motion & Vestibular Disorders

- Designing for Crisis

# How is Color perceived?
People who have color blindness can’t perceive differences in certain color combinations.
- The most common color blindness deficiencies are Red/Green color deficiencies, which make difficulties in red and green values.

## Red Deficiencies
In this red and green look the similar but red look little dark

## Green Deficiencies
In this case both color look the same

## Blue Deficiencies

In this case blue and green are appear similar, yellow can disappear or possibly appear red.


## No Color

In this case only differentiate between light and dark values (white and black)

So we should design an application where if someone has color blindness still should be able to differentiate between the values.

## Different design consideration regarding different displays display color differently like mobile and desktop.

## Environment/surrounding lighting can effect on the colors. Like sun light can make more difficult to distinguish between color values


# Images & Accessibility
The Images that are inserted into content should have accessibility, but images used for decoration, look and feels are added through css or dont require a description becasue they on serve the static purposes.
Images by default are Inaccessible to those who cant see them, for this reason we need to provide the descript.
```
<img src="dog.jpg" alt="Brown Dog" />

```
It content succinct descript of the content of the image.

- For more complex image like Chart/Graph: we can provide the long descript which can contain any HTML necessary to describe the content of the image.

```
<img src="graph.jpg" longdesc="GraphDesc.txt" />

```
Long Description can be a URL to a differrent page or can link to an ID on the current page. However browser support is almost non-existent for long description. 
. So at this time its recommended to provide simpliy link to long description

- Use a Link Instead link for long description
```
<img src="graph.jpg" aria-describedby="desc" alt="Graph" />
<a href="GraphDesc.html" id="desc">
Get Graph Details
</a>


```

- What if we Dont Need Description?
```
<img src="image.jpg" alt="" />

```
# Content & Accessibility
Doesn't Matterr
. What device they're using.
. If they have disabilities
. If they're using assistive technologies
. If they're losing abilities due to aging
. If they have vestibular or reading disorders

- Provide Skip to Main content link
- When Providing Audio content provide "Get Transcript" link for who has hearing issue.
- When Providing video provide the captions with "Get Transcript" link
- Avoid Text as a part of image.
- Avoid using link text that doesnt make sense e.g when text large description is displayed using turncated and prove "Read More" , In place of this provide descriptive 
"Read More About Product"

# HTML Attributes & Accessibility

- Language Attributes: 
Let the browser or assistive technology know what language the site is using

```
<html lang="en">

```

If displaying something in a differernt  language within the page, add the "lang" attribute

```
<blockquote lang="fr">

French text
</blockquote>

```
- Abbreviation tag: When adding abbreviation using abbreviation tag provide title with full discription.
The Title must contain the description for the word and nothing else.

```
<abbr title="Hyper text markup language">
HTML
</abbr>

```


- For Attribute: 
Connect labels with their associated form fields

```
<label for="firstName">
First Name
</label>
<input type="text" id="firstName" />

```

- Required Attribute: 
Provide more information for required fields
```
<label for="firstName">
First Name
</label>
<input type="text" id="firstName" required />

```

- Tabindex Attribute:  
It's more crucial when using keyboard but add it when needed. e.g when we built a custom button using our won logic
Forces non-standard controls into the tab order for keyboard navigation.

```
<span class="button" tabindex="5">
Submit
</span>

```

# Web Forms & Accessibility

Forms can be complex in order to make them accessible we need to make simple, we need to structure them in the logical order by grouping them in the Logical Groupings with Fieldsets and legends when its make sense.

- Fieldsets & Legends: Use them to logically group forms fields
```
<fieldset>
 <legend> billing Address</legend>
 <label for="billingAddress">Address</label>
 <input type="text" id="billingAddress" />
 
```

- Labels: Every field should have an associated label using the "for" attribute

- Placeholder attribute: 
We "SHOULD NOT" be using a placeholder for replacement of labels because its not widely supported.

Generally its "SHOULD" be used to provide hints and tips

```
<fieldset>
 <legend> billing Address</legend> 
 <input type="text" id="billingAddress" placeholder="Your Billing Address" />


```

- Hidden Labels
Its usefull when we are creating search control

```
<form id="sitesearch">
<label for="s" class="hidden">
Search This Site
</label>
 <input type="text" id="s" placeholder="Search this site" />
 <input type="button" value="GO" />
</form>
```

- Required: This attribute should be added to all required fields

```
<fieldset>
 <legend>Contact Us</legend> 
<label for="name">Your Name</label>
<span class="required">Required</span>
 <input type="text" id="name" placeholder="Your name" />


```
- Skip Nagivation Link: make it on of the 1st elements in the document.
use the id of the main content container in the "href" of the link
```
<head>
<title>Skip Link Example</title>
</head>
<body>
<a href="#primaryContent">
Skip to main context
</a>

```
# CSS & Accessibility
Browser provide default very basic Style to html elements. 
The style we provide has different levels of importance/President 
1. Default browser styles
2. Our external CSS
3. Style sheets embedded in the page. This will override the both browser and external css.
4. Inline styles on the individual control elements
5. End user accessibility setting adjustments: each individual has final choice how everything looks..e.g 
. how text size should be. 
. color setting increase/decrease the contrast.
. changed font who has reading deficiency.


# Preventing assistive technology for reading the content
. width: 0
. height: 0
. display: none
. visibility: hidden;

these prevent assistive technologies from reading their contents.

# When can screen reader read the hidden content: 
In this case screen reader read the content by providing long rectangular on the screen

```
{
text-indent:-9999px;
}

```
# Absolute Positioning
Positions the content off of the page, which will allow visual hidden text.

```
{
postion:absolute;
left: -9999px;

}
if we use top or right it will make browser to focus the control and scroll the page.

```

# CSS Clip Property
Nice way to provide visually hidden text.



```
{
postion:absolute;
clip:1px 1px 1px 1px;/* for ie 6 to 7
clip:1px, 1px, 1px ,1px;
}
```
- Focus & Active Indicators

Alway use css for Focus and active indicator.

```
:focus{
outline: dotted 2px #f06924;
}
:active{
outline: dotted 2px #39b54a;
transform: scale(0.8);
}
```
# Web Performance & accessibility

- Keep file size small
- Limit http requests: this is occurs for each assets e.g(images, fonts,stylesheet and script files) so fewer these files we have the faster page load.
- Optimize images: use optimize image technique e.g
. [JPEGmini](http://jpegmini.com/) for JPEG images without reduce quality.
. [tinypng](htpps://tinypng.com/) for png or jpg

- Image Sprites:
The idea behind them is place multiple images in single file and then we use css to cropp out the area and show. It reduces http request, it has caching advantage of browser side

- SVG graphics: use svg over jpeg because its 
. relatively small file sizes.
. Can be embedded difectly into html.
. Can be styled with CSS
. Greater flexibility
. It work with responsive design, scalable without loss in quality

# Inlining "Critical Path" CSS
More recently inlining or critical path css appears as a better practice. In this CSS used to create render tree for html document and javascript tends to block the externel CSS during the contruction of the page. So if we separate none essential CSS like print media other media queries, basically anything not render above the fold get this chunk of css down to smallest size as possible. And then inline in the document to elemenate round trip to the server. 

```
<!-- Critical Path CSS -->
<style type="text/css">
html, body{
...
...

}
a{
...
...
}



```
There are so many tools out there to automate this task
. [critical](https://github.com/addyosmani/critical)



# Progressive Enchancement & Accessibility
Not assuming with which technology a site is consumed is a key component in accessible web development, as assistive technology is so diverse.

1. Start with the lowest common demonimator
2. Well-structured HTML
3. Add in well-supported CSS
4. Add in more advanced CSS
5. Add in Javascript to further enchance the experince
this will allow us to make sure our contents are remain accessible to largest number of people

# Basic rule for ARIA
The Basic rule for ARIA is if there is semantic html elements that has the functionality that we need simply use it dont create your wont custom control if you have same functionality of native HTML elements. These aria attribute are design to be used for OS accessibility APIs so that assistive technology will interpret these widgets in the same way as a native control.

# Aria divided into two different categories

## Roles: what a widget is and what it does, it is used for things like
e.g.
. Menus
. Sliders
. Progress meters
. Modals
.etc

Roles are also used to Describe the Structrue. e.g.
. Headings
. Regions
. Tables

## States & Properties
States describe the current interaction state of widget
States e.g
. Checked
. Disabled
. Selected
. Hidden
Properties is more about characteristics of the widgets. Information widget that contained required elements
. Drag & Drop
. Live Regions
. Modals






# ARIA Roles
Aria Roles are categories in three types
- Landmark Roles : It helps for assesstive technology 
. Navigate the content.
. Describe common regions within the document
. Added "role" attributes


- role="application": 
Used if the region is considered an application, Tells assistive technology to switch to application browsing mode.

- role="banner": 
Generally the header of the site or application. This is likely to contain name of the application or title of the page.
It should be used once in the page.

- role="navigation": 
Contains navigation for the site or application.

- role="main": 
contains main content
It should be used once in the page.

- role="search": 
Added to the search form for the site or application.

- role="complimentary"
contains content that is complimentary to the main content for the document.

- role="form" : 
Add to anything that contains a collection of fields that makes up a form.

- role="contentinfo": 
Generally found in the footer provides information about the parent document.This should used once in a page.

- [Widget Roles:](http://www.w3.org/TR/wai-aria/roles#widget roles)
alert			    menuitem				    spinbutton
alertdialog		menuitemcheckbox		status
button			  menuitemradio			  tab
checkbox		  option					    tabpanel
dialog		  	progressbar				  textbox
gridcell		  radio					      timer
link			    scrollbar				    tooltip
log			      slider					    treeitem
marquee

This roles are used to describe the interactive elements that currently dont have HTML counter part, Here is the sub set that can be used as there won or as a part of larger composite widget

```
<html lang="en">
<head>.. </head>
<body>
<form action>
<fieldset>
<legend> Create an Account</legend>
<div class="field"> .. </div>
<div class="field"> .. </div>
<div class="field"> 
<label for="password">Create a Password</label>
<input aria-describedby="password-help" type="password" id="password" required>
<div role="tooltip" id="password-help"> Must be at least 8 characters long</div>
 </div>
<button>Create Account</button>
</fieldset>
</form>
</body>
</html>

```

- Container Roles:
There are sub set of Widget roles that can be used as a container for other content widgets are

combobox		menu				    tablist
grid			  menubar				  tree
listbox			radiogroup			treegrid

```
<nav role="navigaton">
<h2> Main Navigation</h2>

<ul role="menu" class="menu">
  <li role="menuitem" class="current">..</li>
  <li role="menuitem" >
    <a herf="#" aria-haspopup="true">Our Products</a>
    <ul role="menu" class="menu" aria-hidden="true">
      <li role="menuitem">..</li>
      <li role="menuitem" >..</li>
      <li role="menuitem">..</li>
      <li role="menuitem">..</li>
    </ul>

  </li>
  <li role="menuitem" >..</li>
  <li role="menuitem" >..</li>
</ul>
</nav>
```

- [Document Structure Roles:](http://www.w3.org/TR/wai-aria/roles#Document Structure roles)

This is used to described none interactive elements that provide the structure of the contains within the site or application



article				  img				      region
columnheader		list				    row
definition			listitem			  rowgroup
directory			  math				    rowheader
document			  note				    separator
group				    presentation		toolbar
heading 

```

<div role="note">
This article was last updated july 30, 2015 at 8:23PM.
</div>

```

# Proper Document Structure.
Its all about html semantics and using the right tag for the jobs. The proper document structrue should be written in such way that if we remove the CSS the page will still render and logical order and with proper hierarchy, it wont be necessary pretty but the content should be organized and heirarchy should remain clear.
HTML heading <h1> to <h6> are critical elements of Accessibility Pie.
It provide document outline which provides structure and shows how sections of the page is related to one another. They also provides the targets that some assisstive technology like screen reader can use to jump from section to section. It should be used in proper order e.g.
```
<main role="content">
<h1>I'm the Main Title</h1>
<p>I'm the Main description</p>
<h2>I'm the Secondary Title</h2>
<h1>I'm the Secondary description</h1>
</main>
```
In short no heading level should be skipped, meaning should never have <h5> heading without having nearest parent of it<h4>

# Use of HTML List

- Unordered List <ul> :
Use of unordered list when no order of sequence or importance is needed.

```
<ul>
  <li>Milk</li>
  <li>Bread</li>
  <li>Lettuce</li>
</ul>
```

- Ordered List <ol>: 

Use when order of sequence or importance IS needed
```
<ol>
  <li>First we need to do this</li>
  <li>Next we need to do this</li>
  <li>Lastly we need to do this</li>
</ol>
```

- Description List <dl>: 

Use when a description for each item is needed
```
<dl>
  <dt>Milk</dt>
  <dd>Fat free organic milk</dd>
  <dt>Bread</dt>
  <dd>Whole wheat sourdough</dd>
</dl>
```
# ARIA states & Properties: Normarlly referred to as an ARIA attributes

- ARIA States: Aria spec provides certain attribute to describe the Dynamic states of custom components. These state attribute normally updated with javascript when they need to change. These attribute Prefixed with "aria-"
Below is some example of aria state changes, which uses boolean values to reflect state change.

. aria-busy
. aria-disabled
. aria-grabbed
. aria hidden
. aria-invalid


- ARIA properties: It is primarily used to describe the Relationships between elements and almost never change like state do.
e.g
. aria-decribedby
. aria-flowto
. aria-haspopup
. aria-label
. aria-labelledby


# ARIA & Keyboard Control
Many assistive technologies use keyboard like functionality to navigate or interact with web. The problem is that often developers may forget or be unware it when they build custom widgets. The goal should be the keyboard control of application to function very similar to the way that it would if its native destop application

# Section 508
Its an Amendment to the United States Workforce Rehabilitaion Act of 1973. It was signed into law in 1998. It is put into the place that any Information technology that is purchased by fedral agencies be accessible by those with disabilities.
So section 508 is much more above web technologies, Its about all information technology every thing about hardware to software to the web.
Many of the standard are very similar to those in the WCAG.

# Testing for Accessibility
Easiest way to test the web accessibility stop using the mouse.
Use keyboard or assistive technology that memic the keyboard.
Use Screen Reader 
. [JAWS](http://www/freedomscientific.com/products/blindness/jaws)
. Mac user can use build in VoiceOver feature.
. Window [NVDA screen reader](http://www.nvaccess.org)

Accessiblity Tools
. WAVE
. [Colour Contrast Analyser](htpp://www.paciellogroup.com/resources/contrastanalyser/)
. chrome extension Accessibility Developer Tools
. [TENON](http://www.tenon.io)
An api that can be used to integrate accessibility testing into our existing toolsets.
Its extremely flexible, reliable and accurate.
Its written to test against the WCAG guidelines






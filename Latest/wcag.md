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

'''
<imag scr="som.png" alt="" />
'''

# Link Purpose

The link text should be sdlf-explanatory else can confuse to the user like (click here or read more).

# Images used for buttons
Possible avoid using image for button if it cant achieve through the CSS and you have to use image then provide alt text.

# Labels for Form Fields

3.3.2 Labels or Instructions: 
. When content requires user input, labels or instructions are provided.
. Labels in close proximity to inputs. os that if someone is using magnifier relationship should be clear.

'''
<label for="details-name">Name * </label>
<input type="text" id="details-name" />

'''

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


Define the label text for a control
'''
<input type="text" ariabe-label="Name" />

'''
States that the control is labelled by another contorl

'''
<input type="text" ariabe-labelledby="lblName" />
'''

If control has more than one label ID's in the attribute value put those IDs separated by a space to show that the control has two labels.
e.g.

For checkbox we can use multiple labels one is question and other is their answer, or we can go with fields in our ealier example we did it.


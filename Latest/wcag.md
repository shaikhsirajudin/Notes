# What's mean  by Accessibility?
Accessibility is the word used to describe product can be used by people of all abilities. 

# What is Web Accessibility?
The W3C say's that Web Accessibility means that people with disabilities can use the web. which make life easier for everyone and few people has to struggle


In general developer consider WCAG nice to have requirement and keep it in the phase two. Which when start they find themselves have to do redo lots of existing work its pretty frustrating process. It takes lot of time. 
If we consider WCAG at the start we will reduce the work significantly.


# To make Application with Web accessibility compatible the things need to keep in mind

1) Keyboard Accessibility
Web Form contents should be keyboard accessible with using the mouse.

2) Work with a Screen Reader
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

# What are the Web Content Accessibility Guidelines?
The Web Content Accessibility Guidelines(WCAG), Produced by the World Wide Web Consortium (W3C), the WCAG are the best means of making your website useful to all of your users.
They are not an all-inclusive list of issues facing web users with disabilities, these are internationally recognised and adopted standards. The guidelines explain how to solve many of the problems that your users with disabilities face.
There are two version of WCAG 
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
•Landmarks are provided to assist in screenreader navigation (e.g. meaningful page title, semantic headings, ARIA landmarks) meaningful headers and meaningful and unique link text.
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

The WAI-ARIA is a technical documents developed by the Accessible Rich Internet Applications Working Group (ARIA WG), which is part of the World Wide Web Consortium (W3C), Web Accessibility Initiative (WAI). 

WAI-ARIA provides Web authors with the following:

• Roles to describe the type of widget presented, such as "menu", "treeitem", "slider", and "progressmeter"
• Roles to describe the structure of the Web page, such as headings, regions, and tables (grids)
• Properties to describe the state widgets are in, such as "checked" for a check box, or "haspopup" for a menu.
• Properties to define live regions of a page that are likely to get updates (such as stock quotes), as well as an interruption policy for those updates—for example, critical updates may be presented in an alert dialog box, and incidental updates occur within the page
• Properties for drag-and-drop that describe drag sources and drop targets
• A way to provide keyboard navigation for the Web objects and events, such as those mentioned above

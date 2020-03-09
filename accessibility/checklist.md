---
title: Beginner Checklist
description: 
published: true
date: 2020-03-09T18:35:47.840Z
tags: 
---

# Beginner Checklist
The following guidelines are the WCAG 2.1 beginner guidelines - excluding the audio and video guidelines which you can find [here](http://172.31.2.178/en/accessibility/Audio&Video). All changes made to the user interface *must* meet these guidelines.

---
**[Guideline 1.1.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#non-text-content)**: Text alternatives should be given for all non-text content with few exceptions.
> Example: The Labor Program logo found on each LSF web page needs an alt text titled “Berea Labor Program Logo.” This can be done by implementing the following: `<img src="/static/laborprogram.png" alt=“Berea Labor Program Logo”/>`

**[Guideline 1.3.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#info-and-relationships)**: The information, structure, and relationships of the web page should be programmatically determined.
> Example: To help the screen reader identify structure use `<nav>` for navigation bars, `<side>` for sidebars, and `<main>` for anything unique on the web page.

**[Guideline 1.3.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#meaningful-sequence)**: The sequence of the web page should be programmatically determined.
> Example: When creating a list in HTML, use the appropriate tags:
>         `<ul>
>         <li></li>
>         <li></li>
>         </ul>`
        
**[Guideline 1.3.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#sensory-characteristics)**: Understanding the content on a web page should not be based on sensory characteristics such as shape, color, size, visual location, orientation, or sound.
> Example: Form validations - such as creating a new Labor Status Form - should not base empty required information on a red border. Instead, both text and alt text should be included with the color change.

**[Guideline 1.4.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#use-of-color)**: Color should not be a basis for understanding any content on the web page.
> Example: ![colorexample2.jpg](/colorexample2.jpg) ![colorexample.jpg](/colorexample.jpg)
>[photo credit](https://www.shopify.com/partners/blog/86314118-5-ways-to-improve-your-ecommerce-design-for-colourblind-users)

**[Guideline 2.1.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#keyboard)**: All functionality on the web page should be accessible through the keyboard with few exceptions.
> Example: The sample code listed below ([found here](https://www.w3schools.com/howto/howto_js_trigger_button_enter.asp)) allows the user to press the Enter key and have it work the same as clicking a button on a keyboard. “13” is the [keycode](https://keycode.info/) for the Enter key.
> `<script>
> var input = document.getElementById("myInput");
> input.addEventListener("keyup", function(event) {
>   if (event.keyCode === 13) {
>    event.preventDefault();
>    document.getElementById("myBtn").click();
>   }
> });
> </script>`

**[Guideline 2.1.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#no-keyboard-trap)**: Any element that a user can focus on by using the keyboard should also allow the user to exit focus by the keyboard. In other words, there should not be any keyboard traps.
> Example: Follow [this](https://interactiveaccessibility.com/education/training/ex7.1.html) link to experience an example keyboard trap.

**[Guideline 2.1.4](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#character-key-shortcuts)**: If there is a keyboard shortcut that only takes one letter there should be a way to either turn off this function, remap this function, or activate only on focus.
> Example: Let’s say we create an email user interface where clicking the letter “D” can delete an email. Allowing the user to turn off this function, change what letter triggers this function, or only having this function work when the user is actively writing an email would meet this criteria.

**[Guideline 2.2.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#timing-adjustable)**: For any time limits on the web page, the user should have the ability to either turn off, adjust, or extend the time limit. The three exceptions are real-time, essential, or 20 hour exceptions. *This does not apply to timeouts that you as the author do not have control over (for example, DUO).*
> Example: ![timeoutfafsa.png](/timeoutfafsa.png)

**[Guideline 2.3.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#three-flashes-or-below-threshold)**: No content should flash more than three times per second or is below the general flash and red flash threshold.
> Example: GIFs are an example of content that does **not** meet this requirement.

**[Guideline 2.4.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#bypass-blocks)**: There should be a way for the user to skip content that is repeated on multiple web pages.
> Example: For Labor Status Form, there should be a link titled “skip to main content” which bypasses the navigation bar and skips to main content. *This may be invisible to sighted individuals as long as it is accessible via keyboard.*

**[Guideline 2.4.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#page-titled)**: All web page titles should describe the topic or purpose.
> Example: The homepage for LSF says “Home - Labor Status Forms” on the browser’s title bar.

**[Guideline 2.4.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#focus-order)**: All web pages should be presented in an order that preserves meaning and operability.
> Example: The keyboard tabbing should make sense to the user. On the Supervisor homepage, it would make sense to go from the navigation menu straight to the download button. It would not make sense to jump down to the “Student Software Development Team” link.

**[Guideline 2.4.4](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#link-purpose-in-context)**: The purpose of any links on a web page should easily be understood through the link title or with the help of programmatically determined link context.
> Example: “**Created & Designed by the** [Student Software Development Team](http://172.31.2.92/contributors)”  found on the bottom of each page on LSF is a great example. This phrase tells the user that by following the link they will be able to see who created and designed the website.

**[Guideline 2.5.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#pointer-gestures)**: Any functionality that uses multipoint or path-based gestures should also be possible with a single pointer non path-based gesture, unless essential.
> Example: Google Maps allows the user to either pinch with two fingers to zoom (multipoint gesture) or press the “plus” or “minus” button to zoom (single pointer).

**[Guideline 2.5.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#pointer-cancellation)**: Single pointer functionalities should have at least one of the following: no down-event, abort/undo option, up-event reversal, or the single pointer functionality is essential. 
> Example: Labor Status Form meets this requirement by implementing the “up-event reversal” and “undo” requirement. For “up-event reversal,” if the user tries to click on any button/link but moves their cursor at the last minute out of that button/link, nothing will happen.

**[Guideline 2.5.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#label-in-name)**: There should be an accessible text for all user interface components with labels that include text or images of texts. 
> Example: If you would like to read more [examples of how to meet this WCAG requirement](https://www.w3.org/WAI/WCAG21/Techniques/general/G211), please follow the link provided.

**[Guideline 2.5.4](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#motion-actuation)**: Any functionality that can be operated by device or user motion should also have the option to be operated by user interface components. Motion should have the option to be disabled, to prevent accidental actuation. The two exceptions are if the action is on a supported application or is essential.
> Example: One example of this would be the “shake to undo text” which is popular on phones. The user can also use the “backspace” on the keyboard to complete this action. There is also a way to turn off this motion in the Settings.

**[Guideline 3.1.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#language-of-page)**: The default human language of each web page should be clear.
> Example: The default language can be determined by HTML. In our case, it should always be English.

**[Guideline 3.2.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#on-focus)**: Context should not change when a component is put into focus. 
> Example: On the Labor Status Form page, tabbing to or hovering over the Supervisor dropdown will not immediately draw focus to the dropdown. The dropdown will not open until the user either clicks enter/space when on the form or clicking on the dropdown with their cursor. 

**[Guideline 3.2.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#on-input)**: Context should not change when a user gives input unless the user is warned of such. Changes of content include user agent, viewport, focus, and content that changes the meaning of the webpage.
> Example: Using `button=submit` that takes you to a new page would meet this requirement.

**[Guideline 3.3.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#error-identification)**: Input errors should be automatically detected and described to the user in text.
> Example: Below is a picture that does not meet this guideline. The error message simply reads “Please fill out all fields before submitting” which does not describe what is actually wrong to the user. To fix this error message, it could instead read “Please fill out the hours per week field before submitting.”
![example.png](/example.png)

**[Guideline 3.3.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#labels-or-instructions)**: Labels and instructions should be provided when content requires user input.
> Example: On the Labor Status Form page under “Supervisor” the user is instructed to “Select Supervisor.”

**[Guideline 4.1.1](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#parsing)**: Any content created in markup language should have start and end tags, should be nested according to their specifications, should not contain duplicate attributes, and IDs should be unique.
> Example: To simplify this guideline, use the formal specifications for all markup languages. If you would like to validate your work please click [here](http://www.chami.com/html-kit/faq/pages/validate_tools.html).

**[Guideline 4.1.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#name-role-value)**: All user interface components (form elements, links, components generated by scripts, etc) should have the name and role programmatically determined. All states, properties, and values that can be set by the user should be programmatically set. All notifications of changes should be available to user agents, including assistive technologies.
> Example:
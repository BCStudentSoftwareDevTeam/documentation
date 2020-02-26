---
title: Beginner Checklist
description: 
published: true
date: 2020-02-26T20:28:13.079Z
tags: 
---

# Beginner Checklist
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
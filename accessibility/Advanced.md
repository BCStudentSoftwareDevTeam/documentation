---
title: Advanced Checklist
description: 
published: true
date: 2020-05-11T15:18:46.581Z
tags: 
---

# Advanced Checklist
The following guidelines are the WCAG 2.1 advanced guidelines - excluding the audio and video guidelines which you can find [here](http://172.31.2.178/en/accessibility/Audio&Video).


---

**[Guideline 1.3.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#identify-purpose)**: The purpose of User Interface Components, icons, and regions can be programmatically determined.
> Example: This example is provided by Deque University and is as follows: A user with a cognitive disability after a concussion has difficulty focusing and processing words. Their assistive technology is able to use the metadata provided with a webpage so that they can turn off the page sections other than the form they are focusing on, and replace some of the form labels with icons that they recognize and process more easily than words.

**[Guideline 1.4.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#contrast-enhanced)**: The contrast ratio of text and images of text should be set to at least 7.1 except for logos.
> Example:  [This](https://developer.paciellogroup.com/resources/contrastanalyser/) color contraster will test the contrast between text and images of text to ensure they meet the 7:1 contrast.
![colorcontrast.png](/colorcontrast.png)
[Photo Credit](https://miro.medium.com/max/673/1*-LTzorP9ozKGowIW7sPS7w.png)

**[Guideline 1.4.8](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#visual-presentation)**: The web page should give users the option to change the presentation through color, width, line spacing, and text size.
> Example: This can be met through not specifying text and text-background colors to allow the user to change that information. It can also be met by ensuring that the user can change the presentation in the browser settings.

**[Guideline 1.4.9](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#images-of-text-no-exception)**: Images of text should only be used for decoration or to convey information.
> Example: The LSF web site contains the Labor Office’s logo in the top right corner of each web page. The logo contains a logotype (text as part of the logo). The visual presentation of the text is essential to the identity of the logo and is included as a gif image which does not allow the text characteristics to be changed. *The image has a text alternative.*

**[Guideline 2.1.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#keyboard-no-exception)**: All functionality on the web page should be accessible through the keyboard without exceptions.
> Example: This guideline is self-explanatory. Everything should be accessible through the keyboard without exception.

**[Guideline 2.2.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#no-timing)**: There should not be any time limits on the web page.
> Example: This guideline is self-explanatory. There should be no time limits to meet this requirement.

**[Guideline 2.2.4](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#interruptions)**: The user should have the option to postpone or suppress interruptions, except in cases of emergency.
> Example: This will most likely not be relevant to anything the Student Programmers create as we do not handle updates or alerts. However, an example would be the preferences page of a Web portal includes an option to postpone all updates and alerts until the end of the current session, except for alerts concerning emergencies.

**[Guideline 2.2.5](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#re-authenticating)**: All data should be saved when the authentication session expires. 
> Example: This will most likely not be relevant to anything the Student Programmers create as we do not handle authentication sessions. However, an example would be saving a shopping cart when checking out online.

**[Guideline 2.2.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#timeouts)**: The user should be warned of any timeout that will result in the loss of data. This does not apply to situations in which there is no user interaction for at least twenty hours.
> Example: A user with cognitive disabilities starts to fill out a hotel registration and soon becomes overwhelmed. The user should be able to come back to the hotel registration form within the twenty hour limit and start from where they left off or the user should be warned when the time limit for data is about to be lost.

**[Guideline 2.3.2](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#three-flashes)**: No content should flash more than three times per second.
> Example: GIFs are an example that would not meet this requirement. They flash more than three times per second.

**[Guideline 2.3.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#animation-from-interactions)**: There should be an option to disable motion animation that is not essential to the functionality of the information being conveyed.
> Example: [Here](https://davideperozzi.com/) is a website that uses parallax scrolling. It does **not** meet this guideline requirement as there is no way to stop the motions.

**[Guideline 2.4.8](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#location)**: It should be clear to the user where they are located.
> Example: A portal Web site organizes topics into categories. As the user navigates through categories and subcategories, a breadcrumb trail shows the current location in the hierarchy of categories. Each page also contains a link to the portal home page.

**[Guideline 2.4.9](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#link-purpose-link-only)**: The purpose of links should be clear from the link text alone.
> Example: A list of books is available in three formats: HTML, PDF, and mp3 (a recording of a person reading the book). The title of the book is followed by links to the different formats. The rendered text for each link is just the format type, but the text associated with each link includes the title as well as the format; for instance, "Gulliver's Travels, MP3."

**[Guideline 2.4.10](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#section-headings)**: Section headings should be used to organize content.
> Example: A Web application contains a settings page that is divided into groups of related settings. Each section contains a heading describing the class of settings.

**[Guideline 2.5.5](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#target-size)**: The size of the target for pointer inputs is at least 44 by 44 CSS pixels except when the target is available through a link or other control, the target is a sentence or block of text, the size can be determined by the user, or the target size is essential. 
> Example: All buttons on the LSF web page should be 44 by 4 CSS pixels.

**[Guideline 2.5.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#concurrent-input-mechanisms)**: Any input modalities such as keyboards or mouse should be available on a platform except when the restriction of one is essential, required to ensure security, or required to respect the user settings.
> Example: On a touch-enabled laptop with coarse precision, people who have difficulty activating a small target because of hand tremors, limited dexterity or other reasons are still able to interact with content using their keyboard and trackpad.

**[Guideline 3.1.3](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#unusual-words)**: Any unusual words or phrases such as idioms or jargon should be defined.
> Example: While this will most likely not be an issue, jargon would include phrases such as “bang for your buck.” These phrases would then need to be defined, either immediately after the word or in a glossary.

**[Guideline 3.1.4](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#abbreviations)**: The expanded form of abbreviations should be available.
> Example: The first instance of LSF should be expanded to “Labor Status Forms” on the webpage.

**[Guideline 3.1.5](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#reading-level)**: The content should be understood by someone with a lower secondary education level.
> Example: This would be a sixth grade reading level. There should not be use of SAT/ACT words.

**[Guideline 3.1.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#pronunciation)**: Any words that may be hard to pronounce are explained.
> Example: This would be anything over a sixth grade reading level. If you must use a difficult word, you may either provide the definition or the International Phonetic Alphabet (IPA) of the word directly following the word.

**[Guideline 3.2.5](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#change-on-request)**: Changes of context should be initiated by the user.
> Example: Instead of automatically updating the content, the author provides an "Update now" button that requests a refresh of the content.

**[Guideline 3.3.5](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#help)**: There should be context-sensitive help provided.
> Example: This could be through providing spell checks and suggestions for text input, providing expected data formats,and providing a help link on every page.

**[Guideline 3.3.6](https://www.w3.org/WAI/WCAG21/quickref/?currentsidebar=%23col_overview&showtechniques=222#error-prevention-all)**: Any web pages that require the user to submit information should have either the option to reverse, check or confirm the information.
> Example: This is almost always met with the interfaces that we build. For example, the Manage Department page on LSF allows the user to easily **reverse** their decision. The LSF page **checks** the information the user inputted to verify that the information matches the expected format and database. It will then ask the user to **confirm** the information before submitting by clicking “submit.”
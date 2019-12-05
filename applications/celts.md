---
title: CELTS Application Documentation
description: User documentation for the CELTS form and spreadsheet
published: true
date: 2019-12-05T17:02:20.469Z
tags: 
---

# Application Usage

The CELTS application (right now) uses a combination of Google Forms and Google Sheets. Data is entered using the Form or Custom List Entry sheet.

When new data comes in, the application processes it and generates a 'clean' data record in the Clean Data sheet. This record has all of the information necessary for further reports, including B# and Bonner indicator, even though those were not entered through the form.

To avoid creating work that could be erased, don't edit the Clean Data spreadsheet directly. All data problems should be fixable through the Form Responses 1, Missing Identifiers, and SOURCE sheets. This way, all of the cleaned data can be regenerated in the event we want to add new features or we change how we process the form data, without losing work or data.

**Form:** https://docs.google.com/forms/d/e/1FAIpQLScW--f3r-8TO2KuVD115YjwmEcTq3Xmq8OWuGCnc0l9X0PQjA/viewform
**Spreadsheet:** https://docs.google.com/spreadsheets/d/1aptu-xZg7a1Cvtpzf8qM-qgidENp0EvDbZmASTuWbAU/edit

## Setup

Copy and paste a list of all student names and B# into the SOURCE - Student B# sheet. This is what the application uses to assign a B# to each cleaned record. 

Edit the SOURCE - Programs sheet to add pre-defined groups of students, and choose the Update Form Groups menu item from the CELTS Management menu.

## Labor Hours Entry

Labor hours can be entered for an individual, but the most likely method is to enter a group using the Custom List Entry sheet. The fastest way to do this is to get a spreadsheet of the labor students and their corresponding hours, and paste the two columns with name and hours into the Custom List Entry sheet. Then, choose the Process Custom Student List menu item from the CELTS Management menu.

## Volunteer Hours Entry

Volunteers can be entered as individuals and groups. If there is a standard list of students likely to be at an event, you can add them in the SOURCE - Programs sheet so they are available in the form. You can also copy and paste a list of students into the Cust om List field on the form if they all share the same number of hours, or into the Custom List Entry sheet in the spreadsheet, if they each have their own hours.

## Service Learning Classes Entry

To enter an entire class for Service Learning, choose the Group entry option in the form, enter the name of the class, and then paste a comma-separated or newline separated list of students into the field.

## Indicating Bonner Scholars

To report on what students in the Bonner Scholars program are doing, add the names of the Bonner scholars to the SOURCE - Bonner sheet. Don't edit Clean Data directly.

## Fixing Missing B#

If a Clean Data record is missing the B# for a student, this is likely due to a name mismatch. Check the SOURCE - Student B# sheet for the student to see what the problem is. If the name was misspelled, you can either fix the name in the Form Responses 1 sheet, or you can add the B# to the automatically created record in the Missing Identifiers sheet. If the name is just an alternate or more common form of the name, use Missing Identifiers rather than changing the SOURCE entry (so it will persist if a new student list is copied in).

## Changing Predefined Programs and Groups

If you have a common list of students associated with a program, you can set up the form to provide those students as options for quicker group entry. Edit the SOURCE - Programs sheet with the programs and their lists of students, then choose the Update Form Groups menu item from the CELTS Management menu.

If you have removed an entire program, you will need to choose the Reset Form Questions menu item, and then use Update Form Groups to add the groups back. See caveat below about fixing the group question after resetting the form.

## Caveats

If you use the Reset Form Questions item to remove all of the groups, there is an additional step you need to take on the form. *After adding the Groups back in* with Update Form Groups, you will need to manually add the Other option to the Group selection question. No idea why the script is unable to do this automatically - it gives an error.


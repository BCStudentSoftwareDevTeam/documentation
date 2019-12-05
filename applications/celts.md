---
title: CELTS Application Documentation
description: User documentation for the CELTS form and spreadsheet
published: true
date: 2019-12-05T16:44:06.522Z
tags: 
---

# Application Usage

## Labor Hours Entry

Labor hours can be entered for an individual, but the most likely method is to enter a group using the Custom List Entry sheet. The fastest way to do this is to get a spreadsheet of the labor students and their corresponding hours, and paste the two columns with name and hours into the Custom List Entry sheet. Then, choose the Process Custom Student List menu item from the CELTS Management menu.

## Volunteer Hours Entry

Volunteers can be entered as individuals and groups. If there is a standard list of students likely to be at an event, you can add
them in the SOURCE - Programs sheet so they are available in the form. You can also copy and paste a list of students into the Cust
om List field on the form if they all share the same number of hours, or into the Custom List Entry sheet in the spreadsheet, if th
ey each have their own hours.

## Service Learning Classes Entry

To enter an entire class for Service Learning, choose the Group entry option in the form, enter the name of the class, and then pas
te a comma-separated or newline separated list of students into the field.

## Indicating Bonner Scholars

To report on what students in the Bonner Scholars program are doing, add the names of the Bonner scholars to the SOURCE - Bonner sheet.

## Changing Predefined Programs and Groups

If you have a common list of students associated with a program, you can set up the form to provide those students as options for quicker group entry. Edit the SOURCE - Programs sheet with the programs and their lists of students, then choose the Update Form Groups menu item from the CELTS Management menu.

If you have removed an entire program, you will need to choose the Reset Form Questions menu item, and then use Update Form Groups to add the groups back. See caveat below about fixing the group question after resetting the form.

## Caveats

If you use the Reset Form Questions item to remove all of the groups, there is an additional step you need to take on the form. *After adding the Groups back in* with Update Form Groups, you will need to manually add the Other option to the Group selection question. No idea why the script is unable to do this automatically - it gives an error.


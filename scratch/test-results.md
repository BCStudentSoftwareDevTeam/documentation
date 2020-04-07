---
title: Test Results
description: 
published: true
date: 2020-04-07T13:02:41.323Z
tags: 
---

# Test Results

There are two return statements back-to-back in the populateModal and ConvertPdf methods, and neither of them uses an error code.
 `app/controllers/main_routes/laborHistory.py`
 
-----

The error case for these routes do not return a 500 code, so there is no indication that something is wrong (to a test).

* `/laborHistory/modal/printPdf/<statusKey>`
* `/admin/emailTemplates/getPurpose/<recipient>`
* `/admin/emailTemplates/getEmail/<purpose>`
* `/laborstatusform/getcompliance/<department>`
* `/laborstatusform/getPositions/<department>`
* `/laborHistory/modal/<statusKey>`
* `/admin/pendingForms/<formType>`
* `/admin/getNotes/<formid>`
* `/main/department/<departmentSelected>`
* `/laborHistory/<id>`
-----

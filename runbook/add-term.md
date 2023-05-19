---
title: Add BCSR Courses
description: 
published: true
date: 2023-05-19T18:29:35.632Z
tags: 
editor: markdown
dateCreated: 2023-05-19T18:19:19.212Z
---

- Get xlsx from Registrar and convert to csv
- Copy file to `/var/www/html/bcsr-flask/terms_csv` on bcsr server
- Follow instructions in `addNewTerm.py`. Roughly,
  - Back up database
  - Add new term in bcsr application
  - update file variables to match your .csv
  - make sure column indices match your .csv
  - execute `addNewTerm.py`
- Verify courses exist in your new term: https://bcsr.berea.edu/courses
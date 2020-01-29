---
title: LSF Demo - 01/29/2020
description: 
published: true
date: 2020-01-29T22:04:39.581Z
tags: 
---

Demo of Labor Status Forms for Labor Office
--------------------------------------------

**Notes from Labor Office**
*Brian's Comments*

### Demonstrating Administration capabilities
 - Administrators
 - Terms
 - Departments
 - Email Templates

### Demonstrating Labor Status Form creation

Question - Can they backdate forms
 - They like that we restrict LSF dates to be within the term dates

**Add 12 to the Hours Per Week dropdown**
Easy 3, Valuable 3

**Make "Students should not work any hours" bold or emphasized in the Overload warning modal**
Easy 3, Valuable 2


Question - can larger departments select multiple students at once
**Investigate using a multi-select for student dropdown**
*EDIT: Just don't clear the field inputs - Alex. Make sure that the table is persistent until submitted*
Easy 2, Valuable 3

*What would the Review modal look like if there are, say, 20 LSFs*

Question - do we show errors for first year LSF
**First year, first semester students should not be allowed to have a Secondary position**
Complete Solution - Easy 1, Valuable 3
Partial Solution - Easy 2, Valuable 2
Partial Solution - warn on form if the student classification is freshman/first-year, warn on admin page somewhere

Question - limiting Primary form after a submission deadline
**Add a cutoff date to each term, after which Primary submissions are disallowed**
Easy 2, Valuable 3

Question - do supervisors get flagged if there is another submission for a student during a break?
**Warn supervisors if a student has multiple forms during a break. Email both supervisors with reminder about hours limit.**
Easy 2, Valuable 2

**Add summer term requirements modal when submitting a form for a summer term**
Easy 3, Valuable 2


### Demonstrating Pending Forms

**Increase default # of entries to 50**
*Implement UI for paging through multiple reviewed forms*
Easy 3, Valuable 3

**Change Admin note display to a log view**
*Does that mean we need to change how we store notes? Or do we handle that already?*
Easy 1, Valuable 3

*Standardize notes icon
Easy 3, Valuable 2

### Demonstrating Modify Labor Status Form

Question - are we missing hours worked in the Modify form
**Add hours back in to the Modify form**
Easy 3, Valuable 3

Question - What about position adjustment after approval
**We need to implement form adjustment after approval**
Easy 1, Valuable 3 +++

*I didn't see the option to enter a reject reason when Denying a form*
**Create modal to enter Reject Reason when denying a form**
Easy 2, Valuable 3

### Demonstrating Supervisor Portal

Questions - limiting information about student labor history across departments 
**No inter-departmental history for supervisors**
Easy 1, Valuable 3 +++

Question - can we handle removing a form rather than denying it
Yes, through the supervisor portal

Question - supervisors often enter incorrect dates for release forms
**Find some way to allow future releases?**
**Short term: Remove default date from release form**
*Requires controller re-work to fix the button display*
Easy 2, Valuable 3

*If there is only one department in My Department, it should be automatically selected*
**Admins should be able to see all departments in My Department, even if empty**
Easy 3, Valuable 1


### Wrapup

**Change Logo**
Easy 3, Valuable 3 +++

Question - What happens with the current historical data?
At least for now, two separate systems.

Question - What about overload form process?
Explained.

Question - financial aid can give approval for specific term, when a position carries over multiple terms
*Explore letting financial aid approve for shorter terms than the original position. Detect 'sub-terms' in full terms? Editable contract dates on pending forms?*
Easy 1, Valuable 3

Question - Can SSDT replace SOAR?

SOAR - Career development software, internal indeed.com for students
* Contains student resumes (exportable)
* Contains campus job descriptions for students

There is discussion about whether having a form for resume submission eliminates the educational benefit of creating the initial resume.

Features:
* Supervisor request for top X students
* Supervisor search through resumes
* Students see job descriptions that are open - browsable and searchable

Discussion - Replace Labor Evaluations (Smart Evals)

Vision - Create a Labor portal where supervisors can handle labor status forms, job descriptions, labor evaluations, etc.

Department Allocations
**report of current and past department allocations**
Easy 2, Valuable 2
**future - admin interface for setting department allocations**
**future - request for more allocations**
**future - warning when departments exceed allocations**
Easy 1, Valuable 3

### Post-demo discussion

* Still need Approve Reluctantly clarification
* Restricting adjustments to form after the last drop day (add button to term, think of good naming)



### Next Steps

URL - lsf.berea.edu, old site at labor.berea.edu/forms
Connections with Banner and ultratime
Finish required features
'Live' system used for demo for a while

DEPLOY



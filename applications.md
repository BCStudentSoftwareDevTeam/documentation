---
title: Applications
description: The applications in development or managed by the SSDT
published: true
date: 2023-03-30T16:49:07.354Z
tags: 
editor: markdown
dateCreated: 2019-10-04T20:30:08.140Z
---

# Our applications
These applications are directly developed by our team.

## Berea College Syllabus Repository
Stores all course syllabi across campus for SACSCOC compliance.

**Point of Contact:** Scott Steele <steeles@berea.edu>, Sam Cole <colesa@berea.edu>
**Application Link:** https://bcsr.berea.edu
**Production IP(s):** 192.68.112.65
**Production VM(s):** IS&S VM `Bcsr`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/bcsr
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/bcsr#readme)
**End User Documentation:**

## Course Administration & Scheduling
Facilitates scheduling and room selection prior to course entry in Banner.

**Point of Contact:** Judy Ginter <ginterj@berea.edu>, Scott Steele <steeles@berea.edu>
**Application Link:** https://cas.berea.edu
**Production IP(s):** 192.68.112.108
**Production VM(s):** IS&S VM `CAS`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/cas
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/cas#readme)
**End User Documentation:**

## Labor Status Forms
Entry and tracking of all labor forms and student labor assignments at Berea.

**Point of Contact:** Armando Buenrostro <buenrostroa@berea.edu>
**Application Link:** https://lsf.berea.edu or https://labor.berea.edu
**Production IP(s):** 192.68.112.111
**Production VM(s):** IS&S VM `CS-LSF`
**Staging IP:** 172.31.2.92
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/lsf
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/lsf#readme)
**End User Documentation:**


## Chemical Inventory Management
Tracks chemicals from the Berea College chemical bunker and their movements to labs around campus.

**Point of Contact:** Andrew Garrett <garretta@berea.edu>
**Application Link:** https://chemical.berea.edu
**Production IP(s):** 192.68.112.214
**Production VM(s):** IS&S VM `Chemical`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/chemical-inventory
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/chemical-inventory#readme)
**End User Documentation:**


## Ulmann Galleries
Ulmann Galleries is a management tool for gallery application entries. It provides an easy way to accept applications from artists that want to show their work in a Berea College Gallery Showing.

**Point of Contact:** Kelsey Malone <malonek2@berea.edu>
**Application Link:** http://ulmann.berea.edu
**Production IP(s):** 52.15.206.17
**Production VM(s):** AWS EC2
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/Ullman_Galleries
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/Ullman_Galleries#readme)
**End User Documentation:**


## Undergraduate Research and Creative Projects Program
Collects proposals for summer projects and provides tools for review by the committee.

**Point of Contact:** Jim Strand <strandj@berea.edu>
**Application Link:** https://urcpp.berea.edu
**Production IP(s):** 192.68.112.107
**Production VM(s):** IS&S VM `CS-URCPP`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/urcpp
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/urcpp#readme)
**End User Documentation:**


## CELTS Link
Records volunteer, labor, and service learning hours for CELTS participants across different projects, events, classes and teams. *In Progress*

**Point of Contact:** Ashley Cochrane <cochranea@berea.edu>
**Application Link:** https://celts-link.berea.edu
**Production IP(s):** 192.68.112.131
**Staging IP:** https://celts-staging.berea.edu
**Production VM(s):** IS&S VM `CS-CELTS`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/celts
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/celts#readme)
**End User Documentation:** [Wiki](celts)

# Supported applications
These applications are not directly developed by the SSDT but we support them either for external clients or for our own use.

## Berea College Art Collection
Keeps track of art and artifacts both on and off-campus.

**Point of Contact:** Kelsey Malone <malonek2@berea.edu>
**Application Link:** https://bcac.berea.edu/
**Production IP(s):** 192.68.112.109
**Production VM(s):** IS&S VM `CS-BCAC`
**Available Externally:** Yes
**Repository:** https://github.com/BCStudentSoftwareDevTeam/Art-Archives
**Setup Documentation:** [README.md](https://github.com/BCStudentSoftwareDevTeam/Art-Archives#readme) and [bcac_sftp](bcac_sftp)
**End User Documentation:**

## Loyal Jones Collective Access
Inventory and catalog of physical artifacts in the Loyal Jones Appalachian Center.

**Point of Contact:** Christopher A. Miller <millerc@berea.edu>
**Application Link:** https://ljacatc.berea.edu/
**Production IP(s):** 192.68.112.130
**Production VM(s):** IS&S VM `CS-ACA`
**Available Externally:** Yes
**Repository:** https://github.com/collectiveaccess/providence.git
**Setup Documentation:** [README.md](https://github.com/collectiveaccess/providence/blob/master/README.md)
http://ssdt-documentation.berea.edu/en/applications/collective-access
**End User Documentation:**

## SSDT Documentation
All of the documentation for our team and applications is contained in Wiki.js. The pages are also stored as .md files and are synced with this repository: https://github.com/BCStudentSoftwareDevTeam/documentation. Any .md files edited in this repo will be updated in the wiki.

**Point of Contact:** Brian Ramsay <ramsayb2@berea.edu>
**Application Link:** http://ssdt-documentation.berea.edu
**Production IP(s):** 172.31.2.178
**Production VM(s):** CS VM - `documentation`
**Available Externally:** No
**Repository:** https://github.com/BCStudentSoftwareDevTeam/documentation
**Setup Documentation:** 
**End User Documentation:**

## SSDT Jenkins
Our continuous integration and deployment server runs Jenkins in a docker container. SETUP IN PROGRESS.

**Point of Contact:** Brian Ramsay <ramsayb2@berea.edu>
**Application Link:** http://172.31.2.60
**Production IP(s):** 172.31.2.60
**Production VM(s):** CS VM - `jenkins`
**Available Externally:** No
**Repository:** 
**Setup Documentation:** 
**End User Documentation:**

## CELTS Staging
A staging server for the celts-link application.

**Point of Contact:** Brian Ramsay <ramsayb2@berea.edu>
**Application Link:** http://172.31.2.98/
**Production IP(s):** 172.31.2.98
**Production VM(s):** CS VM - `celts-staging`
**Available Externally:** No
**Repository:** https://github.com/BCStudentSoftwareDevTeam/celts
**Setup Documentation:** 
**End User Documentation:**

## EE Signals Documentation
Documentation for the Electrical Engineering lab.

**Point of Contact:** Brian Ramsay <ramsayb2@berea.edu>
**Application Link:** http://172.31.3.95
**Production IP(s):** 172.31.3.95
**Production VM(s):** CS VM - `ee-lab-documentation`
**Available Externally:** No
**Repository:** https://github.com/BCStudentSoftwareDevTeam/ee-lab-documentation
**Setup Documentation:** 
**End User Documentation:**

# Retired Applications
These are applications that were developed by the student programmers but have been removed from service.

## Advancement Office
Manages requests for institutional data.

**Point of Contact:** Dorothy Morgan <morgando@berea.edu>, Sue Johns <johnss@berea.edu>
**Application Link:** https://advancement.berea.edu
**Production IP(s):** 172.31.2.146
**Production VM(s):** CS - advancement
**Available Externally:** No
**Repository:** https://bitbucket.org/laborstudents/advancementoffice
**Setup Documentation:** [README.md](https://bitbucket.org/laborstudents/advancementoffice/src/development/README.md)
**End User Documentation:**

## LSF in C#
Entry and tracking of all labor forms and student labor assignments at Berea.

The servers have been decommissioned. The code is at https://bitbucket.org/laborstudents/labor-status-forms.


## CELTS Time Tracker
Records volunteer, labor, and service learning hours for CELTS across different projects, events, classes and teams. *In Progress*

**Point of Contact:** Ashley Cochrane <cochranea@berea.edu>
**Application Link:** Google Spreadsheet
**Production IP(s):** N/A
**Production VM(s):** N/A
**Available Externally:** N/A
**Repository:** https://bitbucket.org/laborstudents/celts-tracker-google-app-script/
**Setup Documentation:** [README.md](https://bitbucket.org/laborstudents/celts-tracker-google-app-script/src/master/README.md)
**End User Documentation:** [Wiki](celts)
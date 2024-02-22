---
title: Documenting Your Code
description: 
published: true
date: 2024-02-22T19:18:55.910Z
tags: 
editor: markdown
dateCreated: 2024-02-22T19:18:55.910Z
---

# Documenting Your Code
## What makes a function well documented?
- Clear and descriptive docstring
- Example of a good docstring (in app/logic/participants.py):
```
def sortParticipantsByStatus(event):
    """
    Takes in an event object, queries all participants, and then filters those
    participants by their attendee status.
    return: a list of participants who didn't attend, a list of participants who are waitlisted,
    a list of participants who attended, and a list of all participants who have some status for the 
    event.
    """
```
- Sometimes you can OVER document functions and code. There is a good balance between spelling out what really simple code is doing and leaving confusing code completely undocumented.
- If what is being returned is confusing, state what it is doing. Same with parameters.
- Concise but clear comments
- Good example:
```
# get all RSVPs for event and filter out those that did not attend into separate list
eventRsvpData = list(EventRsvp.select(EventRsvp, User).join(User).where(EventRsvp.event==event).order_by(EventRsvp.rsvpTime))
eventNonAttendedData = [rsvp for rsvp in eventRsvpData if rsvp.user not in eventParticipants]
```
- Poor example:
```
# if event is in the past
if event.isPast:
```
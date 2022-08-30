---
title: Peer Review
description: How to thoroughly review a pull request
published: true
date: 2022-08-30T15:45:04.866Z
tags: dev, guidelines
editor: markdown
dateCreated: 2022-08-30T15:45:04.866Z
---

# Peer Review
The process of peer review is an important step in maintaining software quality. In order to properly review code a reviewer must be good at reading and understanding code, as well as executing it in her head. This also happens to be a critical skill for any software developer. Getting better at reviewing code will make you a better programmer.

#### Recommended Reading
[Google's Code Review Developer Guide](https://google.github.io/eng-practices/review/) - This is all good, but specifically for this list, read [What to look for in a code review](https://google.github.io/eng-practices/review/reviewer/looking-for.html).
[Yelp's Code Review Guidelines](https://engineeringblog.yelp.com/2017/11/code-review-guidelines.html) - Talks about the overall process as a whole, for both reviewer and developer.
[Swarmia's Complete Guide](https://www.swarmia.com/blog/a-complete-guide-to-code-reviews/) - Higher level, not so much a complete guide as a summary

## Correctness
- Does the build pass? #1 check. If it fails, move on to the next PR to review.
- Does the UI work as expected? 
- Does the UI still work in other, related areas of the application?
- Does the fix meet requirements?
- Are tests added for new functionality? Are they correct? Will they fail as expected?
- Is the code efficient enough? (but remember, ["Premature optimization is the root of all evil"](http://wiki.c2.com/?PrematureOptimization))
- Are errors handled appropriately, with a distinction between debugging messages and user information messages? 
- HTML - Are the id attributes for html elements unique?
- JS - Is javascript executing in or after `document.onready`?

## Maintainability
- Is the code readable? 
- Are function and variable names clear, consistent, and informative?
- Are [coding style guides](http://ssdt-documentation.berea.edu/en/ssdt-program/coding-conventions-and-style-guides) followed?
- Is the code decomposed into functions properly?
- Are we duplicating any functionality?
- Have we avoided negative conditionals where possible (especially double negatives)?
- Is development debug output removed?

### Comments (a special subsection)
- Do new functions have a helpful docstring?
- Are comments correct? 
- Do they provide clarity?
- Can you read them in the flow of the code? (end-of-line comments are usually bad)
- If a comment is necessary to explain the code, is it because the concept is tricky or because the code is unnecessarily confusing?



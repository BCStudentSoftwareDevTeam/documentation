---
title: Handling Line Endings
description: 
published: true
date: 2020-07-13T12:56:40.069Z
tags: dev
---

# Handling Line Endings
Text files use symbols to indicate the end of a line depending on the operating system involved. There are two non-printable characters used to denote the end of a line: Carriage Return (CR) and Line Feed (LF). Windows programs by default use both symbols (CRLF), while Unix systems, including modern Mac OS systems use only LF. Legacy Macintosh operating systems further complicated things and used CR only.

We should not be mixing and matching line endings. All line endings in our repositories should only use LF.

## Checking line endings
### Linux / Mac OS
The `file` utility can be used to investigate a file type, producing results like this:

    ramsayb2:~/dev/lsf-flask %>file app.wsgi
    app.wsgi: Python script text executable, ASCII text, with CRLF line terminators`

To check your entire repository for bad line endings, use this command: 
`find . -type f 2< /dev/null | grep -v git | grep -v venv | grep -v pyc | xargs file | grep CRLF`

Within the `vim` editor, you can view whitespace with `:set list` while in command mode, and any Carriage Returns will show up as the whitespace character `^M`.

### Windows

This will be editor-specifc. For Atom, install the [line-ending-selector](https://atom.io/packages/line-ending-selector) package.


## Converting line endings
### Linux / Mac OS

You can use `dos2unix` and `unix2dos` to convert files back and forth between different line endings. To do a mass convert for your entire repo, use this command: `find -X . -type f 2< /dev/null | grep -v git | grep -v venv | grep -v pyc | xargs dos2unix`

### Windows

This will be editor-specific. For Atom, install the [line-ending-converter](https://atom.io/packages/line-ending-converter) package.
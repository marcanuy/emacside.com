---
layout: post
title:  "Moving between functions within a file in Emacs"
header: "Moving between functions within a file"
description: "Showing basic browsing of the current file functions definitions."
usecase:
  - Display a list of all the functions in the current file
  - Jump to function declaration
  - Jump back to where I was
  - Browse through the function list
  - Jump directly to a function reference
  - Show which function the cursor is in
date:   2015-06-11 10:51:14
#author: marcanuy
tags: 
  - editor-textmate
  - package-imenu-mode
  - package-which-function-mode
  - package-occur-mode
editors:
    editor-textmate:
        title:       "Symbols in the current document"
        description: "For languages that support it, the rightmost pop-up in the status bar shows the current 'symbol'. 
         It is possible to click on the pop-up to get a list of all the symbols in the current document
         and move the caret to one of these. For keyboard navigation there is also 
         Navigation → Go to Symbol… (⇧⌘T)"
        url:         "https://manual.macromates.com/en/navigation_overview"
commands:
  - keys:
    function: which-function-mode
    desc:     "display the current function name in the mode line, updating it as you move around in a buffer." 
  - keys: 
    function: imenu
    desc:     "find the major definitions in a file by name"
  - keys:     C-u C-SPC
    function:
    desc:     "Move point to where the mark was, and restore the mark from the ring of former marks."
  - keys:     C-s
    function: isearch-forward
    desc:     "Incremental regular expression search, as you type characters, they add to the search string and are found"
  - keys:     C-x C-x
    function: exchange-point-and-mark
    desc:     Put the mark where point is now, and point where the mark is now.
  - keys:     M-s o
    function: occur
    desc:     Show all lines in the current buffer containing a match for a regular expression. It serves as a menu to find any of the occurrences in this buffer.
  - keys:     M-g M-n
    function: next-error
    desc:     Visit next occurence of searched string and corresponding source code.
screencasts:
  - # steps: "Several quick ways to jump to a function definition in the current file, searching through possible candidates and returning to the original position. 
    title: "Using <em>imode</em>"
    usecase:   
      - Display a list of all the functions in the current file
      - Browse through the function list
      - Jump to function declaration
    video:
      filename: "imenu-mode.mp4"
      type: mp4
      width: 740
      height: 542
    keys: |
      M-x execute-extended-command
      imenu
      RET minibuffer-complete-and-exit  *Minibuf-1*
      TAB minibuffer-complete  *Minibuf-1*
      Making completion list...
      5 * TAB minibuffer-complete  *Minibuf-1*
      *get
      TAB minibuffer-complete  *Minibuf-1*
      TAB minibuffer-complete  *Minibuf-1*
      Making completion list... [2 times]
      Conv
      TAB minibuffer-complete  *Minibuf-1*
      RET minibuffer-complete-and-exit  *Minibuf-1*

---

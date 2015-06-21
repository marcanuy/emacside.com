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
  - editor-vim
  - package-imenu-mode
  - package-which-function-mode
  - package-occur-mode
editors:
    editor-intellij:
        title:       "Structure Tool Window"
        description: "Displays the structure of a file currently opened in the editor"
        url:         "https://www.jetbrains.com/idea/help/structure-tool-window-file-structure-popup.html"
    editor-textmate:
        title:       "Symbols in the current document"
        description: |
          "For languages that support it, the rightmost pop-up in the status bar shows the current 'symbol'. 
          It is possible to click on the pop-up to get a list of all the symbols in the current document
          and move the caret to one of these. For keyboard navigation there is also 
          Navigation → Go to Symbol… (⇧⌘T)"
        url:         "https://manual.macromates.com/en/navigation_overview"
    editor-vim:
      title:       "FufBufferTag"
      description: "Searches the tags from the current active buffer :FufBufferTag"
      url:         "http://www.vim.org/scripts/script.php?script_id=1984"
commands:
  - keys:
    function: which-function-mode
    desc:     "display the current function name in the mode line, updating it as you move around in a buffer." 
  - keys:     C-u C-SPC
    function:
    desc:     "Move point to where the mark was, and restore the mark from the ring of former marks."
  - keys:     C-s
    function: isearch-forward
    desc:     "Incremental regular expression search, as you type characters, they add to the search string and are found"
  - keys:     C-x C-x
    function: exchange-point-and-mark
    desc:     Put the mark where point is now, and point where the mark is now.
screencasts:
  - 
    title: "Using imode"
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
    commands:
      - keys: 
        function: imenu
        desc:     "find the major definitions in a file by name"
  - title: "Browsing functions in a single file with occur-mode"
    usecase:
      - Search for the function keyword in a file with <code>M-x occur</code>
      - Browse through occurences in search result frame from the source code frame - <code>C-M-v</code>, <code>C-M-S-v</code>
      - Browse through functions jumping between source code with <code>M-g M-n</code>, <code>M-g M-p</code>
    video:
      filename: occur-mode.mp4
      type: mp4
      width: 740
      height: 582
    keys: |
        M-x execute-extended-command Model.php
        occur
        RET minibuffer-complete-and-exit  *Minibuf-1*
        functionSPC
        RET exit-minibuffer  *Minibuf-1*
        Searched 1 buffer; 206 matches for `function '
        You can run the command `occur' with M-s o
        Searched 1 buffer; 206 matches for `function '
        5 * C-M-v scroll-other-window Model.php
        4 * C-M-S-v scroll-other-window-down Model.php
        8 * M-g M-n next-error Model.php
        4 * M-g M-p previous-error Model.php
        C-x o other-window Model.php
        3 * C-v scroll-up-command *Occur*
        C-s isearch-forward *Occur*
        array
        2 * C-s isearch-repeat-forward *Occur*
        <return> isearch-exit *Occur*
        Mark saved where search started
        RET occur-mode-goto-occurrence *Occur*
    commands:
      - keys:     M-s o
        function: occur
        desc:     Show all lines in the current buffer containing a match for a regular expression. It serves as a menu to find any of the occurrences in this buffer.
      - keys:     M-g M-n
        function: next-error
        desc:     Visit next occurence of searched string and corresponding source code.
---

---
layout: post
title:  "Moving between functions within a file in Emacs"
header: "Moving between functions within a file"
description: "Showing basic browsing of the current file functions definitions."
date:   2015-06-11 10:51:14
#author: marcanuy
category: navigation
youtube_id: r6nKLXBst5s
tags: 
  - editor-intellij
  - editor-textmate
  - editor-vim
  - package-imenu-mode
  - package-which-function-mode
  - package-occur-mode
editors:
    intellij:
        title:       "Structure Tool Window"
        description: "Displays the structure of a file currently opened in the editor"
        url:         "https://www.jetbrains.com/idea/help/structure-tool-window-file-structure-popup.html"
    textmate:
        title:       "Symbols in the current document"
        description: "For languages that support it, the rightmost pop-up in the status bar shows the current 'symbol'. It is possible to click on the pop-up to get a list of all the symbols in the current document and move the caret to one of these. For keyboard navigation there is also  Navigation → Go to Symbol… (⇧⌘T)"
        url:         "https://manual.macromates.com/en/navigation_overview"
    vim:
      title:       "FufBufferTag"
      description: "Searches the tags from the current active buffer :FufBufferTag"
      url:         "http://www.vim.org/scripts/script.php?script_id=1984"
screencasts:
- title: "Using imode"
  usecase:
    - action: Display a list of all the functions in the current file
      keys: 
      function: imenu
      desc:     "find the major definitions in a file by name"
    - action: Browse through the function list
    - action: Jump to function declaration
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




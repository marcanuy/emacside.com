---
layout: post
title:  "Distraction-free writing in Emacs"
header: "Distraction-free writing environment"
description: "Full screen modes to minimize distractions cleaning the screen from windows, frames, status icons and other programs. Just focus in coding removing everything else from the screen."
date:   2015-06-02 10:51:14
#author: marcanuy
tags: 
  - editor-sublime-text
  - editor-writeroom
  - package-writeroom-mode
editors:
    editor-sublime-text:
        title:       "Distraction Free Mode"
        description: "Distraction Free Mode shows your files full screen, with nothing but text shown in the center of your monitor."
        url:         "http://www.sublimetext.com/docs/2/distraction_free.html"
    editor-writeroom:
        title: "WriteRoom"
        description: "Distraction free writing. WriteRoom is a full screen writing environment."
        url: "http://www.hogbaysoftware.com/products/writeroom"
commands:
  - key
screencasts:
- title: "Cleaning the screen with writeroom-mode"
  usecase: 
    - action:   Dismiss all other windows
      key:      C-x 1
      function: delete-other-windows
      desc:     Dismiss all other windows
    - action: Clean the entire screen and display just one buffer with centered text.
      key:      ""
      function: writeroom-mode
      desc:     Minor mode for distraction-free writing
  video:
    filename: "writeroom-mode.mp4"
    type: mp4
    width: 740
    height: 418
      
  keys: |
    C-x 3 split-window-right *GNU Emacs*
    C-x 2 split-window-below *GNU Emacs*
    C-x 3 split-window-right *GNU Emacs*
    3 * C-x o other-window *GNU Emacs*
    C-x 2 split-window-below *GNU Emacs*
    C-x C-f find-file *GNU Emacs*
    Development/scraper.php
    RET minibuffer-complete-and-exit  *Minibuf-1*
    C-n next-line scraper.php
    2 * / c-electric-slash scraper.php
    SPCISPCneedSPCmoreSPCspace..SPC
    C-x 1 delete-other-windows scraper.php
    C-j electric-newline-and-maybe-indent scraper.php
    2 * / c-electric-slash scraper.php
    SPCnotSPCenough
    , c-electric-semi&comma scraper.php
    SPCenteringSPCtheSPCZENSPCmodeSPC
    M-x execute-extended-command scraper.php
    writeroom-mode
    RET minibuffer-complete-and-exit  *Minibuf-1*
    Writeroom mode enabled
    C-j electric-newline-and-maybe-indent scraper.php
    2 * / c-electric-slash scraper.php
    SPCISPCcanSPCfocusSPCnow!SPC
---

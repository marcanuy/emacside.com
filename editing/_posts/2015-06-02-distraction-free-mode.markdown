---

layout: post
title:  "Distraction-free writing in Emacs"
header: "Distraction-free writing environment"
description: "When your screen gets filled with windows, frames, status icons, browsers, and you just want to focus in coding, its time to activate the <code>writeroom-mode</code> to minimize distractions. Writeroom-mode is a full screen mode that let you focus in just one buffer, removing everything else from the screen."
date:   2015-06-02 10:51:14
author: marcanuy
tags: editor-sublime-text
editors:
    editor-sublime-text:
        title:       "Distraction Free Mode"
        description: "Distraction Free Mode shows your files full screen, with nothing but text shown in the center of your monitor."
        url:         "http://www.sublimetext.com/docs/2/distraction_free.html"
    editor-writeroom:
        title: "WriteRoom"
        description: "Distraction free writing. WriteRoom is a full screen writing environment."
        url: "http://www.hogbaysoftware.com/products/writeroom"
packages:
    writer-mode:
        urls:
        - title: "https://github.com/joostkremers/writeroom-mode"
          url: "https://github.com/joostkremers/writeroom-mode"
        - title: "http://www.emacswiki.org/emacs/WriteRoom"
          url: "http://www.emacswiki.org/emacs/WriteRoom"
examples:
- title: "Showing how writeroom-mode looks"
  description: "An example to show how <code>writeroom-mode</code> clean the screen after getting the window messed up."
  video_filename: "writeroom-mode.mp4"
  video_type: "mp4"
  video_width: "800"
  video_height: "452"
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

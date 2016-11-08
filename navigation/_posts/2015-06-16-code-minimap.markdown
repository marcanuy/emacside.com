---
layout: post
title:  "Code minimap in Emacs"
header: "Embedding a code minimap"
description: "Showing a smaller display of the current buffer as a sidebar for navigating source code by dragging the active region with the mouse."
usecase:
  - Display an embedded minimap of the current source code buffer
  - Browse through the minimap
  - Close the minimap
date:   2015-06-16 14:10:11
#author: marcanuy
tags: 
  - editor-sublime-text
  - package-minimap-mode
editors:
    editor-sublime-text:
        title:       "Minimap"
        description: "The minimap feature shows a reduced overview of the entire file in the top-right corner of the screen. The portion of the file visible in the main editor pane is highlighted and clicking or dragging in this view scrolls the editor through the file."
        url:         "https://en.wikipedia.org/wiki/Sublime_Text"
screencasts:
- title: "Showing a sidebar with minimap"
  usecase:   
    - action:   Display an embedded minimap of the current source code buffer
      key:
      function: minimap-create
      desc:     Create the minimap sidebar
    - action: Browse through the minimap
    - action: Close the minimap
      keys: 
      function: minimap-kill
      desc:     "Kill minimap for current buffer"
  video:
    filename: "minimap-mode.mp4"
    type: mp4
    width: 740
    height: 645
  keys: |
      M-x execute-extended-command page.rb
      minimap
      TAB minibuffer-complete  *Minibuf-1*
      TAB minibuffer-complete  *Minibuf-1*
      Making completion list...
      create
      RET minibuffer-complete-and-exit  *Minibuf-1*
      3 * <down-mouse-1> minimap-move-overlay-mouse page.rb
      <vertical-line> <down-mouse-1> mouse-drag-vertical-line page.rb
      <left-fringe> <drag-mouse-1> nil page.rb
      <left-fringe> <drag-mouse-1> is undefined
      <vertical-line> <down-mouse-1> mouse-drag-vertical-line page.rb
      M-x execute-extended-command page.rb
      minimap
      TAB minibuffer-complete  *Minibuf-1*
      TAB minibuffer-complete  *Minibuf-1*
      Making completion list...
      kill
      RET minibuffer-complete-and-exit  *Minibuf-1*
      Minimap killed.
---

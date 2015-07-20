---
layout: post
title:  "Parens Pairs in Emacs"
header: "Insert closing pair for brackets, parens and quotes"
description: "Automatically insert auto-paired characters completion."
date:   2015-06-16 11:31:14
#author: marcanuy
tags:
  - editor-phpstorm
  - editor-textmate
  - package-smartparens
editors:
  editor-phpstorm:
    title: "Insertion of paired elements"
    description: "you can configure the editor's behavior related to the paired braces. When the option Insert pair is enabled, the closing brace is automatically added with indent on pressing Enter"
    url: "https://www.jetbrains.com/phpstorm/help/completing-punctuation.html"
  editor-textmate:
    title:       "Paired Characters"
    description: "smartTypingPairs — an array of arrays, each containing a pair of characters where when the first is typed, the second will be inserted"
    url:         "https://manual.macromates.com/en/preferences_items.html"
screencasts:
- title:        Using smartparens-mode
  usecase:
    - action:   Complete each opening bracket or quote automatically every time they are typed.
      key:
      function: smartparens-mode
      desc:     Minor mode for Emacs that deals with parens pairs and tries to be smart about it.
---

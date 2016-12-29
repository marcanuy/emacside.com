---
title: "Browsing functions in a single file with occur-mode"
description: Browsing through functions in source code in one buffer
layout: solution
youtube_id: r6nKLXBst5s
---

## Overview

When you want to glance at the overall structure of a source code
file, and are overwhelmed by the file size or the detailed code
present I find useful two things:

- **see a list of the function names** to get an idea of the naming
  conventions and an overview of the file content

- **an easy way to browse functions or procedures** having a quick
  look at their content.

If you can identify any special keyword of how functions are
defined in the programming language you are using, you can filter
them using the <kbd>occur</kbd> command.

`occur` is a standard command that find matches for a regular
expression and list them in a new buffer.
{: class="alert alert-success"}

## Using occur

We start by looking for the keyword that defines functions with the
`occur` command <kbd><kbd>M</kbd>-<kbd>s</kbd> <kbd>o</kbd></kbd> so It
prompt for a regexp and display a list in a new buffer in
**Occur-mode**.

Then we can work directly from the source code or move to the
**Occur** buffer.

### In Occur buffer

This is a special buffer where we can move around with
<kbd><kbd>M</kbd>-<kbd>n</kbd></kbd> and <kbd><kbd>M</kbd>-<kbd>p</kbd></kbd>:

**occur-next** <kbd><kbd>M</kbd>-<kbd>n</kbd></kbd>
: Move to the Nth (default 1) next match in an Occur mode buffer.
{: class="alert alert-info"}

**occur-prev** <kbd><kbd>M</kbd>-<kbd>p</kbd></kbd>
: Move to the Nth (default 1) previous match in an Occur mode buffer.
{: class="alert alert-info"}

To visit the corresponding position in the buffer <kbd>RET</kbd>:

**occur-mode-goto-occurrence** <kbd>RET</kbd>,<kbd><kbd>C</kbd>-<kbd>c</kbd> <kbd>C</kbd>-<kbd>c</kbd></kbd>
: Go to the occurrence on the current line.
{: class="alert alert-info"}

Or visit the position in the buffer but in a new window <kbd><kbd>C</kbd>-<kbd>o</kbd></kbd>:

**occur-mode-display-occurrence** <kbd><kbd>C</kbd>-<kbd>o</kbd></kbd>
: Display in another window the occurrence the current line
describes.
{: class="alert alert-info"}

We can also toggle **Next Error Follow minor** mode with
<kbd><kbd>C</kbd>-<kbd>c</kbd> <kbd>C</kbd>-<kbd>f</kbd></kbd> 
which is a feature of the **Compilation mode** "which makes cursor
motion in the compilation buffer produce automatic source display", so
in this case it will automatically update the cursor in the buffer
where we looked at the functions.

**next-error-follow-minor-mode** <kbd><kbd>C</kbd>-<kbd>c</kbd> <kbd>C</kbd>-<kbd>f</kbd></kbd>
: Minor mode for compilation, occur and diff modes.
{: class="alert alert-info"}

### From the source code buffer

From the source code window we can:

- View the occurences scrolling the other window <kbd><kbd>C</kbd>-<kbd>M</kbd>-<kbd>v</kbd></kbd>

**scroll-other-window** <kbd><kbd>C</kbd>-<kbd>M</kbd>-<kbd>v</kbd></kbd>
: Scroll next window upward ARG lines; or near full screen if no ARG.
{: class="alert alert-info"}

**scroll-other-window-down** <kbd><kbd>C</kbd>-<kbd>M</kbd>-<kbd>S</kbd>-<kbd>v</kbd></kbd>
: Scroll the "other window" down.
{: class="alert alert-info"}

- Browse through occurences from the source code window with
  <kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>n</kbd></kbd> and <kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>M</kbd>-<kbd>p</kbd></kbd>.
  This approach uses the **Compilation Mode**,  a mode that turns each
  error message in the buffer into a hyperlink, this is why they are
  named with the "error" prefix, in this case they are just *occurences*.
  
**next-error** <kbd><kbd>C</kbd>-<kbd>x</kbd> <kbd>`</kbd></kbd>,<kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>n</kbd></kbd>,<kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>M</kbd>-<kbd>n</kbd></kbd>.
: Visit next `next-error' message and corresponding source code.
{: class="alert alert-info"}

**previous-error** <kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>p</kbd></kbd>,<kbd><kbd>M</kbd>-<kbd>g</kbd> <kbd>M</kbd>-<kbd>p</kbd></kbd>
: Visit previous `next-error' message and corresponding source code.
{: class="alert alert-info"}

## Notes

`occur` is part of a set of basic editing commands for Emacs included
in `replace.el`, which already comes with Emacs, that makes it always
available and a quick solution to browse a buffer.

* Replace.el derives from **Special Mode**.

> Special mode is a basic major mode for buffers containing text that
> is produced specially by Emacs, rather than directly from a file.
> Major modes derived from Special mode are given a ‘mode-class’
> property of ‘special’.

> Special mode sets the buffer to read-only.  Its keymap defines
> several common bindings, including <kbd>q</kbd> for ‘quit-window’ and <kbd>g</kbd>
> for ‘revert-buffer’

## Summary

Using standard command from Emacs we can adapt them to browse
functions or other special keywords.

## Reference

- [GNU Emacs Manual: Other Repeating Search](https://www.gnu.org/software/emacs/manual/html_node/emacs/Other-Repeating-Search.html)
- [GNU Emacs Manual: Compilation Mode](https://www.gnu.org/software/emacs/manual/html_node/emacs/Compilation-Mode.html#Compilation-Mode)
  

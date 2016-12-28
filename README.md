# EmacSide

Exploring the IDE side of Emacs.

[![Build Status](https://travis-ci.org/marcanuy/emacside.com.svg?branch=master)](https://travis-ci.org/marcanuy/emacside.com)

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Table of Contents**

- [EmacSide](#emacside)
    - [Overview](#overview)
    - [Editing articles](#editing-articles)
        - [Adding a category](#adding-a-category)
        - [Adding a solution to an existing article](#adding-a-solution-to-an-existing-article)
- [Videos](#videos)
    - [Record screencast](#record-screencast)
        - [Open Emacs](#open-emacs)
        - [Set right emacs window size](#set-right-emacs-window-size)
        - [Big mouse cursor](#big-mouse-cursor)
            - [or directly](#or-directly)
        - [Show keystrokes](#show-keystrokes)
            - [Current Configuration](#current-configuration)
        - [Recording screen](#recording-screen)
    - [Post processing](#post-processing)
        - [Convert `ogv` to `avi`](#convert-ogv-to-avi)
        - [Cut any undesired part from the beginning or end](#cut-any-undesired-part-from-the-beginning-or-end)
    - [Titles of solutions](#titles-of-solutions)
    - [Annotate in screen during video](#annotate-in-screen-during-video)
        - [Install](#install)
        - [To draw on screen](#to-draw-on-screen)
        - [Shortcut keys](#shortcut-keys)
    - [Contribute](#contribute)

<!-- markdown-toc end -->

## Overview

Set of common developers use cases and how to solve them in Emacs.

## Editing articles

The correct way to add a keystroke combination is:

`<kbd><kbd>M</kbd>+<kbd>s</kbd> <kbd>o</kbd></kbd>` for `M+s o`.

Source: [w3 kbd element](https://www.w3.org/TR/html5/text-level-semantics.html#the-kbd-element).

For an Emacs command with its keystrokes and description we use the
Bootstrap 4 *alert* classes:

~~~
**next-error-follow-minor-mode** <kbd><kbd>C</kbd>-<kbd>c</kbd> <kbd>C</kbd>-<kbd>f</kbd></kbd>
: Minor mode for compilation, occur and diff modes.
{: class="alert alert-info"}
~~~

### Adding a category

New categories should be added to `_data/nav.yml` in the
`categories/subcategories` section, e.g. for adding the `navigation` section: 

~~~
documents:
  ...
  subcategories:
    url: /navigation
	name: Navigation
~~~

Then add to the folder `/_documents`

- a new file `/_documents/navigation.html`

~~~
---
layout: document_category
---
~~~

- a new folder `/_documents/navigation`.

### Adding a solution to an existing article

You can add your specific solution to any article

Then add also your personal information and it will be credited to you
in the article as the author owner.

1. Add yourself to the author list `_data/people.yml`.
2. Add a solution to the right folder in the `_documents` directory
   inside the folder of the same article name.

# Videos

Videos are in playlist mode in the main article and each particular
video has a special page.

## Record screencast

### Open Emacs

~~~
$ emacs --name="EmacSide.com"
~~~

More: [Emacs window size](https://www.gnu.org/software/emacs/manual/html_node/emacs/Window-Size-X.html)

### Set right emacs window size

Select the Emacs window and resize. 

Video size: 16:9 original aspect ratio (1280x720 recommended).

~~~
wmctrl -r EmacSide.com -e 0,1,1,1280,720
wmctrl -r EmacSide.com -e 0,1,1,1000,562.5
~~~

### Big mouse cursor

`sudo apt-get install dconf-tools`

~~~
$ dconf-editor
#### or directly
$ dconf write /org/gnome/desktop/interface/cursor-size 48
~~~

### Show keystrokes

Open [screenkey](https://github.com/wavexx/screenkey).

~~~
$ screenkey
~~~

Select Emacs window.

#### Current Configuration

- Time: 2
- Position:
  - Screen 0:None
  - position: bottom
- Aspect
  - Font: Sans Bold
  - Size: medium
  - Font color: 
  - Opacity: 0.7
- Keys
  - Keyboard mode: composed
  - Backspace mode: baked
  - Modifiers mode: emacs
  - NO Show Modifier sequences only
  - YES Always show Shift
  - YES Show Whitespace characters
  - YES Compress repeats after 2

### Recording screen

List windows names

~~~
$ wmctrl -l
~~~

And insert the Emacs window id like `0xFFFFFFF`.

~~~
$ recordmydesktop --output=out.ogv --windowid 0xFFFFFFF
~~~

Automatically:

~~~
$ recordmydesktop --windowid `wmctrl -l | grep "EmacSide.com" | col1
~~~

or

~~~
$ gtk-recordmydesktop
~~~

Generates `~/out.ogv` file.

## Post processing

### Convert `ogv` to `avi`

~~~
$ avconv -i writeroom-mode.ogv -b:v 1000K -q:v 1 -c:v libx264 out.avi
~~~

> If you don't specify a bitrate for the video, it will choose the
> mpeg4 video encoder for the MKV container. It uses a default of 200
> kBit/s, which is low, hence the visual artifacts.
> If you want to increase the quality, you have three options:
> Choose a higher bitrate (e.g. -b:v 1000K)
> Choose variable quality (e.g. -q:v 1). Lower means better. Good values are between 1 and 4.
> Choose a higher quality video codec, e.g. H.264 (-c:v libx264) and
> set the CRF for quality (e.g. -crf 23). Lower means better, and sane
> values are between 18 and 28.

### Cut any undesired part from the beginning or end

~~~
ffmpeg -i input.wmv -ss 00:00:30.0 -c copy -t 00:00:10.0 output.wmv
~~~

May use them while recording:

~~~
;;Highlight current line only in this buffer
;;(hl-line-mode)
~~~

## Titles of solutions

Youtube cut titles at 53 char approx. and the recommended title length
is 70. Try to keep the titles length below the 53 chars mark.

## Annotate in screen during video

### Install

`sudo apt-get install gromit gromit-mpx`

### To draw on screen

Press `Pause` button and start drawing.

Project [homepage](https://github.com/bk138/gromit-mpx).

~~~
$ gromit-mpx
~~~

## Locate mouse pointer

Show the mouse pointer with [locate-pointer](http://askubuntu.com/a/576739/43253).

Current keybinding: `Super+M`.

## Emacs Logo for videos

Generated with [jp2a](https://github.com/cslarsen/jp2a) - JPEG to ASCII image
converter.

### Shortcut keys

Pause:        toggle painting
Shift-Pause:  clear screen
CTRL-Pause:   toggle visibility

ALT-F9:    Quit Gromit-MPX.
F10:       undo last stroke
SHIFT-F10: redo last undone stroke

## Contribute

Any contribution is very welcome. 


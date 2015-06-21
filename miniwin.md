﻿#summary a lua module that contains a class for creating miniwindows
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * a lua module that contains a class for creating miniwindows

# Installation #
  * see the [Installation](Installation.md) page

# Example #
  * see any of the miniwin plugins, for example [miniwin\_example](miniwin_example.md)

# Help #
```
forthcoming

The miniwindows are populated with mushclient styles, you create a table of styles

Example:
quickest way to create a window
 mwin =  Miniwin:new{name="NewWin"}

 lstyle = {} -- the entire line

 style = {}
 style.text = "Right Horizontally (Italic)"
 style.italic = true
 style.hjust = 'right'
 style.hint = serialize.save_simple(style)
 style.mouseover = nofunc

 table.insert(lstyle, {style})
 mwin:addtab('default', lstyle, {{text="Window Header"}} )
 mwin:show(true)


The global line can have the following
  lstyle.backcolour
  lstyle.gradient (true for gradient)
  lstyle.colour1
  lstyle.colour2
  lstyle.bordercolour
  lstyle.borderwidth
  lstyle.borderstyle
  lstyle.lineborder
  lstyle.bordercolour
  lstyle.bordercolour2
  lstyle.topborder
  lstyle.bottomborder
  lstyle.leftborder then
  lstyle.rightborder then

styles can have the following
These are the main ones
  style.text = 'text' -- the only one actually required
  style.textcolour
  style.backcolour

Added for miniwin
  style.start - absolute position to start
  style.hjust - can be set to center to put text in the center of the window on that line (default is left)
    values: 'left', 'center', 'right'
  style.vjust - can be set to vertically adjust text (comes into play when a line has several sizes of text)
    values: 'top', 'center', 'bottom'
  style.font_name
    if a font can't be loaded, then the default font is used
  style.font_size
  style.bold
  style.italic
  style.underline
  style.strikeout
  style.hotspot_id

-- The following are for mouse events and are either function names of the class or actual functions in the plugin
  style.mousedown
  style.cancelmousedown
  style.mouseup
  style.mouseover
  style.cancelmouseover
  style.cursor
  style.hint

  -- next 4 use WindowLine to draw lines
  style.leftborder (true or false)
  style.rightborder (true or false)
  style.bottomborder (true or false)
  style.topborder (true or false)

  -- uses WindowRectOp to draw line around cell
  style.cellborder (true or false)

  style.bordercolour (default white)
  style.borderstyle (default 0)
  style.borderwidth (default 1)

  -- images and circleOp are not coded yet
  style.image = {}
  style.image.name
  style.image.width
  style.image.height
  style.image.mode
  style.image.srcleft
  style.image.srctop
  style.image.srcright
  style.image.srcbottom

  style.circleOp = {}
  style.circleOp.width
  style.circleOp.height
  style.circleOp.pencolour
  style.circleOp.penstyle
  style.circleOp.penwidth
  style.circleOp.brushcolour
  style.circleOp.brushstyle
  style.circleOp.extra1
  style.circleOp.extra2
  style.circleOp.extra3
  style.circleOp.extra4

```
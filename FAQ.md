
---

**Table of Contents**



---

## I accidentally closed the "X" miniwindow ##
> Let's assume the events miniwindow
  1. type "plugins miniwin" and find the plugin associated with that miniwindow
```
miniwin_double                1817  mdbl      false   true      1172      
miniwin_events                1817  mev       false   true      1278      
miniwin_help                  1817  mnhelp    false   true      1033      
miniwin_map                   1817  mmap      false   true      2562      
miniwin_moonbot               1817  mb        false   true      949       
miniwin_noexp                 1817  mnoexp    false   true      774       
miniwin_spellup               1817  mspell    false   true      8488      
miniwin_stats                 1817  mstat     false   true      2027      
miniwin_tabwin                1817  mtab      false   true      1309      
miniwin_vote                  1817  mvote     false   true      1304
```
> > the command for that plugin would be "mev"
  1. type "mev objects"
```
miniwin_events v1817 phelp Objects associated with this plugin
-----------------------------------------------
events
miniwin_events_help
```
> > the window would be "events"
  1. all miniwindows have the following commands:
    * front  - bring the miniwindow to the front
    * back   - send the miniwindow to the back
    * show   - show the miniwindow
    * hide   - hide the miniwindow
    * toggle - toggle the miniwindow (hide if shown, show if hidden)
    * reset  - reset the miniwindow
  1. type "mev events show" and "mev events front" to see the window
  1. If this doesn't work, then type "mev events reset"

## I lost miniwindow X ##

> Follow the instructions to find the appropriate object above
> We will still assume minwin\_events.

  1. "mev events reset"
  1. "mev events front"
  1. "mev events show"
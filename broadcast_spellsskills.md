### Table of Contents ###


# Introduction #
  * Author: Bast
  * this is a plugin that broadcasts spelltags and slist

# Installation #
  * see the [Installation](Installation.md) page
  * The default command for this plugin is "bsst"

# Troubleshooting #
  * run the command "bsst debug" to enable debugging

# Help #
```
/*
[FOR PLUGIN AUTHORS ONLY]

Broadcasts spelltags
Broadcasts
   1 - affon
   2 - affoff
   3 - recon
   4 - recoff
   5 - fail

Example
  function OnPluginBroadcast (msg, id, name, text)
    if id == "aaa72f3b5453567e2bba9d50" and msg == 1 then
      -- get the info
      loadstring( text )()
      stag = spelltag
    end
  end

Broadcast 1
 spelltag = {}
  spelltag.sn = 554
  spelltag.time = 990

Broadcast 2
 spelltag = {}
  spelltag.sn = 554

*/
```
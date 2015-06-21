﻿#summary Plugin to broadcast level info
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * this is a plugin that broadcasts info about  level

# Installation #
  * see the [Installation](Installation.md) page
  * The default command for this plugin is "blev"

# Troubleshooting #
  * run the command "blevel debug" to enable debugging

# Help #
```
/*
[FOR PLUGIN AUTHORS ONLY]

Broadcasts stats when leveling
Example
  function OnPluginBroadcast (msg, id, name, text)
    if id == "aaa0ab9ed92f8fc614664bd1" and msg == 2 then
      local pvar = GetPluginVariable(  "aaa0ab9ed92f8fc614664bd1", levelinfo )

      -- get the info
      loadstring( pvar )()
      info = levelinfo
    end
  end

Broadcasts
   1 - level info, get var.levelinfo and loadstring it
    levelinfo = {}
      levelinfo.starttime = 1340385935
      levelinfo.hp = "30"
      levelinfo.mv = "31"
      levelinfo.luc = 0
      levelinfo.blessingtrains = 0
      levelinfo.pracs = "10"
      levelinfo.level = "126"
      levelinfo.str = 1
      levelinfo.con = 0
      levelinfo.totallevels = 1734
      levelinfo.bonustrains = 0
      levelinfo.mp = "25"
      levelinfo.int = 0
      levelinfo.type = "level"
      levelinfo.trains = "4"
      levelinfo.wis = 1
      levelinfo.dex = 0
  2 - Created
  3 - Heroed
  4 - SuperHeroed
  5 - Preremort
  6 - Remorted to Level 1
  7 - Pre-Tiered
  8 - Tiered
*/
```
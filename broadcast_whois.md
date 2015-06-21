﻿#summary Plugin to broadcast whois info
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * this is a plugin that broadcasts whois info

# Installation #
  * see the [Installation](Installation.md) page
  * The default command for this plugin is "bwhois"

# Troubleshooting #
  * run the command "bwhois debug" to enable debugging

# Help #
```
/*
[FOR PLUGIN AUTHORS ONLY]

Broadcasts stats when leveling
Broadcasts
   1 - whois info, get var.whoisinfo and loadstring it

Example
  function OnPluginBroadcast (msg, id, name, text)
    if id == "aaaf9a8dc92f8fc614663ac0" and msg == 1 then
      local pvar = GetPluginVariable(  "aaaf9a8dc92f8fc614663ac0", whoisinfo )

      -- get the info
      loadstring( pvar )()
      info = whoisinfo
    end
  end

Broadcast 1
 whoisinfo = {}
  whoisinfo.combatmazedeaths = "0"
  whoisinfo.duelslost = "0"
  whoisinfo.totallevels = 1733
  whoisinfo.questsfailed = "141"
  whoisinfo.gquestswon = "148"
  whoisinfo.subclass = "ninja"
  whoisinfo.birthdate = "15 Jul 2003"
  whoisinfo.trainedstats = "685"
  whoisinfo.powerupsall = 0
  whoisinfo.combatmazewins = "0"
  whoisinfo.questpoints = "114997"
  whoisinfo.hoursonline = "9578"
  whoisinfo.level = 125
  whoisinfo.powerupsmort = 0
  whoisinfo.timeskilled = "178"
  whoisinfo.tiers = 1
  whoisinfo.sex = "male"
  whoisinfo.triviapoints = "183"
  whoisinfo.classes = {}
    whoisinfo.classes[1] = "thief"
    whoisinfo.classes[2] = "psionicist"
  whoisinfo.race = "shadow"
  whoisinfo.monsterskilled = "64004"
  whoisinfo.duelswon = "0"
  whoisinfo.campaignsfld = "38"
  whoisinfo.qpearned = "288254"
  whoisinfo.questscomplete = "12871"
  whoisinfo.campaignsdone = "1635"
  whoisinfo.name = "Bast"
  whoisinfo.remorts = 2
*/
```
﻿#summary Plugin to broadcast gq info
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * this is a plugin that broadcasts info about a gq
  * it is used for the [miniwin\_gq](miniwin_gq.md) plugin

# Installation #
  * see the [Installation](Installation.md) page
  * The default command for this plugin is "bgq"

# Troubleshooting #
  * run the command "bgq debug" to enable debugging

# Help #
```
/*
[FOR PLUGIN AUTHORS ONLY]

Broadcasts when anything happens in a gquest
Broadcasts
   1 - gquest available
   2 - gquest joined
   3 - Mob list, get var.mobs and loadstring it
       mobs = { 1 = {name = 'Some name', location = 'Some location', clean = 'A name with some stuff removed', num=number},
              2 = {name = 'Another name', location = 'Another location', clean = 'Another name with some stuff removed', num=number}, }
       It will be resent when a mob is killed and will be nil when a gquest is not active
   4 - rewards get var.gq_info and loadstring it
       see below
   5 - gquest over

Example
  function OnPluginBroadcast (msg, id, name, text)
    if id == "aaa77f81c5408278ccda7100" and msg == 3 then
      local pvar = GetPluginVariable(  "aaa77f81c5408278ccda7100", "mobs" )

      -- get the mobs
      loadstring( pvar )()
      gq_mobs = mobs
    end
  end

gq_info = {}
  gq_info.starttime = 1241394128
  gq_info.mobs = {}
    gq_info.mobs[1] = {}
      gq_info.mobs[1].num = "1"
      gq_info.mobs[1].location = "Castle Vlad-Shamir"
      gq_info.mobs[1].name = "demon cook"
      gq_info.mobs[1].clean = "demon cook"
    gq_info.mobs[2] = {}
      gq_info.mobs[2].num = "1"
      gq_info.mobs[2].location = "Castle Vlad-Shamir"
      gq_info.mobs[2].name = "an insane demon"
      gq_info.mobs[2].clean = "an insane demon"
    gq_info.mobs[3] = {}
      gq_info.mobs[3].num = "1"
      gq_info.mobs[3].location = "Diamond Soul Revelation"
      gq_info.mobs[3].name = "Marie Antoinette"
      gq_info.mobs[3].clean = "marie antoinette"
    gq_info.mobs[4] = {}
      gq_info.mobs[4].num = "1"
      gq_info.mobs[4].location = "Realm of Deneria"
      gq_info.mobs[4].name = "Zombie"
      gq_info.mobs[4].clean = "zombie"
    gq_info.mobs[5] = {}
      gq_info.mobs[5].num = "1"
      gq_info.mobs[5].location = "ST:TNG"
      gq_info.mobs[5].name = "a loose crystal of the entity"
      gq_info.mobs[5].clean = "a loose crystal of the entity"
    gq_info.mobs[6] = {}
      gq_info.mobs[6].num = "1"
      gq_info.mobs[6].location = "Star Wars"
      gq_info.mobs[6].name = "a transporter crewman"
      gq_info.mobs[6].clean = "a transporter crewman"
    gq_info.mobs[7] = {}
      gq_info.mobs[7].num = "1"
      gq_info.mobs[7].location = "The Flying Citadel"
      gq_info.mobs[7].name = "Blandine, archangel of dreams"
      gq_info.mobs[7].clean = "blandine archangel of dreams"
    gq_info.mobs[8] = {}
      gq_info.mobs[8].num = "1"
      gq_info.mobs[8].location = "The Goblin Fortress"
      gq_info.mobs[8].name = "Orchid the pilferer"
      gq_info.mobs[8].clean = "orchid the pilferer"
    gq_info.mobs[9] = {}
      gq_info.mobs[9].num = "1"
      gq_info.mobs[9].location = "The Imperial City of Reme"
      gq_info.mobs[9].name = "a leper"
      gq_info.mobs[9].clean = "a leper"
  gq_info.qpmobs = 0
  gq_info.won = 0
  gq_info.length = 0
  gq_info.finishtime = 1241394624
  gq_info.pracs = 0
  gq_info.gold = 0
  gq_info.tp = 0
  gq_info.level = "69"
  gq_info.trains = 0
  gq_info.qp = 0
*/
```
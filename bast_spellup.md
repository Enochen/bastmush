### Table of Contents ###


# Introduction #
  * This plugin is the command line part of my new spellup plugin
  * Most of the actions can be done from the miniwin\_spellup

# Features #
  * ability to add skills along with spells
  * disable/enable specific spellups
  * can have spellups that block other spellups from being activated
  * import/export settings
  * can keep settings through remort without having to readd spellups
  * Two options for spelling up others
    * pick spellups that you want to use on others
    * fast option which is basically the mud version of the spellup, It looks through all your spellups and casts the ones that can be cast on others and you have practiced
  * Can toggle spells/skills to be spellups clientside although they are not spellups on the mudside, For example, stealth.

# Installation #
  * See the [Installation](Installation.md) Page
  * The default command for this plugin is "bsp"
    * for help on a specific command, "`bsp <cmd> help`"

# Help #
  * the default cmd alias is bsp
  * For spells with multiple words, surround the spell with single quotes or use the sn
  * to add a spell in a certain position, add a :position to the end of the spell, Example: "bsp sadd aid:1" to add aid to the first position
  * Commands for spellups on self
```
------- self -------
slist           : list requested spells for self
sadd            : add a spell to cast on self, use 'all' to add all spellups
sremove         : remove a spell, use 'all' to clear table
senable         : enable a spell
sdisable        : disable a spell
sba             : add blockers, Ex. 'protection good:inertial barrier'
sbr             : remove blockers
fast            : cast all spells requested in one go

------- other -------
olist           : list spells to be cast on other
oadd            : add spells to cast on other
oremove         : remove spells to cast on other
oenable         : enable a spell
odisable        : disable a spell
other           : cast spells on another char, use 'fast' to cast all spellup spells, otherwise it only casts the ones added with oadd

------- Spells -------
togglespellup   : toggle a spell to be a spellup regardless of what the mud says
toggleclan      : toggle a spell/skill to be a clan skill
searg           : add an argument to be cast with a spell

------- Misc -------
export          : export current spell list as list of commands
info            : show info on a spell
check           : lists everything that needs to be checked before spellups begin
pause           : pause spellup
resume          : resume spellup
refresh         : refresh affected spells
```

# Variables #
```
Specific settings for this plugin
autoprac                       : false                - auto practice skills/spells in your spellup list
practo                         : 85                   - the percentage to practice spells to
```

# Walkthrough #
  * This is the export of my current spellups
```
# remove all self spellups
bsp sremove all

# add spellups that I have, I have even added spellups for my entire mort
bsp sadd 155 157 4 5 31 32 33 34 49 51 53 57 68 72 76 91 97 112 116 118 119 121 123 126 235 168 484 252 253 248 249 185 554 133 135 422 421 427 425 424 431 430 429 428 435 439 437 317 423 335 164 333 434 171 250 152 255 259 442 174 254 559 58

# block protection good from being cast if inertial barrier is active, Protection good is before inertial barrier in sadd to make this work
bsp sba 68:121

# disable spells I don't want to use, most of these are detects because of the Aard Helm
bsp sdisable 31 32 33 34 58

# remove all other spellups
bsp oremove all

# add the spellups I want to activate on others
bsp oadd 155 157 171 254

```
  * I also have this alias to go vis
```
<aliases>
  <alias
   match="vis"
   enabled="y"
   send_to="12"
   omit_from_output="y"
   keep_evaluating="y"
   sequence="100"
  >
  <send>Execute("bsp sd 'shadow form' hide")
DoAfter(.2, 'visible')</send>
  </alias>
</aliases>
```
  * and this one to reenable shadow form
```
<aliases>
  <alias
   match="sha"
   enabled="y"
   send_to="10"
   keep_evaluating="y"
   sequence="100"
  >
  <send>bsp sen 'shadow form' hide
</send>
  </alias>
</aliases>
```

  * Example of "bsp list"
    * P  = Pending - in the queue to be activated
    * B  = Blocked - by a recovery or another spell
    * D  = Disabled
    * NP = Not Practiced
    * NL = Not Learned
```
bast_spellup v6 Spells requested (9)
-----------------------------------------------
#. Name                        P  B  D  NP  NL
____________________________________________________
1. aid                         P
2. detect evil                       D
3. frenzy
4. giant strength
5. haste                                NP
6. night vision
7. toxic resistance                         NL
8. stealth                        B              Blocked by Recovery: stealth
9. invis                             D
```
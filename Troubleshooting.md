﻿#summary Troubleshooting plugins
#labels Featured

## General Information ##
  * the support files are required for most of the plugins to work
  * most of the plugins have debug options and can be toggled by typing "(plugincmd) debug"
  * delete the state file for the plugin and reload it
  * put a %c at the end of your prompt (and bprompt) and turn off promptflags
    * automatically fix your prompt, do "plugins load fix" then after a few seconds, "fix prompt"
  * type "tags" and make sure Global Tags is on

## Miniwindows not showing ##
  * Several Options
    1. Load miniwin\_tabbar, it will show if a window is loaded
    1. type `plugincmd> objects`, find the non help object and then type `<plugincmd> <object> show` and then `<plugincmd> <object> front`
    1. V6 and beyond: type `<plugincmd> windows` and it will show you if a window is hidden or not

## whois command over and over, or tabs not showing in miniwin\_stats ##
  * set pagesize to 0 or something > 400
  * set nopretitle to "You will no longer see pretitles."
  * "whois"
  * "statdb comp" to see if the stat db was seeded

## Getting Help ##
  * post a message in the mushclient forums (best place for help)
  * add an issue in the issue tracker on this web page
  * catch me on the mud

## My Config ##
  * If all else fails, here is my mudside setup
  * my prompt is off
  * config
```
Command      Description                                     Status    
------------ ----------------------------------------------- ------   
AUTOASSIST   Assist group members in mob combat              NO 
AUTODESC     See descriptions when using the whois command   NO 
AUTOEQ       Check for better equipment when you level.      YES
AUTOEXIT     Show exits when rooms are displayed             YES
AUTOGOLD     Automatically take gold from enemy corpses      YES
AUTOKEEP     Automatically keep items bought from shops      YES
AUTOLOOT     Automatically take equipment from enemy corpses YES
AUTOMAP      Automatically see the Aardwolf map when moving  YES
AUTONOSUM    Automatically set nosummon after each summoning NO 
AUTOPK       Assist group members in PK combat               NO 
AUTOREC      Attempt to recall if you lose link              YES
AUTOSAC      Automatically sacrifice enemy corpses           YES
AUTOSAVEMSG  See a message when your character autosaves     YES
AUTOSHARE    Automatically split gold with group members     NO 
AUTOTICK     Display a message each mud 'tick'               NO 
BATTLESPAM   See combat messages of people not grouped with  NO 
CATCHTELLS   Save all tells that are sent to you             NO 
CLANTAGS     See clan logos in who/swho                      YES
COLORPATHS   Include colors in find output                   YES
COMPACT      Remove the blank line between commands          NO 
DAILY PROMPT Notice in prompt when daily blessing available  YES
DUEL         See player vs player duels                      NO 
ECHODEATHS   Sense / Hear deaths around you                  YES
EXPRATE      Show exprate wish bonus separately              NO 
ECHOCOMMANDS See your commands echod back to you             NO 
GROUPSPAM    See combat messages of people in your group     YES
HEARFRIENDS  See tells from friends while in deaf mode       NO 
KEYLOOT      Will only loot keys from enemy corpses          YES
LEVELHINTS   Show hints when you level                       YES
MAPRUN       See the Aardwolf map when using run             NO 
MARKET NOTES Receive marketplace notes while online          YES
NOCANCEL     Allow other players to cancel your spells       NO 
NOCHALLENGE  Accept duel challenges                          NO 
NOCURSE      See curse channels, curse socials, etc          NO 
NODELIVER    Accept deliveries from various stores           YES
NOEXP        Receive experience for mob kills/skill gains    NO 
NOFOLLOW     Allow people / mobs to follow you               YES
NOFRIENDS    Allow others to friend you                      YES
NOGIVE       Allow other players to give items to you        YES
NOGRACE      PK protection / half exp after being PKed       YES
NOGROUP      Allow others to invite you into groups          YES
NOHELP       See additional help when using commands         NO 
NONIGHT      Use Night vision abilities if available         YES
NOLOOT       Allow people to loot your corpse                NO 
NOOBJLEVEL   Show level of items in inventory                YES
NOPAGE       Allow people to page (beep) you                 NO 
NOPASSDOOR   Turns passdoor wish on and off                  YES
NOPEEK       Automatically use 'peek' when looking at others YES
NOPREFIX     Show prefixes to prevent trigger abuse          YES
NOPRETITLE   See pretitles on players                        NO 
NOSPELLUPSP  See other player spellups                       YES
NOSTATUS     Display enemy health each round of combat       NO 
NOSPAM       Display parry/dodge/etc messages during combat  YES
NOSUMMON     Allow people to summon you / gate to you        YES
NOTITLES     See other player's titles in room               YES
NOWARINFO    Remove total wars/losses from your warinfo      NO 
NOWEATHER    Be informed of changes in the weather.          YES
PAGEREPEAT   Show Paging prompt after all output.            YES
PKOFF        Can attack other players.                       YES
PROMPTFLAG   Show Quiet / Afk / Noexp mode in prompt         NO 
QUIET        Quiet mode                                      NO 
QUIETSELL    See haggle/tax messages when selling to stores  YES
QUIETSPELLS  See spell chanting when others cast             YES
RAWCOLORS    See color codes in output                       NO 
RSOCIAL      Allow people to use remote socials on you       NO 
SAVETELLS    Save tells while fighting/running               NO 
SEEGRAY      Show the gray color code                        YES
SHORTFLAGS   Show mob/object flags in shortened form         YES
SKIPNEXT     Doesn't loot your next mobkill                  NO 
STATMON      Show tagged stats after every prompt            NO 
STRICTSOCIAL Require '*' prefix to use socials               NO 
TICKINFO     See additional information with autotick        YES
XTERM        Xterm 256 color support                         YES
PAGESIZE     Sets number of lines per page (0 = off)         NO
-----------------------------------------------------------------------
Your game prompt is  : [%h/%Hhp %m/%Mmn %v/%Vmv %qqt %Xtnl] > %c
Your battle prompt is: [Fighting: %h/%Hhp %m/%Mmn %v/%Vmv %Xtnl%b ]> %c
You are using the default paging prompt.
-----------------------------------------------------------------------
```
  * Info
```
Info channel    On/Off
--------------  ------
Claninfo        OFF
Classchanges    OFF
Deaths          OFF
Levels          OFF
Newbies         OFF
Notes           ON
Other           ON
Quests          ON
PKDeaths        OFF
Raiding         OFF
----------------------------
Your info channel is ON
```
  * damage
```
You are displaying damage mode 1.
```
  * tags
```
Tag Name      Description                                             Status    
------------  ------------------------------------------------------- ------   
BIGMAP        Display tags/keyword around bigmap: {BIGMAP}            YES
CHANNELS      Display tags around channels - {chan ch=name}           YES
COORDS        Display coordinates while on continents: {coords}       YES
EDITORS       Display tags when entering / leaving editors: {edit/}   NO 
EQUIP         Display tags when viewing own equipment: {equip/}       NO 
EXITS         Display tags around autoexits: {exits}                  NO 
HELPS         Display tags around help and help headers.              YES
INV           Display tags when viewing own inventory: {inventory/}   NO 
MAP           Display tags around map: <MAPSTART> <MAPEND>            YES
MAPEXITS      Adds room exits within maptags                          YES
MAPNAMES      Adds room name within maptags                           YES
QUIET         Temporarily turns all other tags on/off:                NO 
ROOMDESCS     Display tags around descs {RDESC}                       NO 
ROOMNAMES     Display tags around roomnames when moving: {rname}      NO 
SAYS          Display tags around says: {say}                         YES
SCORE         Display tags around score: {score}                      NO 
SKILLGAINS    Display tags when you gain/increase a skill/spell       YES
SPELLUPS      Display tags on spellups - multiple tags                YES
TELLS         Display tags around tells - {tell}                      YES
TELOPTS       See output when client auto sets flags.                 NO 
MAPDATA       Experimental - does nothing yet.                        NO 
ROOMCHARS     Display tags around characters in a room.               NO 
ROOMOBJS      Display tags around items in a room.                    NO 
SCAN          See tags around scan output.                            YES
REPOP         See tags around repop messages.                         NO 
Global tags option (tags on/off) is On.
```
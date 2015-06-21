﻿{{{
self.invlayout['invheader'] = ["serial", "level", "type", "worth",
> "weight", "wearable", "flags", "owner",
> "fromclan", "timer", "u1", "u2", "u3",
> "score"]
self.invlayout['container'] = ["capacity", "heaviestitem", "holding",
> "itemsinside", "totalweight", "itemburden", "itemweightpercent"]
self.invlayout['statmod'] = ['name', 'value']
self.invlayout['resistmod'] = ['name', 'value']
self.invlayout['weapon'] = ["wtype", "avedam", "inflicts", "damtype",
> > "special"]
self.invlayout['skillmod'] = ['name', 'value']
self.invlayout['spells'] = ["uses", "level", "sn1", "sn2", "sn3", "sn4",
> > "u1"]
self.invlayout['food'] = ['percent']
self.invlayout['drink'] = ["servings", "liquid", "liquidmax", "liquidleft", "thirstpercent", "hungerpercent", "u1"]
self.invlayout['furniture'] = ["hpregen", "manaregen", "u1"]
self.invlayout['eqdata'] = ["serial", "shortflags", "cname", "level",
> > "type", "unique", "wearslot", "timer"]
self.invlayout['light'] = ['duration']
self.invlayout['portal'] = ['uses']
self.invlayout['tempmod'] = ['type', 'u1', 'u2', 'statmod', 'duration']

In identify but not in invdetails:

> Material, Leads To, keywords, Found at, Affect mods, Notes (like on an ore or area reset token)

{invdetails}
{invheader}10337366|100|Armor|100000|5|torso|unique, glow, hum, magic,
> dohskill, held, burn-proof, solidified, illuminated, v3, precious
|Bast|| ||381|
|:|:|

{container}3860|100|604|77|-216|78|20
> capacity|heaviest|holding|itemsinside|totalweight|itemburden|weightpercentageofitem

{weapon}dagger|420|pierce|Pierce|vorpal
> weapontype|avedam|inflicts|damtype|specials

{furniture}250|250|1
> hp|mana|unknown

potions, wands, scrolls, pills
{spells}1|60|54|54|54|54|0
> uses|level|spell|spell|spell|spell|unknown

replenishes hunger
{food}100

drink
{drink}31|root beer|1000|620|27|30|0
> servings|liquid|liquidmax|liquidcurrent|replenishesthirst|replenisheshunger|unknown

{statmod}Luck|2
> stat|mod
{skillmod}201|2
> sn|mod

{resistmod}Acid|100
{resistmod}All physical|25
> resist|mod
{/invdetails}

{tempmod}
{tempmod}581,9,14,5,24088
{tempmod}216,7,6,1,17556
{tempmod}216,9,14,6,17556
{tempmod}581,1,10,3,448125
{tempmod}581,1,11,3,448125
{tempmod}581,1,3,5,448125
{tempmod}581,1,2,3,448125
{tempmod}581,1,3,3,448125

[skill/spell number, u1, u2, statmod, duration]

if u1 = 7 and u2 = 6 then add poison flag
if u1 = 9 and u2 = 14 then add average damage modified by statmod
if u1 = 1, then add a stat value of statmod
> u2 = 1, str
> u2 = 2, int
> u2 = 3, wis
> u2 = 4, dex
> u2 = 5, con
> u2 = 6, luck
> u2 = 10, hit roll
> u2 = 11, dam roll
> u2 = 12, saves

sn 581 = temper
sn 216 = envenom
}}}```
### Table of Contents ###


# Introduction #
  * This plugin looks up items in the eq database

# Installation #
  * See the [Installation](Installation.md) Page
  * The command for this plugin is "eqlu"

# Troubleshooting #
  * The argument to the lookup command must be a valid sql statement

# Examples #
  * `eqlu level between 151 and 161`
    * will get all eq between level 151 and level 161
  * `eqlu containerid = 'Worn'`
    * will get all worn eq
  * `eqlu containerid = 'Inventory' and type = 11`
    * will show all containers in Inventory
    * find the type # with `eqlu translate object`
  * `eqlu wearloc = 0`
    * find what is worn as a light
    * find the wear # with `eqlu translate wear`
  * `eqlu name like '%breastplate%'`
    * find all items with breastplate in their name

# Sample output #
  * for `eqlu name like '%breastplate%'`
  * click on the serial number to get the details if they are available
```
Serial          Container       Level Score Name
---------------------------------------------------------------
6285179         Inventory       1     192   Aardwolf Breastplate of magic resistance
10337366        Worn            100   392   Aardwolf Breastplate of magic resistance
```
> ![http://bastmush.googlecode.com/svn/wiki/images/eqlookup/eqlookup.png](http://bastmush.googlecode.com/svn/wiki/images/eqlookup/eqlookup.png)

# Help #
```
close           : close the db
getitem         : print info on item with id
lu              : lookup stuff in the db
translate       : show what strings mean for certain types of flags
```
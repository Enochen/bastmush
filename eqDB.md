### Table of Contents ###


# Introduction #
  * This plugins saves inventory into a sqlite database
  * Also see [miniwin\_eq](miniwin_eq.md)

# Installation #
  * See the [Installation](Installation.md) Page
  * The command for this plugin is "eqdb"
    * for help on a specific command, "`eqdb <cmd> help`"
    * there is an alias for eqlu that will pass the arguments to "`eqdb lu`"

# Extras in the plugin #
  * add an identifier to an item
    * "`eqdb addid <serial> <identifer>`"
    * "`get 49495858`" will get the item from whatever container it is in
    * for the following mud commands: get, put, remove, wear, ident
      * will substitute identifiers for item serial #s
  * "`lget/lput <serialorident> <level1> <level2(opt)>`" - get/put items between level1 and level2 from/into a container

# Restoring a previous backup #
  * backups are located in the `<MUSHclient>\logs\db_backups` directory
  * the eq database is `eq.db.<extension>`
  * close MUSHclient and copy one of the backups into the logs directory and replace eq.db
  * reopen MUSHclient and then an `eqdb refresh`

# Troubleshooting #
  * To reset all eq
    * "`eqdb refresh`" then "`eqdb clean`"
    * or delete the eqdb.db file in the logs directory and reload the plugin

# Overriding the inventory and equipment commands #
  * variables
```
groupitems                     : true                 - groupitems that are the same when inventory is overloaded
overloadinventory              : true                 - overload the inventory, equipment and 'look in' commands
```
  * help, by typing "`inv help`"
```
when you override the inventory command (also works with l i <container> and eq)
inv can have several arguments
 : a single level (inv 100) - will show any items level 100 or above
 : two levels (inv 1 100) - will show any items from level 1 to level 100
 : "-g" - don't group items
 : "+g" - group items (this is default)
 : "-f" - don't show flags
 : "+f" - show flags (this is default)
 : "+se" - show serial #s (default for inventory command)
 : "+sc" - show score
 : an item type: such as weapon, armor, container, food, etc see 
       "eqdb translate objecttypes"
 : a word: the items shortname will contain this word
 : a sort field: +level, -level will sort by level
 
If you override the inventory commands on the mud, you can type the full
command to bypass eqdb

If you think your inventory does not reflect your actual inventory,
then type "eqdb refresh"
```

  * screenshots
    * ![http://bastmush.googlecode.com/svn/wiki/images/eqdb/inventory.png](http://bastmush.googlecode.com/svn/wiki/images/eqdb/inventory.png)
    * ![http://bastmush.googlecode.com/svn/wiki/images/eqdb/eq.png](http://bastmush.googlecode.com/svn/wiki/images/eqdb/eq.png)

# Examples #
  * This is how I do portals
    * "`eqdb addid <bagserial> portbag`"
    * Then to use a portal I can get it with: "`get share portbag`"
    * Also "`get <serial#forshare>`" would work
  * Looking up and sorting equipment
    * use the command eqlu
      * sorting all equipment by level
        * "`eqlu level between 1 and 50 ORDER BY level asc`"
          * asc means ascending, so the order shown will start with 1 and go to 50 (desc is the opposite of asc)
      * sorting eq in a specific bag
        * "`eqlu level between 1 and 50 and containerid = 549229115 ORDER BY level asc`"
          * containerid can be 'Worn' for worn items, 'Inventory' for items in Inventory, or a serial number of a container that you have


# Help #
```
------- Obtaining information on items -------
lu              : lookup stuff in the db
getitem         : print info on item with id
comp            : compare items,args = list of serials
getcolourname   : return the name of the item with embedded color codes

------- Manipulating identifiers on items -------
addid           : add an identifier to an item
remid           : remove an identifier from an item
listid          : list items with identifiers

------- Manipulating notes on items -------
addnote         : add a note to an item, first arg is serial, the rest will be the note
remnote         : remove a note from an item, only arg is note number
listnote        : list notes for an item, only arg is item serial

------- Manipulating items -------
lget            : get items from container between level1 and level2
lput            : put items in container between level1 and level2

------- Database commands -------
clean           : clean the db of stale items
idinv           : identify all items in inventory (does not include Worn or items in bags)
refresh         : refresh the db
close           : close the db

------- Misc -------
translate       : show what strings mean for certain types of flags
```

# Variables #
```
Specific settings for this plugin
showoutput                     : false                - show tags
overloadid                     : true                 - overload the identify command to use getitem
```
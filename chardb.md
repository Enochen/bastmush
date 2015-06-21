﻿#summary module that will interface a sqlite db to put stats in
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * This will save information into a sqlite database
    * Stats
    * skills
    * cps
    * quests
    * gqs

# Installation #
  * See the [Installation](Installation.md) Page
  * default location of database is in the logs directory, this can be changed by creating a variable in the Aardwolf world called dblocation with a path to the directory you would like to store it
  * Note: this does not differentiate between characters, change the dblocation variable for each character

# SQL spec #
```
CREATE TABLE campaigns (
      cp_id INTEGER PRIMARY KEY,
      starttime INT,
      finishtime INT,
      qp INT,
      gold INT,
      tp INT,
      trains INT,
      pracs INT,
      level INT,
      failed INT
     );
CREATE TABLE classes(
      class TEXT NOT NULL PRIMARY KEY,
      remort INTEGER
     );
CREATE TABLE cpmobs(
      cpmob_id INTEGER NOT NULL PRIMARY KEY autoincrement,
      cp_id INT NOT NULL,
      mobname TEXT,
      mobarea TEXT
     );
CREATE TABLE gqmobs(
      gqmob_id INTEGER NOT NULL PRIMARY KEY autoincrement,
      gq_id INT NOT NULL,
      num INT,
      mobname TEXT,
      mobarea TEXT
     );
CREATE TABLE gquests (
      gq_id INTEGER PRIMARY KEY,
      starttime INT,
      finishtime INT,
      qp INT,
      qpmobs INT,
      gold INT,
      tp INT,
      trains INT,
      pracs INT,
      level INT,
      won INT
     );
CREATE TABLE levels (
      level_id INTEGER PRIMARY KEY,
      type TEXT,
      level INT,
      str INT,
      int INT,
      wis INT,
      dex INT,
      con INT,
      luc INT,
      starttime INT,
      finishtime INT,
      hp INT,
      mp INT,
      mv INT,
      pracs INT,
      trains INT,
      bonustrains INT,
      blessingtrains INT DEFAULT 0
     );
CREATE TABLE mobkills(
      mk_id INTEGER NOT NULL PRIMARY KEY autoincrement,
      name TEXT,
      xp INT default 0,
      bonusxp INT default 0,
      blessingxp INT default 0,
      totalxp INT default 0,
      gold INT default 0,
      tp INT default 0,
      time INT default -1,
      vorpal INT default 0,
      banishment INT default 0,
      assassinate INT default 0,
      slit INT default 0,
      disintegrate INT default 0,
      deathblow INT default 0,
      wielded_weapon TEXT default '',
      second_weapon TEXT default '',
      room_id INT default 0,
      level INT default -1
     );
CREATE TABLE quests(
      quest_id INTEGER NOT NULL PRIMARY KEY autoincrement,
      starttime INT default 0,
      finishtime INT default 0,
      mobname TEXT,
      mobarea TEXT,
      mobroom TEXT,
      qp INT default 0,
      double INT default 0,
      daily INT default 0,
      totqp INT default 0,
      gold INT default 0,
      tier INT default 0,
      mccp INT default 0,
      lucky INT default 0,
      tp INT default 0,
      trains INT default 0,
      pracs INT default 0,
      level INT default -1,
      failed INT default 0
     );
CREATE TABLE recoveries(
      sn INTEGER NOT NULL PRIMARY KEY,
      name TEXT
     );
CREATE TABLE skills (
      sn INTEGER PRIMARY KEY NOT NULL,
      name TEXT,
      percent INT DEFAULT 0,
      target INT DEFAULT 0,
      type INT DEFAULT 0,
      recovery INT DEFAULT -1,
      spellup INT DEFAULT 0,
      clientspellup INT DEFAULT 0,
      clanskill INT DEFAULT 0,
      mag INT DEFAULT -1,
      thi INT DEFAULT -1,
      war INT DEFAULT -1,
      cle INT DEFAULT -1,
      psi INT DEFAULT -1,
      ran INT DEFAULT -1,
      pal INT DEFAULT -1
     );
CREATE TABLE stats (
      stat_id INTEGER PRIMARY KEY,
      name TEXT,
      level INT,
      totallevels INT,
      remorts INT,
      tiers INT,
      race TEXT,
      sex TEXT,
      subclass TEXT,
      qpearned INT,
      questscomplete INT,
      questsfailed INT,
      campaignsdone INT,
      campaignsfld INT,
      gquestswon INT,
      duelswon INT,
      duelslost INT,
      timeskilled INT,
      monsterskilled INT,
      combatmazewins INT,
      combatmazedeaths INT,
      powerupsall INT,
      totaltrivia INT,
      time INT,
      milestone TEXT
     );
CREATE TABLE version(
      version_id INTEGER NOT NULL PRIMARY KEY autoincrement,
      version INT default 1
     );
```

# Help #
  * see the [StatDB](StatDB.md) plugin
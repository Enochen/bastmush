﻿#summary a module for various table functions
#labels Author-Bast

### Table of Contents ###


# Introduction #
  * Author: Bast
  * a plugin for table functions

# Installation #
  * See the [Installation](Installation.md) Page

# Help #
```
/*
functions in this module

tableSort
     sort the table by the keys or an internal key to each table, will sort string or integer keys

  > test = {}
  > test['a'] = {}
  > test['b'] = {}
  > test['b']['sortlev'] = 40

  Example 1
  > for i,v in tableSort(test) do
     print(i)
    end

  returns
   a
   b

  Example 2
  > for i,v in tableSort(test, 'sortlev', 50) do
     print(i)
    end

  returns
   b
   a

tableExtend
    extend a table by adding another table

*/
```
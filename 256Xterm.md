# Introduction #
  * an alias to see all the xterm colors
  * **This alias is now included in [r443](https://code.google.com/p/bastmush/source/detail?r=443) of the Aardwolf MUSHclient, the colors are not correct otherwise**


# Details #
  * Copy the script from the page, then go to Game->Configure->Aliases and hit the "Paste" button
  * "`showxterm`" will show the colors with the numbers
  * "`showxterm no`" will show the colors without the numbers

```
<aliases>
  <alias
   match="^showxterm(.*?)$"
   enabled="y"
   regexp="y"
   send_to="12"
   sequence="100"
  >
  <send>local nonum = "%1"
dofile(GetInfo (60) .. "aardwolf_colors.lua")

for i=0,255 do
  local text = string.format('@x%-d    @w', i)
  if nonum ~= "" then
    text = string.format('@x%-d  @w', i)
  else
    ColourTell("", "", string.format('%-3s : ', tostring(i)))
  end
  local newstyles = ColoursToStyles(text)
  for i,v in ipairs(newstyles) do
    ColourTell("", RGBColourToName(v.textcolour), v.text)
  end
  if nonum == "" then
    ColourTell("", "", " ")
  end
  if i &lt; 16 then
    if i == 7 or i == 15 then
      ColourNote("", "", "")
    end
    if i == 15 then
      ColourNote("", "", "")
    end
  else
    if math.fmod(i - 21, 6) == 0 then
      ColourNote("", "", "")
    end
    if math.fmod(i- 21 + 6, 36) == 0 then
      ColourNote("", "", "")
    end
  end
end
ColourNote("", "", "")</send>
  </alias>
</aliases>
```

# Images #
![http://bastmush.googlecode.com/svn/wiki/images/xterm/xtermnum.png](http://bastmush.googlecode.com/svn/wiki/images/xterm/xtermnum.png)

![http://bastmush.googlecode.com/svn/wiki/images/xterm/xtermnonum.png](http://bastmush.googlecode.com/svn/wiki/images/xterm/xtermnonum.png)
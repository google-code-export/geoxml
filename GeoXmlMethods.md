# Methods on GeoXml #

**parse();**
//loads data sources associated with the GeoXml on to the map.

**parseString(datastring);**
//allows parsing from a dynamically created string instead of loading a url.

**hide();**
//hides all content and toggles any side bar entries to match

**show();**
//shows all content and toggles any side bar entries to match

**clear();**
//removes all content and empties sidebar area associated with this instance of GeoXml.
//to reuse after change the contents of the urls array, then call parse.

//to add another datasource
```
clear();
geoxmlvar.urls.push("newdatasource");
geoxmlvar.parse();
```
//to use completely new data sources
```
clear();
geoxmlvar.urls = ["newdatasource","anotherdatasource"];
geoxmlvar.parse();
```
//to just update the same source
```
clear();
geoxmlvar.parse();
```

new parameter makedescription:true <- useful for georss feeds.

new parameter iwheight:250 <--- specify height of information block before the window gets scroll bars.
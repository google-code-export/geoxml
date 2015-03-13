#This is a page for recording the various options for GeoXml
# Introduction #
GeoXml though has many options which correspond to those in [EGeoXml](http://econym.org.uk/gmap/egeoxml.htm), we can record divergence here.

---

Url parsing  is built in to GeoXml
http://www.dyasdesigns.com/geoxml/c2020.htm?openbyname=Babcock%20Ranch
The above opens the placemark associated with the name

Like above also supported openbyid  // uses xml id

Like above the following are all equivalent and load an external src (but only within domain restrictions).
> kml=pathofkml, src=pathofsrc, url=pathof source


---

```
 markerfollowlinks: true 
```
the above specifies to open links in a new window or tab
Where links are defined in the xml source (generally in RSS) and formatted thusly.
```
<link>http://www.somedomain.com</link>
<href>http://www.somedomain.com</href>
or 
<link href="http://www.somedomain.com"></link>
```


---


```
 alwaysinfopop: true 
```
the above results in informational windows opening even when a element is clicked programmatically or from a sidebar click.
```
 zoomhere: 12 
```
the above results in informational bwindows with directions using a Zoom level of 12 when you click on Zoom Here
```
 iwheight: 100 
```
the above results in informational windows with height of 100px (note you may get scroll bars if your content doesnt fit. )
```
clickablepolys : false
clickablelines : false
clickablemarkers : false
```
To turn off clicking of elements
```
preloadHTML :false
```
To turn off preloading info window html
```
pointlabelclass: "mymarkerlabelclassname" 
```
A string containing the name of the CSS class to be used for ELabels on markers.
```
polylabelclass: "mymarkerlabelclassname" 
```
A string containing the name of the CSS class to be used for ELabels on polygons.
```
iconFromDescription:true
```
enables the option which allows things like rss feeds and gml to find the image source in the atom/elements descriptions ala [yahoo\_weather](http://www.dyasdesigns.com/geoxml/myweather.htm)

```
maxiwwidth : number 
```
puts an absolute max on computed width for the info window.

```
sidebariconheight:32
```
sets sidebar icon height to something other than default 16
```
sidebarsnippet:true
```
use snippets (or first 20 characters from description) as a side bar entry
example using both the above (note css to control snippet not really optional)
http://www.dyasdesigns.com/geoxml/customsidebar.htm

```
allfoldersopen:true
```
controls the side bar folders to show all there contents independent of  open and closed settings in the kml.

```
hilite : { color:"#aaffff",opacity: 0.3, textcolor:"#000000" }
```

Sets opacity and color settings for sidebar and polygon fill elements
.http://www.dyasdesigns.com/geoxml/c2020.htm
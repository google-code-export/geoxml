GeoXml is a term coined by google themselves referring to Geospatial XML formats and the Google Maps API has its own tool for handling it. This project is a third party parser which can take its place and opens up the features to include more GeoXml formats and better OGC support... ie not just KML it also parses GML(such as produced by a WFS) and GeoRSS and GPX, its benefits include creation of collapsible tree based layer control (generally vertical in a sidebar).  It can also save out to its own kjson format (requires json.js or a browser with built in json toJSONString support). This parser in some cases actually handles kml created by Google Earth better than the API's GGeoXml. When a WMS base ground overlay is parsed in a kml it is auto-tiled as a GTileOverlay or GTileMapType making them first class citizens.

I have posted this to better enable others to help contribute and fix bugs and track versioning and bug fixes.. ok the latter might be the biggest reason, anyway I have decided to publish this in a more visible public fashion.

I am mirroring the compressed version of the code on the downloads  page If you would like to look at the source in a more readable fashion check it out via svn (see the source tab).

Version 3 is starting to come along and includes new features like label support
https://code.google.com/p/geoxml-v3/

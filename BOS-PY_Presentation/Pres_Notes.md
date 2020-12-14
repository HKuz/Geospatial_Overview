# On Python and Positioning: An Introduction to Working with Geospatial Data in Python with GeoPandas

[x] INTRO

- Hi, I'm Heather Kusmierz and I'm joining from New Hampshire, if you couldn't tell from the flannel
- I'm a relatively new join to this group, but Ned asked very nicely the other month if I'd present
- One goal I had this year was to learn more about geospatial data - I've always been interested in maps, and a lot of my hobbies and iterests happen to take me outdoors a lot, so there was some good overlap here
- I figured this was a great oppourtunity to consolidate what I've learned to share it with all of you
- I'm very much still getting up this learning curve, but hopefully tonight what I cover greases the skids a bit to get you started
- For anyone out there who's a clipart enthusiast, tonight is your night - perhaps next year's foray will be learning about graphic design...

[x] ROADMAP
- Here's an overview of what we're covering tonight
- First I'll introduce the datasets I used, this will give you all an example to keep in mind when we start going through theory
- Next we'll zoom out and get a big picture overview of all the different entities and how they fit together within the geospatial ecosystem
- Then we'll cover some basic theory - the two major ways this data is packaged, common file formats, and a very high-level overview of coordinate reference systems and projections which can be a point of confusion when you first start out and a source of error if you're combining datasets.
- Then we'll zoom in and talk about the various Python packages available, speficially I'm using GeoPandas for the code demo.
- Finally, we'll flip over to a Jupyter notebook to walk through how to import data, create a GeoDataFrame, and map the data. The notebook itself has way more examples of common applications than we can cover tonight, but I included them so you can use as a reference as needed.
- In 20 minutes we probably won't hit this Geospatial Enlightenment, but as I mentioned, the goal tonight is to give you enough information to get started

[ ] DATASETS
- You may have wondered why the last slide resembled a treasure map, the datasets we're using tonight are shipwrecks and divesites off the coast of Massachusetts. I didn't research all the ships in the sets, but there's potentially a pirate ship in there.
- Fun fact: there's a fifty-mile stretch of sea along Cape Cod's coastline that has these shifting, underwater ridges known as shoals, that make navigating it very difficult (especially before the time of sonar and radar), so this stretch has claimed over 3000 vessels. Because of this, it's not-so-affectionately known as the "ocean's graveyard".
- I pulled the shipwreck data off a Wikipedia page that listed a whole bunch of wrecks, but only a small subset of about 50 ships actually had coordinate info as well.
- The other dataset comes from a call to an API to get dive sites within 50 nautical miles of Boston. And that returned JSON with 34 dive sites in it.
- Both sets include the name of the ship or site, then the latitude/longitude coordinates for where they're located.


[ ] GEOSPATIAL ECOSYSTEM / GIS
- Let's zoom out and look at the big picture of what makes up what I've been calling the geospatial ecosystem
- The  technical term is "Geographic Information System", or GIS, and there's a textbook definition here in the subtitle. If you can't read that, it says "A GIS is a computer-based system to aid in the collection, maintenance, storage, analysis, output, and distribution of spatial data and information – this can include hardware, software, data, people, and industry protocols".
- While technically everything on this slide and then some falls under this umbrella term "GIS", usually when someone uses it in conversation, they're referring to software.
- There are a handful of acronyms on this page that I wanted to highlight since they come up a lot when you're searching for information. First is the OGC, or the "Open Geospatial Consortium". They're responsible for establishing the standards that specify file formats, how data is encoded, and how interfaces work, among other things. Basically, they set the rules so things work together, so all the entities here can play together nicely in the same sandbox.
- The software on the right comes in a few different flavors. That first bullet shows two examples of desktop applications with a GUI. QGIS is open source and commercial desktop application software, respectively: QGIS is  and ArcGIS. There are a lot of other choices here too.
-

[x] DATA MODELS
- There are two major ways of packaging data with spatial information, which are vector and raster formats
- So you may be wondering why there are three boxes on the slide - data attributes will always be packaged within vector or raster formats, but you may want to collect additional information that's tied to the same area to combine with the vector or raster data
- Vector formats are a good way to package discrete geometries - this would be a set of points representing shipwrecks (like what we're working with tonight), or it could be lines representing a trail system or railroad network, or polygons to capture areas, like the borders of countries. Multi-polygons are good for when you need several polygons to describe one thing, like the border of Japan where it's made up of a lot of separate islands.
- Raster formats are good for packaging information that's continuous over an area - things like rainfall, elevation, or surface temperatures. It uses a grid that embeds the coordinate system, and each box in the grid is tied to the relevant information.
- These formats are not exclusive - you can convert one into the other if you need to, but usually one is a better fit for the data.
- Some example file formats are on the right side here - this is a subset of all the different formats out there. If you see a shapefile or GeoJSON, you'll know you're working with vector data, whereas a GeoTIFF will be raster data. Some formats like a geopackage can hold either, and data attributes can come in any tabular format.

[ ] COORDINATE REFERENCE SYSTEMS (CRS)
- Alright, next up is coordinate reference systems - this is a theory piece that can be a point of confusion when you first start out working with geospatial data.
- Coordinate reference systems create a framework that ties real world places on the surface of the Earth to coordinates in a consistent manner. So this system puts the origin at the center of the Earth with X, Y, and Z axes shooting out from there, then assigns places around the World like the Eiffel Tower or the summit of Mount Everest a latitude, longitude, and elevation that fit within this system.
- One would think we have one system for this (as I naively thought at first), but unfortunately, this is not the case. There are many coordinate reference systems out there.
- This is because of a few factors, but namely to establish a coordinate reference system, you need estimates of certain geographic measurements of the Earth itself as well as some assumptions. The set of these measurements and assumptions taken together is called a "Datum".
- And I'm talking 'large scale' estimates. For example, the distance from the center of the Earth to the equator, or from the center of the Earth to either the North or South pole (these are different since the Earth is a mushed sphere vs a perfect) - these are items that make up part of a datum. We can't measure them directly, but as technology has improved, we've been able to refine the estimates used in datums, therefore they've changed over time.
- Couple that with the fact the Earth itself is changing with tectonic plate movements, and you can see how there are different versions of coordinate reference systems out there.
-
- WSG84:

[ ] PROJECTIONS
- Projections are used for mapping and visualization - it's a mathematical translation that converts 3D coordinates into a 2D representation
- Think of unrolling the surface of the earth then flattening it down - that's a crude description of what a projection does.
- All projections add some element of distortion
- It's a tradeoff -> preserve some aspect of your data (distances, areas, nautical angles) at the expense of something else
- Show projections
- One point of confusion is that sometimes "CRS" and "projection" are used as synonyms - they are different

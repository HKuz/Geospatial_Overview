# On Python and Positioning: An Introduction to Working with Geospatial Data in Python with GeoPandas

INTRO

- Hi, I'm Heather Kusmierz and I'm joining from New Hampshire, if you couldn't tell from the flannel
- I'm a relatively new join to this group, but Ned asked very nicely the other month if I'd present
- One goal I had this year was to learn more about geospatial data - I've always been interested in maps, and a lot of my hobbies and iterests happen to take me outdoors a lot, so there was some good overlap here
- I figured this was a great oppourtunity to consolidate what I've learned to share it with all of you
- I'm very much still getting up this learning curve, but hopefully tonight what I cover greases the skids a bit to get you started
- For anyone out there who's a clipart enthusiast, tonight is your night - perhaps next year's foray will be learning about graphic design...

ROADMAP
- Here's an overview of what we're covering tonight
- First I'll introduce the datasets I used, this will give you all an example to keep in mind when we start going through theory
- Next we'll zoom out and get a big picture overview of all the different entities and how they fit together within the geospatial ecosystem
- Then we'll cover some basic theory - the two major ways this data is packaged, common file formats, and a very high-level overview of coordinate reference systems and projections which can be a point of confusion when you first start out and a source of error if you're combining datasets.
- Then we'll zoom in and talk about the various Python packages available, speficially GeoPandas which is the one I'm using in the code demo
- Finally, we'll dive into the code demo to walk through some basic

DATASETS

GEOSPATIAL ECOSYSTEM / GIS
-

DATA MODELS
- Two major ways of packaging information and coordinates / location together are vector and raster formats
- Data attributes can be an additional table that  usually combined with
- Can convert one into the other

PROJECTIONS
- Projections are used for mapping and visualization - it's a mathematical translation that converts 3D coordinates into a 2D representation
- Think of unrolling the surface of the earth then flattening the surface
- All projections add some distortion
- It's a tradeoff -> preserve some aspect of your data (distances, areas, nautical angles) at the expense of something else
- Show projections
- One point of confusion is that sometimes "CRS" and "projection" are used as synonyms - they are different

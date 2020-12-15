# Overview of Working with Geospatial Data in Python

This repository holds the code and slides for the presentation for the Boston Python group titled *On Python and Positioning: An Introduction to Working with Geospatial Data in Python with GeoPandas*. It was presented on December 16, 2020.

## Dataset Sources

The presentation used a combination of dive site and shipwreck data garnered off the web. The Massachusetts wrecks are courtesy of [Wikipedia](https://en.wikipedia.org/wiki/List_of_shipwrecks_of_Massachusetts), and the diving info is the result of a call to the [Divesites.com API](http://api.divesites.com/docs/) for sites within 50 nautical miles of Boston, MA.

Fun fact (also from Wikipedia): there's a fifty-mile stretch of sea along Cape Cod's coastline from Chatham to Provincetown that contains thousands of shipwrecks. The dangerously hidden and constantly moving shoals (a natural submerged ridge, bank, or bar of unconsolidated material) located just off-shore have claimed over 3,000 vessels, earning it the moniker of the "ocean graveyard".



## Running the Notebook Locally

If you've cloned this repository and want to run the code locally, you'll need to make sure you have the necessary Python packages installed on your machine.

The Jupyter Notebook runs off an Anaconda environment that contains all of these packages. To re-create the `geo` environment, first make sure you have either an [Anaconda or miniconda distribution](https://www.anaconda.com/) installed, then run the following command:

```bash
conda env create -f environment_geo.yml
```

You can also use a Python 3 pip environment, and `pip install` the following packages: `geopandas`, `geopy`, `folium`, and `contextily`. Also make sure your environment can run a Jupyter notebook.

Once your local environment is ready, activate it (`conda activate geo`) and run the `jupyter notebook` command to access the `geospatial_code_demo.ipynb` file.


<!--
https://www.w3.org/2015/spatial/wiki/Coordinate_Reference_Systems
WGS84, a CRS for latitude-longitude coordinates, is very popular on the web. This has lead to the idea that this CRS can be considered a default CRS. In fact, many specifications have done so (basic geo, GeoJSON, geosparql).

www.thetruesize.com for interactive map showing Mercator projection distortions - as you drag a country around it adjusts to it's accurate relative size.

Gist with KML reading and dropping Z dimension info:
https://gist.github.com/mazzma12/0a32ce693bb42b742252caabb98519db

13 Top open source GIS software: https://gisgeography.com/free-gis-software/

More than you ever wanted to know about GeoJSON:
https://macwright.com/2015/03/23/geojson-second-bite.html

-->

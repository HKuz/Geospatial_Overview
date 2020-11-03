# Overview of Working with Geospatial Data in Python

This repository holds the code and slides behind a short (15 minute) presentation for the Boston Python and Women Who Code groups in November 2020.

## Running the Notebook Locally

If you've cloned this repository and want to run the code locally, you'll need to make sure you have the necessary Python packages installed on your machine.

The Jupyter Notebook runs off an Anaconda environment that contains all of these packages. To re-create the `geo` environment, first make sure you have either an [Anaconda or miniconda distribution](https://www.anaconda.com/) installed, then run the following command:

```bash
conda env create -f environment_geo.yml
```

You can also use a Python 3 pip environment, and `pip install` the following packages: `geopandas`, `geopy`, and `folium`.

Once your local environment is ready, activate it (`conda activate geo`) and run the `jupyter notebook` command.

## Dataset Sources

The presentation used a combination of dive site and shipwreck data garnered off the web. The Massachusetts wrecks are courtesy of [Wikipedia](https://en.wikipedia.org/wiki/List_of_shipwrecks_of_Massachusetts), and the diving info is from the [Divesites.com API](http://api.divesites.com/docs/).

Fun fact (also from Wikipedia): there's a fifty-mile stretch of sea along Cape Cod's coastline from Chatham to Provincetown that contains thousands of shipwrecks. The dangerously hidden and constantly moving shoals located just off-shore have claimed over 3,000 vessels, earning it the moniker of the "ocean graveyard".

<!--
https://www.w3.org/2015/spatial/wiki/Coordinate_Reference_Systems
WGS84, a CRS for latitude-longitude coordinates, is very popular on the web. This has lead to the idea that this CRS can be considered a default CRS. In fact, many specifications have done so (basic geo, GeoJSON, geosparql).
-->

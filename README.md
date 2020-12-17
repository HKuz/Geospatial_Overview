# Overview of Working with Geospatial Data in Python

This repository holds the code and slides titled *On Python and Positioning: An Introduction to Working with Geospatial Data in Python with GeoPandas* that were presented to the Boston Python group on December 16, 2020.

The presentation slides are located in the `BOS-PY-Presentation` subfolder.

## Dataset Sources

The presentation used a combination of dive site and shipwreck data garnered off the web. The Massachusetts wrecks are courtesy of [Wikipedia](https://en.wikipedia.org/wiki/List_of_shipwrecks_of_Massachusetts), and the diving info is the result of a call to the [Divesites.com API](http://api.divesites.com/docs/) for sites within 50 nautical miles of Boston, MA.

Fun fact (also from Wikipedia): there's a fifty-mile stretch of sea along Cape Cod's coastline from Chatham to Provincetown that contains thousands of shipwrecks. The dangerously-hidden and constantly-moving shoals (a natural submerged ridge, bank, or bar of unconsolidated material) located just off-shore have claimed over 3,000 vessels, earning it the moniker of the "ocean graveyard".

In 1717, the pirate ship *Whydah Gally* was caught in a Nor'easter and fell victim to this area, strewing its plunder into the sand along 4 miles of shoreline. Locals were unable to recover much as the riches were buried in the sand, so the ship was largely forgotten about and turned into local lore. It wasn't until 260 years later that the explorer Barry Clifford and his team discovered the wreck. They've been able to excavate over 200,000 artifacts, including the ship's bell and a small placard containing its name, therefore making the *Whydah* the only authenticated pirate wreck in the US.

This presentation leveraged the lore around the Whydah wreck to illustrate how to import data, create a GeoDataFrame in `GeoPandas`, and draw an interactive map with `folium`. An HTML file with the exported `folium` map is saved in the `index.html` file in the repository.

## Running the Code Demo Notebook

### In the Browser

This repository has enabled [Binder](https://mybinder.org/) to run the Jupyter notebook. Just click below to launch an interactive notebook in your browser:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/HKuz/Geospatial_Overview/HEAD)

### Locally with an Anaconda Environment

If you've cloned this repository and want to run the code locally, you'll need to make sure you have the necessary Python packages installed on your machine.

The Jupyter Notebook runs off an Anaconda environment that contains all of these packages. To re-create the `geo` environment, first make sure you have either an [Anaconda or miniconda distribution](https://www.anaconda.com/) installed, then run the following command:

```bash
conda env create -f environment_geo.yml
```

Once your local environment is ready, activate it (`conda activate geo`) and run the `jupyter notebook` command to access the `geospatial_code_demo.ipynb` file.

### Locally with a pip Environment

If you don't have (or want) Anaconda, you can also use a Python 3 pip environment. Run the following commands to create and activate a pip environment using the `requirements.txt` file:

```bash
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
```

<!--
DATA
Gist with KML reading and dropping Z dimension info:
https://gist.github.com/mazzma12/0a32ce693bb42b742252caabb98519db

List of potential treasure around Massachusetts
https://www.onlyinyourstate.com/massachusetts/hidden-treasure-ma/

GIS
13 Top open source GIS software: https://gisgeography.com/free-gis-software/

CRS
https://www.w3.org/2015/spatial/wiki/Coordinate_Reference_Systems
WGS84, a CRS for latitude-longitude coordinates, is very popular on the web. This has lead to the idea that this CRS can be considered a default CRS. In fact, many specifications have done so (basic geo, GeoJSON, geosparql).

PROJECTIONS
www.thetruesize.com for interactive map showing Mercator projection distortions - as you drag a country around it adjusts to it's accurate relative size.

More than you ever wanted to know about GeoJSON:
https://macwright.com/2015/03/23/geojson-second-bite.html

FOLIUM
Leaflet.js/folium CRS:
https://gis.stackexchange.com/questions/362582/coordinate-system-mismatch-in-folium

-->

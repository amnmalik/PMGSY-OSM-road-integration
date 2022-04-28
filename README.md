# Description
The Ministry of Rural Development has made its database of roads, habilitations under the [PMGSY rural road connectivity programme](https://pmgsy.nic.in/) available under GODL license which is compatible with OSM data. This means that data from PMGSY can be used to map in OSM.

## Need
Since there are [various issues](https://github.com/datameet/pmgsy-geosadak/issues/14) which prevent directly importing PMGSY data into OSM, road data from PMGSY can only be mapped manually or semi-automatically. This workflow explains one method utilising PMGSY database as a background layer along with the [MapwithAI](Mapwith.ai/) plugin on JOSM

# Workflow
## I. Adding PMGSY as background layer
1. Open JOSM. Download latest version from [here](https://josm.openstreetmap.de/)
2. Go to `Imagery` -> `Imagery Preferences`. Click on **Add a new WMTS layer by adding a URL** (+ WMTS). A new window opens.
3. Enter the following URL in column 2: `wmts:https://api.mapbox.com/styles/v1/planemad/cknj1leps0ywv17lrj8d16vnj/wmts?access_token=pk.eyJ1IjoicGxhbmVtYWQiLCJhIjoiY2l2eDhnNzNpMDAwNzJ5cGowcnpiMXJkdyJ9.NljuPglsRA3mTGf-4CLIEg`
4. Give layer name as PMGSY. Click okay.
5. The imagery now appears as `PMGSY` when you click on `Imagery`
6. The imagery looks like this. A thin black line indicates all roads from the PMGSY database. A grey line indicates data from OSM. A red line indicates data not in OSM.  
![image](https://user-images.githubusercontent.com/43343789/165785056-0920cc67-85b6-4e51-8a63-e593643c06b3.png). 
8. For a complete map with all PMGSY data, click [here](https://projects.datameet.org/pmgsy-geosadak/map.html#12.15/31.94553/77.14099/-28.8)


## II. Installing MapwithAI plugin on JOSM
1. Go to `Edit` -> `Preferences`. A new window opens. Scroll down to `Plugins`.  ![image](https://user-images.githubusercontent.com/43343789/165784364-7892d249-fc40-4647-a48f-d6aaa19dffb4.png)
2. Search for `mapwithai`. Install the latest version (1.9.10 at the time of writing).
3. Restart JOSM. 



# Pre-requisites
In order to effectively follow the workflow you need basic understanding of:
1. Editing OSM data using JOSM.
2. 

# Description
The Ministry of Rural Development has made its database of roads, habilitations under the [PMGSY rural road connectivity programme](https://pmgsy.nic.in/) available under GODL license which is compatible with OSM data. This means that data from PMGSY can be used to map in OSM.

## Need
Since there are [various issues](https://github.com/datameet/pmgsy-geosadak/issues/14) which prevent directly importing PMGSY data into OSM, road data from PMGSY can only be mapped manually or semi-automatically. This workflow explains one method utilising PMGSY database as a background layer along with the [MapwithAI](Mapwith.ai/) plugin on JOSM

## Contact
For any queries or issues, either start an issue or write to aman.malik@outlook.com

# Prerequisite
Knowledge of editing OSM using JOSM. For a beginner's guide, see [here](https://learnosm.org/en/josm/)

# Workflow
## I. Adding PMGSY as background layer
1. Open JOSM. Download latest version from [here](https://josm.openstreetmap.de/)
2. Go to `Imagery` -> `Imagery Preferences`. Click on **Add a new WMTS layer by adding a URL** (+ WMTS). A new window opens.
3. Enter the following URL in column 2: `wmts:https://api.mapbox.com/styles/v1/planemad/cknj1leps0ywv17lrj8d16vnj/wmts?access_token=pk.eyJ1IjoicGxhbmVtYWQiLCJhIjoiY2l2eDhnNzNpMDAwNzJ5cGowcnpiMXJkdyJ9.NljuPglsRA3mTGf-4CLIEg`
4. Give layer name as PMGSY. Click okay.
5. The imagery now appears as `PMGSY` when you click on `Imagery`
6. The imagery looks like this. A thin black line indicates all roads from the PMGSY database. A grey line indicates data from OSM. A red line indicates data not in OSM.  
![image](https://user-images.githubusercontent.com/43343789/165785056-0920cc67-85b6-4e51-8a63-e593643c06b3.png). 

7. For a complete map with all PMGSY data, click [here](https://projects.datameet.org/pmgsy-geosadak/map.html#12.15/31.94553/77.14099/-28.8)


## II. Installing MapwithAI plugin on JOSM
1. Go to `Edit` -> `Preferences`. A new window opens. Scroll down to `Plugins`.  ![image](https://user-images.githubusercontent.com/43343789/165784364-7892d249-fc40-4647-a48f-d6aaa19dffb4.png)
2. Search for `mapwithai`. Install the latest version (1.9.10 at the time of writing).
3. Restart JOSM. 

## III. Mapping 
1. Go to `Imagery` and click on `PMGSY`. The background layer opens.
2. Select any region/area you want to map and click on `Download Map Data`![image](https://user-images.githubusercontent.com/43343789/165787718-8c33276d-73e6-4f86-8267-e2d29661db12.png). A new window opens. Click on both Openstreetmap data and MapwithAI data; click `Download` 
![image](https://user-images.githubusercontent.com/43343789/165788879-606d6780-f849-4650-b36e-30215d968c99.png)

3. In the layer window on the right, both `Data Layer` and `Mapwithai` layers should be available. If no `Mapwithai` layer is visible, go to `Data` -> `Mapwithai`-> Download data. A new mapwtihai layer should appear but it is probably empty. 

5. Go back to Data->MapWithai-> and click on `MapWithAI`
![image](https://user-images.githubusercontent.com/43343789/165790313-473ce112-7957-4809-a670-21d5bbe30ccb.png)

6. MapwithAI data appears as a pink line. This data is calculated by running AI algorithms on satellite imagery to find roads. In the example below, you see that the algorithm finds: i) roads marked as missing in OSM but present in PMGSY map (blue arrow), ii) Roads not available in PMGSY but in satellite imagery (black arrow), iii) Roads in PMGSY data but not in MapwithAI (red arrow).
![image](https://user-images.githubusercontent.com/43343789/165791587-d19deea5-1479-42da-aa70-69561d4355ae.png)

7. Although the PMGSY has lots of previously unmapped roads, the database is not comprehensive, resulting in roads that the AI algorithm finds but are not in the PMGSY database. At the same time, the AI algorithm can often mistake trails, riverbeds, or electricity lines for roads. If you think that the road found by MapwithAI is indeed a road, feel free to mark it. From point iii), we see that the AI algorithm sometimes also fails to find roads. This can be due to many reasons but often is because of tree or vegetation cover. If the road is visible on PMGSY, you can map it by hand.

8. To upload the data found using mapwithai on OSM, you first need to transfer the data into the `Data` layer. To do this click on the pink line and press `Shift + A`. Activating the `Data` layer shows that the line is now visible there.
![image](https://user-images.githubusercontent.com/43343789/165795600-6b28da5c-6b28-49d2-8fb2-22a496c52b5c.png)

9. The AI algorithm already fills in default values `highway=*` and `source=*` tags for a marked line. You can correct them if you want  before uploading.





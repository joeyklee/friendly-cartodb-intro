# Friendly CartoDB Introduction
This is a friendly introduction to web mapping using CartoDB. 

## Overvview
### Data Creation & Data Import Pt. I:
#### Create data
* Making data with [Geojson.io](http://geojson.io/)
* Making data with [CartoDB - adding geometries](https://docs.cartodb.com/tutorials/adding_geometries/)

#### Data Import:
* "Connect Data Source" using CartoDB

#### Data Acquisition:
* Sources of data:
	* OpenStreetMap:
		* [Mapzen OSM Metro Extracts](https://mapzen.com/data/metro-extracts/)
	* Open Data Catalogs:
		* [Vancouver Open data](http://data.vancouver.ca/datacatalogue/index.htm)
		* [Toronto Open Data](http://www1.toronto.ca/wps/portal/contentonly?vgnextoid=1a66e03bb8d1e310VgnVCM10000071d60f89RCRD)
		* [San Francisco Open Data](https://data.sfgov.org/)
		* ...do a web search for "city" + "open data"
	* University data sets:
		* [UBC GIS Data](http://help.library.ubc.ca/finding-resources/geographic-information-systems/)
	* Open Research Data:
		* [Zenodo](https://zenodo.org/)
		* [Figshare](https://figshare.com/)
	* Blogs:
		* [RT Wilson's Blog of data sources](http://freegisdata.rtwilson.com/)
		* ... do a web search "gis" + data sources

#### Visualization Pt.I
* The cartodb viz wizard
* legends
* Basemaps
* labels

#### Data Merging
* data merging

#### Simple Data Filtering
* Filtering using sliders

#### Visualization Pt.II
* torque - animations
* adding labels and 


#### Export & Share
* Export to web 
* Export data


***

## Making maps on the Web, for the Web
In this workshop we're going to be using CartoDB - a Software as a Service (SaaS) cloud computing platform that provides GIS and web mapping tools for display **in a web browser**. CartoDB users can use the company's free platform or deploy their own instance of the open source software. CartoDB is offered as freemium service, where accounts are free up to a certain size. For larger accounts, a fee is applied.

The great thing about using web-based GIS and mapping tools is that there's basically no setup - you just sign up with CartoDB and start mapping. For anyone who has set up GIS software for desktop, you might understand why this is so amazing. 

Here's a little tour of CartoDB:

(insert video here)



## Data Creation & Upload pt.1


What does it mean to make a map? In many ways it means to create geographic data. This could be in the form of points, lines, and polygons (vector data) or in the form of images (raster data). I won't go into a lot of detail here about geographic data types, but you can find out more about these types of data [here](). 

### Data Creation with Geojson.io

#### Making data
So let's say, we wan't to create some geographic data - How do we do this? There are a number of tools that exist for making geographic data. In the past, most of the geographic data production was either done the old school way - pen and paper - and using desktop GIS software. However, the web has become/is becoming ever more *the place* where geographic data is being and can be generated. Let's look at one called [geojson.io](http://geojson.io/). 

![](assets/img/geojson-io-1.png)

<iframe width="420" height="315" src="https://www.youtube.com/embed/kr3d6SQvZ6o" frameborder="0" allowfullscreen></iframe>

***NOTE: In the video, I mix points, lines, and polygons in the same file - try to avoid this!!! Points with points, lines with lines, polygons with polygons!***

You can use geojson.io to:
* You can use the interface to add points, lines, rectangles, and custom polygons. 
* You can add **properties** to the features using the text editor on the right. The structure of adding properties looks like this:
	```
	"properties": {
	        "key": "value",
	        "key": "value",
	        "key": "value"
	 },
	```
where you can think of the "key" as a column header, and "value", as well, the value. Each "Key-value" pair is separated with a comma (","). So for example we might see something like this:

	```
	"properties": {
	        "name": "trout lake",
	        "location": "Vancouver, BC",
	        "Dog park": "yes"
	 },
	```
* You can switch the basemap to the satellite mode if you want to create vectors from aerial imagery. **make sure you understand the terms and conditions**



#### Saving data
You can save the data in a number of places:

* On the web:
	* Github (You'll need to sign up to github - its free)
	* Gist (You'll need to sign up to github - its free)
* On your desktop in these various formats:
	* GeoJSON
	* TopoJSON
	* CSV
	* KML 
	* WKT
	* Shapefile (.shp)

Try saving your data as:
1.  a GeoJSON 
2.  to a Gist 

## Getting Started with CartoDB:

### Sign-up for CartoDB:
* Sign up for CartoDB by going to [Cartodb.com](https://cartodb.com/)
	* you can login with your [google account](https://www.google.ca/) or 
	* select a **username**, **email**, and **password**


### Create a new map!
If you've just created your account, you'll get a nice prompt like this:

![](assets/img/newmap2.png)

If you already have an account, you'll get a prompt like this:

![](assets/img/newmap1.png)

Either way, you'll click **new map** to *create a new map*.

### Connect dataset:
Now we're going to connect the data we just created and add it to the CartoDB database. 

![](assets/img/connectdata1.png)

We will then get a whole slew of nice options - you can see that we can directly drag and drop data, upload from Google Drive, dropbox, etc. Pretty cool!

Lucky for us, our data is stored on [Github](https://github.com/) and therefore we can link directly to it.

![](assets/img/connectdata2.png)

In the input box, copy and paste this link and click **submit**:

```
https://gist.githubusercontent.com/anonymous/93f6c4083ffe4b59e586a74b4ae0085b/raw/ee6ae52994830b4c5ec10ec0356614bba8496ed8/map.geojson
```

![](001-cartodb-upload-3.png)

The data gets uploaded and instantly you can see both a table and a map view! (NOTE: that all the data is converted to lines - remember to try and keep your geometries from mixing).

<iframe width="420" height="315" src="https://www.youtube.com/embed/gb-iFYiSALk" frameborder="0" allowfullscreen></iframe>

Whoa! We already have a web map! Before we move on to more exciting things, let's look at one alternative for generating geographic data.

### CartoDB "Add Feature"

We saw how we can use  to create data and save it using geojson.io. CartoDB also has methods of adding data. Let's try out these tools. 

Start by going to the `data view` and clicking `new dataset`:

![](assets/img/002-cartodb-createFeature-1.png)

Click `create empty dataset`:
![](assets/img/002-cartodb-createFeature-2.png)

There will be a loading screen
![](assets/img/002-cartodb-createFeature-3.png)
![](assets/img/002-cartodb-createFeature-4.png)

You can then add daa in 2 ways:
1. You can add data via latitude/longitude coordinates:
![](assets/img/002-cartodb-createFeature-4.png)
![](assets/img/002-cartodb-createFeature-5.png)
2. You can switch to the `map view` and the add the geometry this way:

![](assets/img/002-cartodb-createFeature-6.png)
![](assets/img/002-cartodb-createFeature-7.png)

You can then edit the rows and the columns either in the `map view` or in the `table view`.


## Data Acquisition

Woohoo! Now we've got a number of tools under our belts for making our own data. But really how often are you creating your own data rather than using existing datasets? The reality is: not that often. Usually when working with maps, we will tap into some existing data sources, do analysis on them, and generate derivative data from your analyses. Take some time to find some data that interests you or get your data that you're interested in working with. There's a list in the [Overview](##overview).

There are lots of data out there, from urban datasets on taxi and bus data to global data on from social media sources like twitter and instagram. Not all of these data come in GIS friendly formats and sometimes need to be wrangled a bit in order to be made useful. We won't get deep into Application Programming Interfaces (API's) today, but just know that you can use API's to retrieve data from things like Twitter, the international space station, Modo (the car co-op), car2go, etc.  

*** 

# Building our First Visualization with CartoDB

## Data:

* [X Hours of Vancouver Twitter Data]()
	* I've collected 3500 tweets from the Metro Vancouver area using the Twitter streaming API.  
* [Metro Vancouver polygons]():
	* We will use the city boundaries for the metro vancouver area to create a choropleth for the number of tweets per city. 

## Make a new Map

The first thing we need to do is make a new map. 


## Connect the Twitter data to CartoDB:

In the URL input box, you will first add the link to the Twitter data:

```

```















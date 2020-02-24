# Homework

## Joining Flat Files with Vector Layers

Looking at (one aspect of) the digital divide in Pennsylvania.

1. Get these data sets, and save them into your designated folder for QGIS files; extract both folders:
    * PA Census Tracts from [TIGER/Line Shapefiles](https://www.census.gov/geo/maps-data/data/tiger-line.html) - 2018, Web Interface, Census Tracts, Pennsylvania
    * [American FactFinder](https://factfinder.census.gov/) - Internet Access (under Advanced Search, Topics -> Housing -> Physical Characteristic), limit Geographies to Census Tracts in Pennsylvania (all) (B28002)
1. Start a new project (and then save it in your designated folder for QGIS files).
1. Add the Census Tracts shapefile as a layer.
1. Have a look at its attribute table.
1. Clean up the Internet Access (ACS_17_574_B28002_with_ann) file in Excel, to remove data we don't want. (Open it, Save As something meaningful, and then start making changes.)
    * It's vital that we keep the GEO.id2 field, but let's change it to GEO_id2.
    * Let's say we're looking at the estimated number of households without internet access, column HD01_VD13 (second to last column); we should keep that. We'll also want the estimated total number of households (HD01_VD01). We should keep those two columns, plus GEO_id2. We should also give them more useful names: total_households and no_internet_households.
    * We should also remove that explanatory row (row 2).
1. Now, we can add it as a delimited text layer. Unlike the tree data file, this one has no geometry. After it's added, change its name to something easier to work with, like "census_data"
1. To add the information from this layer to the attribute table of our census tracts, we need to perform what's called a "Join." Right-click on the census tracts layer, and choose "Properties," and then choose "Joins" on the left-hand menu.
1. Hit the plus sign.
1. Since we're in the Properties of the tracts layer, the join layer will be the census_data layer. We're combining these tables based on the census tract ID, so GEO_id2 will be our join field, and GEOID will be our target field.
1. Click OK, and go look at the attribute table now. (Aren't you glad we changed the layer name on our census data? That said, we could have changed the column label prefix in the layer join dialog box, too, but it's useful to have it match.)
1. Now we're going to add a column to hold the percentage of households without internet. (I called mine "no_net_per.") It's done just like the density of trees in the previous exercise, only we take the number of households without internet and divide by the total number of households in each tract. (Don't forget to make it a decimal type column, not a whole number type.)
1. After we add that column, sort it. Nulls aren't great, right? I propose we highlight those rows and use the Field Calculator to set them to zero.
1. Now we're going to make a graduated color map, just like we did in the first example.
1. We're also going to set the display values on mouse-over.

What can you tell me about the digital divide in PA? How about in Allegheny County?

## Readings

Work through [Joining Flat Files with Vector Layers](#qgis2) on your own. Bring a map and a data-backed assertion about the digital divide in PA or Allegheny County to class next week.

 ~~Look through the [PASDA](http://www.pasda.psu.edu/) data sets, and make a map and a data-based assertion that's interesting to you. If none of the data sets speak to you, please look at how many [oil and gas](http://www.pasda.psu.edu/uci/DataSummary.aspx?dataset=283) or [coal](http://www.pasda.psu.edu/uci/DataSummary.aspx?dataset=271) operations are being run in the [Chesapeake Bay watershed](http://www.pasda.psu.edu/uci/DataSummary.aspx?dataset=59) (or Allegheny County or any other subset of the state of interest to you). There are also [oil and gas water pollution control facilities](http://www.pasda.psu.edu/uci/DataSummary.aspx?dataset=284), if you'd like to look at those. Don't forget to cite your data sources, and keep a log of the changes you make, so that another data analyst could follow your steps.~~

~~You have enough tools to get started on a project using Census data, as well. Explore American Factfinder (or any other source of data we've covered in 102 or 201), and think about what kind of map you'd like to make for your mapping project. We're going to explore areas of interest at the beginning of next class, and I'm hoping groups will magically coalesce ... but failing that, we'll work together to figure something out.~~

### Readings (you've got two weeks for this one)

* [What's in a map?](https://www.gislounge.com/whats-in-a-map/)
* [Design principles for cartography](https://www.esri.com/arcgis-blog/products/product/mapping/design-principles-for-cartography/)

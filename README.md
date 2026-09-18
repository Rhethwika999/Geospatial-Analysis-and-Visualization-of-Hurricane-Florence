# Geospatial Analysis and Visualization of Hurricane Florence 🌀🗺️

Geospatial analysis and visualization of **Hurricane Florence** using Python to map the hurricane's trajectory across the United States. The project combines hurricane storm-history data containing latitude and longitude coordinates with U.S. state boundary geospatial data to visualize the storm's path geographically.

## Aim 🔍

The primary aim of this project is to use **geospatial data analysis and visualization** to understand and visualize the trajectory of Hurricane Florence. The project demonstrates how traditional latitude and longitude data can be transformed into geospatial objects and combined with geographic boundary data to create meaningful spatial visualizations.

## Objectives 🎯

1. **Explore U.S. Geographic Data**: Load and visualize U.S. state boundary data using GeoPandas.
2. **Analyse Hurricane Florence Data**: Explore storm-history information including latitude, longitude, wind speed, pressure, movement, and storm classification.
3. **Create Geospatial Coordinates**: Convert latitude and longitude observations into geometric Point objects.
4. **Build a GeoDataFrame**: Transform the hurricane dataset from a standard Pandas DataFrame into a GeoPandas GeoDataFrame.
5. **Visualize the Hurricane Path**: Plot Hurricane Florence's trajectory using its geographic coordinates.
6. **Overlay Geographic Data**: Combine the hurricane path with U.S. state boundaries to provide geographic context for the storm's movement.

## Libraries and Packages Used 📦

* **Python Libraries**:

  * `pandas`: For loading, manipulating, and analysing hurricane storm-history data.
  * `geopandas`: For handling and visualizing geospatial datasets.
  * `matplotlib`: For creating geographic plots and visualizations.
  * `shapely`: For converting latitude and longitude coordinates into geometric Point objects.

## Data Sets and Sources 📊

### Hurricane Florence Storm History

* **File**: `stormhistory.csv`
* **Records**: 105 storm observations.
* **Description**: Contains historical observations describing the development and movement of Hurricane Florence.
* **Key Variables**:

  * `AdvisoryNumber`
  * `Date`
  * `Lat`
  * `Long`
  * `Wind`
  * `Pres`
  * `Movement`
  * `Type`
  * `Name`
  * `Received`
  * `Forecaster`

The dataset records the storm from its earlier classification as a **Potential Tropical Cyclone** through later stages including **Tropical Depression** and **Post-Tropical Cyclone**.

### U.S. State Boundary Data

* **File**: `gz_2010_us_040_00_5m(1).json`
* **Format**: GeoJSON
* **Description**: Contains geographic boundary information for U.S. states, including state names and polygon/multipolygon geometries.
* **Purpose**: Used as the geographic base layer on which the Hurricane Florence trajectory is plotted.

## Data Preparation 🧹

### Loading Geographic Data

The U.S. state boundary dataset is loaded using GeoPandas and initially visualized to understand its geographic coverage.

### Geographic Filtering

Since the analysis focuses on the hurricane's trajectory relative to the continental United States, **Alaska and Hawaii are removed** from the visualization.

This produces a clearer map of the mainland states relevant to the hurricane trajectory.

### Loading Hurricane Data

The Hurricane Florence storm-history dataset is loaded using Pandas. Initial plotting of the standard DataFrame demonstrates that latitude and longitude columns alone are not automatically interpreted as geographic coordinates.

## Geospatial Transformation 🌍

A key part of the project is transforming the hurricane dataset from a traditional tabular dataset into a geospatial dataset.

### Latitude and Longitude Conversion

The `Lat` and `Long` variables are converted into geographic points using `shapely.geometry.Point`.

Each storm observation therefore represents a geographic location:

`Point(longitude, latitude)`

The longitude values are converted to negative values so that the hurricane coordinates align correctly with the longitude representation used by the U.S. geographic dataset.

### Creating a GeoDataFrame

The generated Point objects are stored in a new `coordinates` column.

The Pandas DataFrame is then converted into a **GeoPandas GeoDataFrame**, using the coordinate points as its geometry.

This transformation enables geospatial plotting and allows the hurricane trajectory to be combined with other geographic datasets.

## Methodology 📈

### 1. Geographic Data Exploration

U.S. state boundaries are loaded and plotted using GeoPandas to understand the geographic structure of the dataset.

### 2. Geographic Filtering

Alaska and Hawaii are excluded to focus the visualization on the mainland United States and improve map readability.

### 3. Hurricane Data Exploration

The storm-history dataset is loaded and inspected to understand Hurricane Florence's recorded geographic positions and storm characteristics.

### 4. Coordinate Transformation

Latitude and longitude values are transformed into Shapely `Point` geometries.

### 5. GeoDataFrame Creation

The hurricane observations are converted into a GeoDataFrame, allowing the data to be treated as geospatial information rather than ordinary numerical variables.

### 6. Hurricane Path Visualization

The geographic points are plotted to reveal the trajectory of Hurricane Florence.

### 7. Geographic Overlay

The U.S. state boundary GeoDataFrame and Hurricane Florence GeoDataFrame are plotted on the **same Matplotlib axes**.

This overlays the hurricane observations on the U.S. map and provides geographic context for the storm's movement.

## Implementation Steps ✅

1. **Import Libraries**: Imported Pandas, GeoPandas, Matplotlib, and Shapely.
2. **Load Geographic Data**: Read U.S. state boundaries from the GeoJSON dataset.
3. **Visualize State Boundaries**: Created an initial map of the United States.
4. **Filter Geographic Data**: Removed Alaska and Hawaii for clearer visualization.
5. **Load Hurricane Data**: Imported Hurricane Florence storm-history observations.
6. **Create Geographic Points**: Converted latitude and longitude values into Shapely Point objects.
7. **Create GeoDataFrame**: Converted the hurricane DataFrame into a GeoPandas GeoDataFrame.
8. **Plot Hurricane Trajectory**: Visualized the geographic path of Hurricane Florence.
9. **Overlay Spatial Data**: Plotted the hurricane trajectory and U.S. state boundaries on the same axes.

## Results 🔑

### Hurricane Trajectory

Converting the latitude and longitude coordinates into geometric points successfully transforms the storm-history dataset into spatial data, allowing the trajectory of Hurricane Florence to be visualized geographically.

### Geographic Overlay

Overlaying the Hurricane Florence GeoDataFrame on the U.S. state boundary map provides a much clearer representation of the storm's movement than plotting the raw latitude and longitude columns as ordinary numerical variables.

### Geospatial Data Transformation

The project demonstrates the importance of converting conventional datasets into appropriate geospatial structures before performing spatial visualization.

A standard Pandas DataFrame containing latitude and longitude values does not automatically understand their geographic relationship. Converting these coordinates into Shapely geometries and creating a GeoDataFrame enables proper geospatial analysis and visualization.


## Conclusion 🏆

This project demonstrates how Python's geospatial ecosystem can be used to transform and visualize location-based data. Hurricane Florence's latitude and longitude observations were converted into geographic Point objects and integrated into a GeoPandas GeoDataFrame.

By overlaying the hurricane trajectory with U.S. state boundary data, the project creates a clear spatial representation of the storm's movement and demonstrates the importance of correctly structuring geographic information before visualization.

Overall, the project provides practical experience with **GeoPandas, Shapely, Pandas, Matplotlib, GeoJSON data, coordinate transformation, and geospatial visualization**.


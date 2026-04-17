Healthy Grocery Stores USA (OSM + Overture)

This project downloads healthy grocery store locations across the United States using two major open geospatial data sources:

OpenStreetMap (OSM) via Overpass API
Overture Maps Foundation via DuckDB + Parquet

The goal is to build a nationwide dataset of food access points, including grocery stores, supermarkets, organic markets, and related food facilities.

Project Overview

## This repository contains two main workflows:

# Overture Data Pipeline
Connects to Overture Maps using DuckDB
Streams nationwide places dataset
Filters food-related categories:
grocery_store, supermarket, health_food_store
bakery, butcher_shop, seafood_market
farmers_market, delicatessen, convenience_store
Extracts:
Name, category, address
City, state, ZIP
Latitude & Longitude
Outputs a GeoDataFrame → Shapefile
# OpenStreetMap (OSM) Pipeline
Uses Overpass API to query data by U.S. state
Extracts:
shop = supermarket, greengrocer, health_food, etc.
amenity = marketplace
organic = yes
Handles:
API retries & rate limits
XML parsing
Outputs:
Clean dataset with attributes and coordinates
Shapefile for GIS use

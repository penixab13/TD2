# Spatial Database - TD-2

This repository provides the steps for *Creating Spatial Tables* using PostgreSQL, PostGIS, and QGIS. This tutorial guides users through creating spatial tables for points, polygons, and lines, inserting data into these tables, and visualizing the data using QGIS.

## Overview

The tutorial covers:

1. *Creating a Table for Points*
2. *Creating a Table for Polygons*
3. *Creating a Table for Lines*
4. *Inserting Data Using QGIS*

## Steps

### 1. Create a Table for Points
- Using PgAdmin, execute the following SQL command to create a table with a geometry column for storing point data:
  sql
  CREATE TABLE points_of_interests (
      id SERIAL PRIMARY KEY,
      nom VARCHAR(255),
      geom GEOMETRY(Point, 4326)
  );
  

- Insert data into this table using QGIS:
  1. Open QGIS and connect to your PostgreSQL database.
  2. Right-click on PostgreSQL in the Explorer panel > New Connection.
  3. Provide your connection details and test the connection.
  4. Once connected, double-click the points_of_interests table to add it as a layer in QGIS.
  5. Switch to edit mode, add points to the layer, and save changes.

- Verify the inserted data using the following query in PgAdmin:
  sql
  SELECT * FROM points_of_interests;
  

### 2. Create a Table for Polygons
- Using PgAdmin, execute the following SQL command to create a table with a geometry column for storing polygon data:
  sql
  CREATE TABLE zones_protegees (
      id SERIAL PRIMARY KEY,
      nom VARCHAR(255),
      geom GEOMETRY(Polygon, 4326)
  );
  

- Insert data into this table using QGIS:
  1. Add the zones_protegees table as a layer in QGIS.
  2. Switch to edit mode, draw polygons, and save changes.

- Verify the inserted data using the following query in PgAdmin:
  sql
  SELECT * FROM zones_protegees;
  

### 3. Create a Table for Lines
- Using PgAdmin, execute the following SQL command to create a table with a geometry column for storing line data:
  sql
  CREATE TABLE routes (
      id SERIAL PRIMARY KEY,
      nom VARCHAR(255),
      geom GEOMETRY(LINESTRING, 4326)
  );
  

- Insert data into this table using QGIS similarly to the previous steps.

## Notes
- Use the 4326 SRID for all geometry columns.
- Ensure QGIS is properly configured to connect to your PostgreSQL database.

## License
This repository is licensed under the MIT License. See LICENSE for details.

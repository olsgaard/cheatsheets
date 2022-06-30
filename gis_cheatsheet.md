# GIS - `Geographic Information System` Notes

- Geographic - Spatial
- Information - Attributes
- System - All the moving parts

# Words and definitions

- Authority String: 
    - A shorthand for a common projection, published by a well known organization. Typical authority strings include:
        - EPSG, European Petroleum Survey Group. EPSG:4326 is their Authority String for GPS projection
        - ESRI, Environmental Systems Research Institute. A US provate corporation selling GIS systems
        - WS, WGS, World Geodetic System. A standard mapping the wolrd as an an ellipsoid. WS84, is the GPS standard, also known as WGS1984, presumably becasue the revision was published in 1984
- CRS: 
    - Coordinate Reference System, also known as a Spatial Reference System
- SRS: 
    - Spatial Reference System, also known as a Coordinate Reference System
- Latitude
    - East/West   coordinate. X-axis
- Longitude
    - North/South coordinate. Y-axis

# Geographic VS Projected CRS
Both are coordinate systems

- Geographic coordinate systems are based on a spheroid and utilize angular units (degrees)
    - WGS 84 / GPS
    - Needs non-euclidean math to measure distances.
    - GeoPandas can't handle these for measuring distances.

- Projected coordinate systems are a euclidean a plane 
    - The spheroid is projected onto a 2D surface.
    - utilize linear units (feet, meters, etc.)
    - This is good for measuring distances in local areas, as you can use normal euclidean calculations, but will be distorted when measuring on large areas.

- More info:
    - https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/gcs_vs_pcs/

# Common projections

- EPSG:3395
    - The World Mercator Projection
    - Preserve parallel lines, good for navigating on sea
    - Huge area distortion the closer you move to the poles

- EPSG:4326
    - Also known as WGS 84
    - "GPS Coordinate system"
    - Used by the GPS satellite navigation system and for NATO military geodetic surveying.

# Find projection for your project

- projectionwizard.org
    - Enter a rough area, and type of distortion you can tolerate and receive a projection map

# Sources and links

- https://gisgeography.com/
    - Collection of high quality articles on GIS topics, links to data sources.
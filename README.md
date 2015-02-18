# contour_tooling
AWK scripts to generate ArcPy for topographic-bathymetric contouring on very fine grids.
# contour_tooling
AWK scripts to generate ArcPy for topographic-bathymetric contouring on very fine grids.
## AWK tools for contouring in ArcGIS

These scripts were created to help analyze large raster surfaces (8 GB--80 GB) to detailed topographic-bathymetric contours.
Using Esri ArcGIS 10.2.2 and 10.3 for Desktop, stability issues required the use of ContourList() calls on clipped terrain grid extents.
Also, to avoid redundant storage, a single surface (meters in x,y,z) was analyzed for both metric and US customary contours, facilitated by ArcPy scripting and appropriately generated Feature Class names.

ArcGIS Python dialect, [ArcPy](http://resources.arcgis.com/en/help/main/10.2/index.html#/What_is_ArcPy/000v000000v7000000/) packages access to several hundred geoporcessing functions that can be licensed from Esri as ArcGIS for Desktop and its extensions.  As a Windows 32-bit application, there are occasional stability issues when analyzing large raster inputs or producing large vector outputs.  Doing both at the same time, as when analyzing a finely detailed terrain with frequent topographic contours, is an exercise in patience.  These scripts were created to help with that issue.

By software engineering standards, these scripts could appear appallingly ugly---and yet they bear the scars of actual use.  The workflow that inspired their use analyzed single-precision floating point grids from [40k by 45k] on the smallest to [125k by 150k] on the largest size.  The vector features were output to Esri File Geodatabase format for performance in use, and exceeded 3 GB of feature detail.

Attempts were made to keep the largest possible areas contiguous for improved contour-drawing performance in desktop environment.  Stability of Esri's 32-bit application led to an adaptation where the terrain was split into five sectors based on somewhat subtle characteristics.  



Tips & Tricks
==============

This directory contains a list of tips & tricks useful to create EPANET and SWMM models. 

Pre-processing data to build water supply and drainage models is always a hard task. Usually, available data has several errors, such as disconnected links or missing nodes, which must be corrected before running a simulation. Some work around can also be needed to combine data, such as assigning elevation to nodes or relating land use types with SWMM sub-catchments parameters. Hopefully, available GIS software provide nowadays several tools to manage this data and to organize it in a way that EPANET and SWMM can read it.


##Tips & tricks to build the network

###1. Create network nodes
- GRASS: v.net.nodes ?
- [inp.PINS] (https://sites.google.com/site/inppins/): inp.Tools: Create Node Shp from Link Shp

###2. Clean vector files with GRASS
- Snap lines: v.clean.snap
- Break lines at intersections: v.clean.break
- Remove duplicated lines: v.clean.rmdupl
- Simplify lines: v.clean.prune; v.clean.rmline; v.clean.rmsa; v.generalize

###3. Slip polylines at points
- gvSIG: Sextante --> Split polylines at nodes

###4. Slip polylines at given distance from upstream and downstream nodes / create nodes
- GRASS: v.split

###5. Assign start and end nodes to links
- GRASS: v.distance ?
- [inp.PINS] (https://sites.google.com/site/inppins/): inp.Tools --> FromNode/ToNode assign to Link Shp

###6. Nearest neighbourhood analysis
Examples: assign point with demands to closest nodes (points to points); assign data defined by points, such as diameters and materials in drawing files, to closest links (points to links).
- GRASS: v.distance ?
- gvSIG: Geoprocessing Tools --> Spatial Join (with 'Transfer from nearest feature' option) (Note: distances base on centroids)

###7. Interpolation
Examples: interpolate invert levels for manhole nodes in SWMM

###8. Network simplification
Example: prune, merge

###9. Create XS for links based on DTM
- [inp.PINS] (https://sites.google.com/site/inppins/): inpMaker --> Tsects

###10. Point sample
- QGIS: 'Point Sampling Tool' plugin
- GRASS: v.sample

###11. Trace 
- QGIS: 'Flow Trace' plugin (Note: this plugin analysis depends on the polyline direction)

###12. Profile 
- QGIS: 'Profile tool' plugin


##Tips & tricks for SWMM sub-catchments

###1. Sub-catchment delineation - Thiessen delineation within polygons
Example: divide major sub-catchments, delineated by the user, with Thiessen polygons for each node.

###2. Sub-catchment discharge connections
- [inp.PINS] (https://sites.google.com/site/inppins/): inpTools --> Subcatchment connections
Note: if sub-catchments are delineated one per each node, the point sampling tool can also be used to assign node discharges for sub-catchments with a table merge afterwards.

###3. Sub-catchment land use data
To download OSM data - QGIS: OSM --> Download data
For raster stats analysis - GRASS: v.rast.stats

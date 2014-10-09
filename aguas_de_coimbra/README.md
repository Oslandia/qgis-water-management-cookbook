Real case study - one day hydraulic simulation
========================================
This example is a one day simulation of a real network. It aims to present the use of QGIS-EPANET plugin for model building, simulations run and results analysing. 

The EPANET model used in this example was developed by AC, Águas de Coimbra, E.M., a water utility company that manages the water supply and the drainage system of Coimbra, Portugal.
 

1. Model characterization:

*Reservoirs: 1 un. 
*Tanks: 1 un. 
*Junctions: 272 un. 
*Pipes: 294 un. (29.27 km) 
*Pumps: 1 un. 
*Valves: 1 un. (pressure reducing valve - PRV) 

 

Overall map: 

![Network](images/ac1.png)
 

##2. Model building: 

To build the EPANET model in QGIS you only have to organize GIS according with inp file format. The essential condition is to organize the attributes following the same order as the inp file format for each object - please check EPANET manual. 

For this example, we build the model already for you. You can open it in 2 ways: 


###2.1. Open the project with the spalite data base: 

![Spalite_project](images/ac2.png)
 

###2.2. Insert the the shape files and the csv tables in your project: 

![Shape_files](images/ac4.png)
![csv_tables](images/ac5.png)
 

Finally, you should get the model in QGIS:  

![Model](images/ac3.png)
 

You can add a base map in QGIS, such an OSM base layer with OpenLayers plugin: 

![OSM_adding](images/ac7.png)
![OSM_basemap](images/ac8.png)
 

Note: This example is defined in the Portuguese Grid projection - EPSG:20791  

![example_projection](images/ac6.png)
 

##3. Model dataset 

Now let's take a look at the model objects. You can open the attributes table for each one and check the parameters defined as follows. 


###3.1. Reservoir and pump details: 

In this example the reservoir is defined with a fixed head and the pump is defined with an head-discharge curve defined in the "curves" table. 

![reservoirs_pumps](images/ac9.png)
 

###3.2. Tank details: 

![tanks](images/ac10.png)
 

###3.3. PRV valve details: 

![valves](images/ac11.png)
 

###3.4. Junctions details: 

Junctions are characterised essentially by the elevation and demands. The demands were calculated with the average consumptions of the geo-located clients and assigned to the nearest node. Each demand is defined by the demand value and its pattern. 

![junctions](images/ac12.png)
 

###3.5. Pipes details: 

![pipes](images/ac13.png)
 

###3.6. General tables: 

General tables presented in the next figure define the EPANET options, simulation times and report options. Related with the system operation, a status table define the initial condition of several objects and the controls define the operation rules of the pump. 

![tables](images/ac14.png)
 

##4. Model runs 

To run the model you just have to open the EPANET-QGIS plugin in the processing toolbox. Then verify if all the objects are correctly selected, that should be automatically assigned to each category if they have similar name.
![plugin](images/ac15.png)
 

Press Run and check out the results in QGIS! 

![results](images/ac16.png)
 

##5. Model results 

The results can also be visualized with support of a base map that can be OSM or existing ones: 

![results_osm](images/ac17.png)
![results_ortos](images/ac18.png)
 

Then you can visualise results for each object. Just as an example, the following section show the simulation results for the main objects of this system. 

###5.1. Pump operation results: 

The following figure shows the flow in the pump and the pressure in its downstream node.  

![results_pump](images/ac19.png)
 

###5.2. Tank results: 

The following figure shows the tank level and the flow velocity in its inlet and outlet pipes. 
 
![results_tank](images/ac20.png)
 

###5.2. PRV results: 

The following figure shows the PRV operation with the pressure in its inlet and outlet nodes. 

![results_prv](images/ac21.png)
 

##6. Conclusions 

This example shows the EPANET-QGIS plugin running with a real network example. 
As an user, you can now take advantage of all the flexibility to manage data that QGIS allows and perform whatever scenario evaluation you want!
 

Credits
=======
![logo](http://www.aguasdecoimbra.pt/templates/aguascoimbra/logo.png) 

Acknowledgements: AC, Águas de Coimbra, E.M. - http://www.aguasdecoimbra.pt; Luis Costa (Head of Planning and Construction Department), Sandra Pereira (Eng) 

Disclaimer: This example can only be used with the EPANET-QGIS plugin. It cannot be used for commercial proposes. The authors and the AC, Águas de Coimbra, E.M. disclaim any responsibility for its use.

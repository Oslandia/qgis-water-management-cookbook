Real case study - one day hydraulic simulation
========================================
This example is a one day simulation of a real network. It aims to present the use of QGIS-EPANET plugin for model building, simulations run and results analysing. <br>
The EPANET model used in this example was developed by AC, Águas de Coimbra, E.M., a water utility company that manages the water supply and the drainage system of Coimbra, Portugal.
 <br>
1. Model characterization:
Reservoirs: 1 un. <br>
Tanks: 1 un. <br>
Junctions: 272 un. <br>
Pipes: 294 un. (29.27 km) <br>
Pumps: 1 un. <br>
Valves: 1 un. (pressure reducing valve - PRV) <br>
 <br>
Overall map: <br>
![Network](images/ac1.png)
 <br>
2. Model building: <br>
To build the EPANET model in QGIS you only have to organize GIS according with inp file format. The essential condition is to organize the attributes following the same order as the inp file format for each object - please check EPANET manual. <br>
For this example, we build the model already for you. You can open it in 2 ways: <br>

2.1. Open the project with the spalite data base: <br>
![Spalite_project](images/ac2.png)
 <br>
2.2. Insert the the shape files and the csv tables in your project: <br>
![Shape_files](images/ac4.png)
![csv_tables](images/ac5.png)
 <br>
Finally, you should get the model in QGIS:  <br>
![Model](images/ac3.png)
 <br>
You can add a base map in QGIS, such an OSM base layer with OpenLayers plugin: <br>
![OSM_adding](images/ac7.png)
![OSM_basemap](images/ac8.png)
 <br>
Note: This example is defined in the Portuguese Grid projection - EPSG:20791  <br>
![example_projection](images/ac6.png)
 <br>
3. Model dataset <br>
Now let's take a look at the model objects. You can open the attributes table for each one and check the parameters defined as follows. <br>

3.1. Reservoir and pump details: <br>
In this example the reservoir is defined with a fixed head and the pump is defined with an head-discharge curve defined in the "curves" table. <br>
![reservoirs_pumps](images/ac9.png)
 <br>
3.2. Tank details: <br>
![tanks](images/ac10.png)
 <br>
3.3. PRV valve details: <br>
![valves](images/ac11.png)
 <br>
3.4. Junctions details: <br>
Junctions are characterised essentially by the elevation and demands. The demands were calculated with the average consumptions of the geo-located clients and assigned to the nearest node. Each demand is defined by the demand value and its pattern. <br>
![junctions](images/ac12.png)
 <br>
3.5. Pipes details: <br>
![pipes](images/ac13.png)
 <br>
3.6. General tables: <br>
General tables presented in the next figure define the EPANET options, simulation times and report options. Related with the system operation, a status table define the initial condition of several objects and the controls define the operation rules of the pump. <br>
![tables](images/ac14.png)
 <br>
4. Model runs <br>
To run the model you just have to open the EPANET-QGIS plugin in the processing toolbox. Then verify if all the objects are correctly selected, that should be automatically assigned to each category if they have similar name.
![plugin](images/ac15.png)
 <br>
Press Run and check out the results in QGIS! <br>
![results](images/ac16.png)
 <br>
5. Model results <br>
The results can also be visualized with support of a base map that can be OSM or existing ones: <br>
![results_osm](images/ac17.png)
![results_ortos](images/ac18.png)
 <br>
Then you can visualise results for each object. Just as an example, the following section show the simulation results for the main objects of this system. <br>
5.1. Pump operation results: <br>
The following figure shows the flow in the pump and the pressure in its downstream node.  <br>
![results_pump](images/ac19.png)
 <br>
5.2. Tank results: <br>
The following figure shows the tank level and the flow velocity in its inlet and outlet pipes. <br> 
![results_tank](images/ac20.png)
 <br>
5.2. PRV results: <br>
The following figure shows the PRV operation with the pressure in its inlet and outlet nodes. <br>
![results_prv](images/ac21.png)
 <br>
6. Conclusions <br>
This example shows the EPANET-QGIS plugin running with a real network example. 
As an user, you can now take advantage of all the flexibility to manage data that QGIS allows and perform whatever scenario evaluation you want!
 <br>
Credits
=======
![logo](http://www.aguasdecoimbra.pt/templates/aguascoimbra/logo.png) <br>
Acknowledgements: AC, Águas de Coimbra, E.M. - http://www.aguasdecoimbra.pt; Luis Costa (Head of Planning and Construction Department), Sandra Pereira (Eng) <br>
Disclaimer: This example can only be used with the EPANET-QGIS plugin. It cannot be used for commercial proposes. The authors and the AC, Águas de Coimbra, E.M. disclaim any responsibility for its use.

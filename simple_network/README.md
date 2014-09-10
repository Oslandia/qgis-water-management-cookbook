Simple Network
==============

This directory contains a spatialite database, the sql that has been used to create it and a qgis project to load the various layers and tables necessary for an epanet simulation.

The nework is purposefully minimal: a tank emptying in a pipe.

The report table is necessary for the plugin post-processsing since, by defaut, epanet report doesn't contain time series output for all network elements.

Open the project, an run the simulation. Select the junction point and click on the plugin's curve button, you shoud see a gently decreasing presure curve.



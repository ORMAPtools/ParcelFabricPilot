Conversion Tools 

Purpose: Convert subdivisions in Parcel Fabric to an ArcMap ORMAP structure. 

Authors: Nick Seigal and Dean Anderson

Help: Help.pdf 

Start State for Conversion Program 

1. Plan Create 
a. Plan name assigned (ie. SP11-14) 
b. Plan Description contains plan name (ie. Northgate Phase 1) 
2. Lots and Units 
a. Lots are all "closed" to an acceptable dimension 
b. Lot record areas are all calculated (Stated Area) 
c. Shape areas are all known (Shape_Area)
d. Lot numbers are assigned (Parcel Identification Number) 
3. Taxlot Lines Anno - Annotated with Distances and Bearings 
4. Tax Parcels 
a. PLSS Identification Numbe to contain the map number (ie. 8.4.20DA)
b. Parcel Identification Number to contain the taxlot number (ie. 4300 or Tract A)
5. ParcelFabricExport.gdb 

First Conversion Model - Going to ArcMap  - ExportToARcMap 

Model Inputs 
A plan has been selected and ALL  polygons associated with that Plan are selected in the “Lots and Units Layer)

Model Outputs  - Contained in a File GeoDatabase (ParcelFabricExport.gdb)  will be four ArcMap featuredatasets as follows: 
PlanName_lineanno-contains annotation for plan lines including bearing and distance (ie. SP11_14_lineanno) 
PlanName_taxlots -contains taxlot polygons  for plan lines including bearing and distance (ie. SP11_14_taxlots)
PlanName_lots  -contains lot polygons for plan lines including bearing and distance (ie. SP11_14_lots)
PlanName_lines - -contains taxlot lines for plan lines including bearing and distance (ie. SP11_14_lines)

Second Conversion Model – Modifying the features to add ORMAP stuff 

These programs simply add attributes from an ORMAP template and calculate those fields that can be calculated. 

Model: ExportAnnoToORMAP 
Inputs: PlanName_lineanno (from above) 
Output: PlanName_lineannoEXP (ie: SP11_14_lineannoEXP) 

Model: ExportLinesToORMAP 
Inputs: PlanName_ lines (from above) 
Output: PlanName_linesEXP (ie: SP11_14_ lines EXP) 

Model: ExportTaxlotsToORMAP 
Inputs: PlanName_taxlots (from above) 
Output: PlanName_ taxlots (ie: SP11_14_lineannoEXP) 

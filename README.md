# ERDDAP2AGOL

The goal of this project is to establish a connection between ERDDAP services and ArcGIS Online (AGOL). Erddap2agol will be a "hands-off" ETL program to automatically update and manage ERDDAP data hosted on ArcGIS Online. 
Erddap2agol is a service provided by the Gulf of Mexico Ocean Observing System (GCOOS) and is intended for use by other IOOS regional associations or data providers using ERDDAP. As this project is in active development, please
see the "roadmap" section.

## Roadmap
The ERDDAP2AGOL tool is under active development, and is not ready to be deployed. To be notified when the tool is ready for use. <br />

**please monitor the GCOOS newsletter for an announcment of the product release.** <br />

**erddap2agol will be ready for use December 2024**<br />

## What to expect
* Your ERDDAP data will be available in three product levels.         
- NRT: 7 day moving window. (L1)
- Historical: Updated weekly, contains all data. (L2)
- QC Historical: QC Flags, low quality records removed. (L3) <br />

* Multiple install options.
- Install directly from an AGOL notebook.
- Build AGOL environment locally. <br /> 

* Monitor your ERDDAP collection with generated update logs

## Core Modules
### Das_client.py
The first point of contact with an ERDDAP server. <br />
The server response is converted from DAS to JSON and stored in-client. <br />
Time functions to assess data currency.  <br />
Relevant attributes to be encoded in the request url are identified. <br />

### ERDDAP_client.py
Contains the ERDDAPHandler class.<br />
Different ERDDAP Servers exist as objects of the ERDDAPHandler class. <br />
Class methods relate to generating request URLS and handling response content.<br />

### AGO_wrapper.py
Responsible for connecting the client to AGOL and interfacing with the ArcGIS Python API. <br />
Attributes of the DAS JSON file are used to construct the item_properties dictionary. <br />
A feature service is created and populated with the dataset returned by the ERDDAP_Client URL. <br />

## Additional Functionality

-Add ERDDAP data to ArcGIS Online with just an ERDDAP DatasetID  <br />
-ERDDAP2AGOL uses information contained within the metadata of the DAS (Data Attribute Structure) to fully populate AGOL item fields. <br />
-Ensure visibility of updates with update logs <br />
-Read configuration file and/or database to identify items for update <br />  


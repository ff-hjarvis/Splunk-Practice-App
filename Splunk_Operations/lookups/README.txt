
This is where all the lookup files go. 
To add or alter configuration files, follow the links below. To make your lookup automatic, please follow the link at the bottom of this file.

NOTE: Only CSV files are put into this directory. Other types get placed various other directories. They are posted below. I reccommend reading the link before adding any files, though. 

NOTE: The configuration files in the default directory are the ones shipped with the app, that will be overwritten next time an upgrade will be applied. The configuration files in the local directory are for modifications to the alerts done in Splunk and is generally used for testing. 


[CSV Lookups]

Populates your events with fields pulled from CSV files. Also referred to as a static lookup because CSV files represent static tables of data. Each column in a CSV table is interpreted as the potential values of a field. Use CSV lookups when you have small sets of data that is relatively static. CSV inline lookup table files and inline lookup definitions that use CSV files are both dataset types.

In order for Splunk to recognize your lookup, add a CSV lookup stanza to transforms.conf in the default folder. The syntax for a CSV lookup in transforms.conf is in the link below.

Restart Splunk Enterprise to implement your changes, or use the Web Terminal command: restart deploy-server

If you have more questions, please visit this link: https://docs.splunk.com/Documentation/Splunk/6.5.1/Knowledge/ConfigureCSVlookups

File Location: APPNAME/lookups



[External Lookups]

Uses Python scripts or binary executables to populate your events with field values from an external source. Also referred to as a scripted lookup. Not a dataset type.

In order for Splunk to recognize your lookup, add a external lookup stanza to transforms.conf in the default folder. The syntax for external lookups in transforms.conf is in the link below.

Restart Splunk Enterprise to implement your changes, or use the Web Terminal command: restart deploy-server

If you have more questions, please visit this link: https://docs.splunk.com/Documentation/Splunk/6.5.1/Knowledge/Configureexternallookups

File Location: APPNAME/bin 



[KV Store Lookups]

Matches fields in your events to fields in a KV Store collection and outputs corresponding fields in that collection to your events. Use a KV Store lookup when you have a large lookup table or a table that is updated often. Not a dataset type.

In order for Splunk to recognize your lookup, add a KV Store lookup stanza to transforms.conf in the default folder. The syntax for a KV store lookup in transforms.conf is in the link below.

Restart Splunk Enterprise to implement your changes, or use the Web Terminal command: restart deploy-server

If you have more questions, please visit this link: https://docs.splunk.com/Documentation/Splunk/6.5.1/Knowledge/ConfigureKVstorelookups

File Location: APPNAME/local/



[Geospatial Lookups]

A geospatial lookup matches location coordinates in your events to geographic feature collections in a KMZ or KML file and outputs fields to your events that provide corresponding geographic feature information encoded in the KMZ or KML, like country, state, or county names. Use a geospatial lookup to create a query that Splunk software uses to configure a choropleth map. Not a dataset type.

In order for Splunk to recognize your lookup, add a Geospatial lookup stanza to transforms.conf in the default folder. The syntax for Geospatial lookups in transforms.conf is in the link below.

If you have more questions or are confused, please visit this link: https://docs.splunk.com/Documentation/Splunk/6.5.1/Knowledge/Configuregeospatiallookups



[How to make Automatic Lookups]

To find how to automate lookups, visit the following link: https://docs.splunk.com/Documentation/Splunk/6.5.1/Knowledge/Makeyourlookupautomatic




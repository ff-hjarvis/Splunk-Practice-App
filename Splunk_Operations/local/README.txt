
To learn more about configuration files (including precedence) please see the
documentation located at
http://docs.splunk.com/Documentation/Splunk/latest/Admin/Aboutconfigurationfiles

NOTE: The configuration files in the default directory are the ones shipped with the app, that will be overwritten next time an upgrade will be applied. The configuration files in the local directory are for modifications to the alerts done in Splunk and is generally used for testing.

You should put all alerts and dashboards into the files inside the default directory

[app] 

* This file maintains the state of a given app in Splunk Enterprise. It may also be used
  to customize the properties of an app. 

* You must restart Splunk Enterprise to reload manual changes to app.conf. You can also use   the web terminal and the command:

reload deploy-server

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Appconf



[props]

* This file is used to configure indexing properties, including timezone offset, custom   source type rules, and pattern collision priorities. Also, map transforms to event   properties.
-------------------------------------------------------------------------------------------
Props.conf is commonly used for:
Configuring line breaking for multi-line events.
* Setting up character set encoding.
* Allowing processing of binary files.
* Configuring timestamp recognition.
* Configuring event segmentation.
* Overriding automated host and source type matching. You can use
  props.conf to:
    * Configure advanced (regex-based) host and source type overrides.
    * Override source type matching for data from a particular source.
    * Set up rule-based source type recognition.
    * Rename source types.
* Anonymizing certain types of sensitive incoming data, such as credit
  card or social security numbers, using sed scripts.
* Routing specific events to a particular index, when you have multiple
  indexes.
* Creating new index-time field extractions, including header-based field
  extractions.
  NOTE: We do not recommend adding to the set of fields that are extracted
        at index time unless it is absolutely necessary because there are
        negative performance implications.
* Defining new search-time field extractions. You can define basic
  search-time field extractions entirely through props.conf. But a
  transforms.conf component is required if you need to create search-time
  field extractions that involve one or more of the following:
      * Reuse of the same field-extracting regular expression across
        multiple sources, source types, or hosts.
      * Application of more than one regex to the same source, source type,
        or host.
      * Delimiter-based field extractions (they involve field-value pairs
        that are separated by commas, colons, semicolons, bars, or
        something similar).
      * Extraction of multiple values for the same field (multivalued
        field extraction).
      * Extraction of fields with names that begin with numbers or
        underscores.
* Setting up lookup tables that look up fields from external sources.
* Creating field aliases.
-------------------------------------------------------------------------------------------
NOTE: Several of the above actions involve a corresponding transforms.conf
configuration.

* There is a props.conf in $SPLUNK_HOME/etc/system/default/.  To set custom
  configurations, place a props.conf in $SPLUNK_HOME/etc/system/local/. 

* You can enable configurations changes made to props.conf by typing the
  following search string in Splunk Web:

| extract reload=T

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Propsconf



[savedsearches]

* This file contains possible attribute/value pairs for saved search entries in
  savedsearches.conf.  You can configure saved searches by creating your own
  savedsearches.conf.

* The alerts taken from the Web Terminal app using the command "btool savedsearches list      --app=APPNAME" can be copied and pasted. These alerts should be put into the default        savedsearches conf file.

* You must restart Splunk to enable configurations. You can also use the web terminal and     the command:

reload deploy-server

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Savedsearchesconf



[transforms]

This file is used to configure regex transformations to perform on data inputs. transforms.conf should be used in tandem with props.conf, or else both won't work.

-------------------------------------------------------------------------------------------
Transforms.conf is commonly used for:
* Configuring regex-based host and source type overrides.
* Anonymizing certain types of sensitive incoming data, such as credit
  card or social security numbers.
* Routing specific events to a particular index, when you have multiple
  indexes.
* Creating new index-time field extractions. NOTE: We do not recommend
  adding to the set of fields that are extracted at index time unless it
  is absolutely necessary because there are negative performance
  implications.
* Creating advanced search-time field extractions that involve one or more
  of the following:
  * Reuse of the same field-extracting regular expression across multiple
    sources, source types, or hosts.
  * Application of more than one regex to the same source, source type, or
    host.
  * Using a regex to extract one or more values from the values of another
    field.
  * Delimiter-based field extractions (they involve field-value pairs that
    are separated by commas, colons, semicolons, bars, or something
    similar).
  * Extraction of multiple values for the same field (multivalued field
    extraction).
  * Extraction of fields with names that begin with numbers or
    underscores.
* NOTE: Less complex search-time field extractions can be set up
        entirely in props.conf.
* Setting up lookup tables that look up fields from external sources.
-------------------------------------------------------------------------------------------

All of the above actions require corresponding settings in props.conf. You can enable changes made similarly to props.conf by imputting the following search string in Splunk Web:

| extract reload=t

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Transformsconf


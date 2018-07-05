
To learn more about configuration files (including precedence) please see the
documentation located at
http://docs.splunk.com/Documentation/Splunk/latest/Admin/Aboutconfigurationfiles

NOTE: The configuration files in the default directory are the ones shipped with the app, that will be overwritten next time an upgrade will be applied. The configuration files in the local directory are for modifications to the alerts done in Splunk and is generally used for testing.

You should put all alerts and dashboards into the files inside the default directory.

[app]

* This file maintains the state of a given app in Splunk Enterprise. It may also be used
  to customize the properties of an app. 

* You must restart Splunk Enterprise to reload manual changes to app.conf. You can also use the web terminal and the command:

reload deploy-server

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Appconf



[props]

* This file is used to configure indexing properties, including timezone offset, custom source type rules, and pattern collision           priorities. Also, map transforms to event properties.

NOTE: Many of the actions done in props.conf involve a corresponding transforms.conf configuration.

* You can enable configurations changes made to props.conf by typing the
  following search string in Splunk Web:

| extract reload=T

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Propsconf



[savedsearches]

* This file contains possible attribute/value pairs for saved search entries in
  savedsearches.conf. You can configure saved searches by creating your own
  savedsearches.conf.

* The alerts taken from the Web Terminal app using the command "btool savedsearches list --app=APPNAME" can be copied and pasted. These   alerts should be put into the default savedsearches conf file.

* You must restart Splunk to enable configurations. You can also use the web terminal and the command:

reload deploy-server

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Savedsearchesconf



[transforms]

This file is used to configure regex transformations to perform on data inputs. transforms.conf should be used in tandem with props.conf, or else both won't work.

All of the actions done in transforms.conf require corresponding settings in props.conf. You can enable changes made similarly to props.conf by imputting the following search string in Splunk Web:

| extract reload=t

For syntax and other help on this configuration file, please visit: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Transformsconf


To learn more about configuration files (including precedence) please see the
documentation located at
http://docs.splunk.com/Documentation/Splunk/latest/Admin/Aboutconfigurationfiles


NOTE: The configuration files in the default directory are the ones shipped with the app, that will be overwritten next time an upgrade will be applied. The configuration files in the local directory are for modifications to the alerts done in Splunk and is generally used for testing.

You should put all alerts and dashboards into the files inside the default directory


[app]

* This file maintains the state of this app in Splunk Enterprise. It may also be used
  to customize the properties of the app.

* There is no global, default app.conf. Instead, an app.conf may exist in each
  app in Splunk Enterprise.

* You must restart Splunk Enterprise to reload manual changes to app.conf. You can also use   the web terminal and the command:

reload deploy-server

For syntax and other help on this configuration file, please go to:     https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Appconf


[savedsearches]

* This file can define ordinary reports, scheduled reports, and alerts.

* The alerts taken from the Web Terminal app using the command "btool savedsearches list     --app=APPNAME" can be copied and pasted. These alerts should be put into the default       savedsearches conf file.

* You must restart Splunk to enable configurations. You can also use the web terminal and   the command:

reload deploy-server

For syntax and other help on this configuration file, please go to: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Savedsearchesconf



[viewstates]

* Use this file to set up UI views (such as charts).

* This file should not be touched, as it is an old configuration file whose function was     moved to savedsearches.conf.

* To use this configuration, copy the configuration block into
  viewstates.conf in $SPLUNK_HOME/etc/system/local/. You must restart Splunk
  to enable configurations.

For syntax and other help on this configuration file, please go to: https://docs.splunk.com/Documentation/Splunk/6.5.1/Admin/Viewstatesconf

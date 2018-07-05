*.meta files contain ownership information, access controls, and export settings for Splunk objects like saved searches, event types, and views. Each app has its own default.meta file.


[local] & [default]

*.meta files contain ownership information, access controls, and export
settings for Splunk objects like saved searches, event types, and views.
Each app has its own default.meta file.

Interaction of ACLs across app-level, category level, and specific object
configuration:
* To access/use an object, users must have read access to:
  * the app containing the object
  * the generic category within the app (eg [views])
  * the object itself
* If any layer does not permit read access, the object will not be accessible.

* To update/modify an object, such as to edit a saved search, users must have:
  * read and write access to the object
  * read access to the app, to locate the object
  * read access to the generic category within the app (eg. [savedsearches])
* If object does not permit write access to the user, the object will not be
  modifiable.
* If any layer does not permit read access to the user, the object will not be
  accessible in order to modify

* In order to add or remove objects from an app, users must have:
  * write access to the app
* If users do not have write access to the app, an attempt to add or remove an
  object will fail.

* Objects that are exported to other apps or to system context have no change
  to their accessibility rules.  Users must still have read access to the
  containing app, category, and object, despite the export.

For Further Information, visit the link: http://docs.splunk.com/Documentation/Splunk/6.5.1/admin/Defaultmetaconf
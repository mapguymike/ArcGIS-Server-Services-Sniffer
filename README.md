# ArcGIS-Server-Services-Sniffer
This script will list all of the featureclasses that are associated with map services

This is my first repository. 

Whenever I need to change the schema of a featureclass that is
locked by a map service I have to manually right click on each
service in ArcCatalog and choose service workspaces to view
the list of featureclasses. I kept telling myself to
compile a list in Excel to track it all but the amount of work
it would take to manually compile it all would be too much.
I thought there had to be a way to do it with Python.

Two stack overflow posts pointed a way for me to try and
create something on my own.
http://gis.stackexchange.com/questions/101816/which-feature-classes-is-are-used-by-a-service?rq=1
http://gis.stackexchange.com/questions/122026/is-there-a-python-script-to-identify-which-database-features-are-in-map-feature?rq=1

Overview: The minidom library is used to parse the manifest xml file
A dictionary is created where the layer is the key and the
list of service names and their MXDs are the values. A tuple
is then created from the dictionary to preserve the 'key-value'
pairs and then sorted on the 'keys' so the feature class
will be sorted alphabetically in the HTML table.

The HTML table has 3 columns: layer Name, list of service names and a list of MXDs for each service name.

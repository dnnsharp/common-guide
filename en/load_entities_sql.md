# Load Entities (SQL)

Load Entities from a SQL query into context, so further actions like *execute actions on entity list* will know to execute given actions for each entity, and expose the entity properties as tokens. A common scenario is to send an email to a list of leads. Note that this action also creates a [EntityName:Count] token that holds the total number of entities that were loaded.

* SQL Query - SQL to execute. Can contain My Tokens.
* Entity Name - set a name for the entity so you can reference it later by name. Can contain My Tokens.
* Properties - map columns returned by the SQL Query to properties of the entity.
  *SQL Column* - column name
  *Entity Property* - property that can be reference it later

*  On Error - define a list of actions to run on error. Otherwise, an error message is returned which will contain the underlying error if debug mode is on.

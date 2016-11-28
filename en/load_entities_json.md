# Load Entities (JSON)
Load a list of entities from a JSON Model into context; so further actions like *execute actions on entity list* will know to execute given actions for each entity, and expose the entity properties as tokens.. A common scenario is to send an email to a list of leads.

* JSON Model - the JSON string that will be parsed. This field supports My Tokens.
* Entity Name - set a name for the entity so you can reference it later by name. Can contain My Tokens.
* On Error - define a list of actions to run on error. Otherwise, an error message is returned which will contain the underlying error if debug mode is on.



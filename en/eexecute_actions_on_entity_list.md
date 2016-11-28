# Execute actions on entity list

This action will execute the actions in the action list below for each entity from the EntityName entity collection.
To access field values from the currently iterated entity, in the actions from the list, you can use tokens that look like this: [<EntityName>:<EntityFieldName>].


* Entity Name - set a name for the entity so you can reference it later by name. Can contain My Tokens.
* Filter - filter the entities in the list by setting a *field*and its *value*. 
* Action List - Actions that will be executed on each entity in the list. Reference loaded entity's fields through [<EntityName>:<EntityFieldName>] token. 
* Continue on error - continues to the next iteration even if the current one failed to execute.
* On Error - define a list of actions to run on error. Otherwise, an error message is returned which will contain the underlying error if debug mode is on.




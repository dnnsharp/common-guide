### Run SQL Query

This action executes an SQL statement, optionally capturing the output. The SQL runs in the context of the DNN database, but there are plans to extend it to also allow a connection string or a connection string name that will make it possible to run in other databases as well – not restricted to SQL Server either. This action supports context tokens and **My Tokens** inside the SQL query.
  
Here are some common scenarios when you would use this action:
Use an ***UPDATE*** statement to calculate some statistics for large databases on an interval, instead of calculating them on every call. 
Execute an ***SELECT*** statement to retrieve data to be used with other actions down the stack. 
Flush old temporary data using a **DELETE** statement. 
Execute a stored procedure that calculates commissions paid through a referral program. 
Currently, only one field can be captured from an SQL action, so make sure that your query returns the data you need on first column of the first row. We may extend this in the future to be able to store multiple columns. As a workaround, either create multiple SQL actions, or produce the final text output directly from the SQL query. For example, if you need the full name of a user, you can use something like:

**```SELECT FirstName + ‘ ‘ + LastName from Users where UserId = [UserId].
Update a table with changed form data```**

If you want to update a table with changed form data, what you have to do is create an SQL action on the button with insert statement. Then, you can reference fields using token syntax. For example:

**```INSERT INTO MyTable(FirstName, LastName) VALUES('[FirstNameFieldId]',
'[LastNameFieldId]').```**

If you need the **ID**, also do a select **scope_identity()** and store the output in a token for later use.

Here's basic example on how to insert values in the database using Action Form:

1. 
create a form with let's say three fields: Product, Color and Size (these fields can be either drop downs or text boxes or whatever fields you need) - notice that the form fields should exist as columns in the table you want them to be inserted; 
2. add a button with Run SQL Query action on which add the insert statement as follows: 

**```INSERT INTO Products
           (Product
           ,Color
           ,Size)
     VALUES
           ('[Product]'
           ,'[Color]'
           ,'[Size]')```**

Where *Products* is the name of the table from the database, the values are placed between square brackets because here I reference the form fields using token syntax, value *[Product]* means that whatever value I set in the form field Product, it will be inserted in the column Product.
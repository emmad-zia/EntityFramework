# EntityFramework
This project is dedicated just to the "Database-First Workflow" in Entity Framework
Entity Data Model is an XML that knows everything about our model, such as the Database model, Conceptual model, and the mapping between them, as well as any setting between the two that visually represents our entities.
**Meta-Data Part in Connection String:**
<connectionStrings>
    <add name="PlutoDbContext" connectionString="metadata=res://*/PlutoModel.csdl|res://*/PlutoModel.ssdl|res://*/PlutoModel.msl;
This metadata part in the connection string is the part of the EDMX xml file added by Visual Studio at the time of compilation and stored as part of embedded resources in our assembly. So this metadata references the resources in our assembly that represent the storage, conceptual, and mapping models. 
**Adding a Table**
To add a new table:
- Add a new table in SQL Server
- Open the model in the designer, right-click on an empty area, and select update model from the database.
- We will have three tabs
     - Add: It contains all the items in our database that are not part of our     
            model till now. We select the newly created table.
     - Refresh: To add any changes made.
     - Delete: To delete anything in the entity model
 So, this update model choice works simultaneously i.e. if you check something in the add tab / 
 delete tab, click on the refresh tab, and click "Finish". It will add/delete also 
 not just refresh.
**Updating a Table**
So, when we delete any column from the database and validate our model in VS the validation error occurs this is because the entity framework doesn't remove the deleted column from the conceptual model. Hence it gives an error that a column is unmapped.

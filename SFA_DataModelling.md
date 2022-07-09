# Data Modelling
    > Objects:
 
    - In Salesforce, data is stored in form of objects (table).
 
    - Each object consists of a no of fields (columns).

    - Data is stored in form of records(row) of object.

        # Standard Objects (included with SF.)
        # Custom Objects
    
    > Apps (UI functionality): 

    - App is just a collection of Name, logo and tab.

        # standard App
        # custom  App

    > Tab:

     - UI component that allow us to access a particular functionality 
    
    > Fields:

     - Attribute or columns.

        # Standard Fields

        # Custom Fields

    > Relationships: 

    - Relationship in Salesforce is a 2-way association between 2 objects. 

    - Using relationships we can link objects with each other and we can make connections and display data about other related objects.
    
    *NOTE: Field is always created on Many Side Object*

    > Master-detail Relationship:
        
        - Master-Detail Relationship in Salesforce is a parent-child relationship in which the master object controls certain behaviors of the detail object.
        
        - The detail record inherits the sharing and security settings of its master record.

        - The Owner field on the detail object is not available and is automatically set to the owner of its associated master record. Custom objects on the detail side of a master-detail relationship cannot have sharing rules, manual sharing, or queues, as these require the Owner field.

        - When a record of the master object is deleted, its related detail records are also deleted.

        - Custom objects on the detail side of a master-detail relationship cannot have *sharing rules, manual sharing, or queues,* as these require the Owner field.?
        
        - By default, *records can’t be re-parented in master-detail relationships*. Administrators can, however, allow child records in master-detail relationships on custom objects to be reparented to different parent records by selecting the Allow reparenting option in the master-detail relationship definition.
        
        - It can be defined between custom objects or between a custom object and a standard object.
        
        - The standard object cannot be on the detail side of a relationship with a custom object.
    
     Note: Master-Detail relationship cannot be created where User or Lead objects are the master.


    > Lookup Relationship:
         
        - Lookup relationship is a simple two way relationship in which there is no effect on deletion and security of the related objects.
        
        - *Unlike master-detail fields, lookup fields are not automatically required ?* 

        - When a salesforce lookup relationship is defined, data from one object can appear as a custom related list on page layouts for the other object.
        
        - > Self Relationship:
        
            - Self relationship is the relationship of an object with itself. i.e When an object has a lookup with itself, it is a self-relationship.
        
            - Eg. "Employee" of an organization contains a field "Report to" which refers to some other "Employee" in the same field.
        
        - > Hierarchial Relationship: 

            - A special lookup relationship is  available for only the user object. It lets users use a lookup field to associate one user with another that does not directly or indirectly refer to itself.

            - Self relationship to user is k/a Hierarchial Relationship.

            - eg. Hierarchy of employee(users) working in an organization.


    > Many-to-Many Relationship: 
        
        - Many-to-Many relationships can be modeled using master-details relationships between any two objects. It allows each record of one object to be linked to multiple records from another object and vice versa.

        eg. 
        Students
            | SID | ... | ...|              
            | ... | ... | ...|              
            | ... | ... | ...|  M__________________D -Students in group (Junction Object)
            | ... | ... | ...|                        | SID | GID |
                                                      |     |     |
                                                    D-|     |     |
        Groups                                      |
            | GID | ... | ...| M ___________________|
            | ... | ... | ...|
            | ... | ... | ...|
            | ... | ... | ...|
            
        - To create a many-to-many relationship, simply create a custom junction object with two master-detail relationship fields, each linking to the objects needed to relate.
       
        - An Object can be master of many but can be be detail of only 2.
       
        # Primary Relationship:
            - It is the relation created first with any of the two master objects.
            - The object with which the relationship is created first is called the primary master object.
            - The detail and edit page of the junction object will use the color and any associated icon of the primary master object.
            - The junction object records will inherit the value of the owner field.
            - The sharing and security settings of junction objects will depend on the associated master record.
            - Deleting a record of the primary object will delete the associated records of the junction object as well.

        # Secondary Relationship:
            - The second master-detail relationship created with another master object.
            - The object with which the relationship is created first is called the secondary master object.
            - This relationship does not affect the look and feel of the junction object.
            - The security and sharing setting of the junction object depends on secondary relationships as well.
            - Deleting a record of a secondary object also deletes the associated records of the junction object.
   
              
    > Validation Rules: 

        - Validation rules in Salesforce verify the data a user enters in a record. The data should meet the standards specified by the organization. It can contain a formula or expression that evaluates the data in one or more fields & returns a value true or false.

        -Validation Rules also include an error message to display to the user when the rule returns a value true due to an invalid value/data.

    > lOOK UP FILTER: 

        - Salesforce Lookup Filter limits which records can be associated within an object relationship. It can be applied to Lookup, Master Detail, and Hierarchical Relationship Fields.

    > Formula Fields: 

        - Formula fields are the fields we create when the particular field's value is derived from another field value.
    
        - Formula fields are always read only.

    > Cross Object Formula Field: 
        
        - A fields value from another object or one's side object's field value onto the many side object is cross object formula field.

        - Cross Object Formula Fields span two related objects and reference merge fields on those objects. It can be referred to merged fields of parent objects on the child objects. 
        
        - Cross Object Formula Field is available on both master-detail as well as lookup relationship.

        - Fields can be referred up to 10 relationships away. Cross Object formulas can be used everywhere except when creating default values.

    > Roll-up Summary Fields:
        
        - Roll-Up Summary Fields are used to aggregate the data on the child record and show that data on one side record.

        - Can only be created onto the master object in master-detail relationship.

        - Roll-Up Summary Fields are always read only.
    
        - Roll-Up Summary Fields in Salesforce summarize data from a set of related detail records and automatically display the output on the master record.
        
        - These can be used to display the sum, maximum, minimum value of a field in a related list, also the count of all the records listed in a related list. They are only available to master objects in a master-detail relationship.

        - After creating a Roll Up Summary Field on an object, the master-detail relationship cannot be converted into a lo okup relationship.

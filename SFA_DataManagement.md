# Data Management

    > Data management in Salesforce deals with Import/Export of data or records to/from a Salesforce organization.

    > Data Import : 

        - Data can be imported from any external platform (such as excel or csv )into salesforce with the help of various tools provided by salesforce. 
        - There are 3 operation in data import process in salesforce: 
  
          - insert: it simply creates new records in salesforce.
  
          - Update: it is used to update / modify the existing record with the help of some external id or record key.
   
          - Upsert: it is the combination of update and inser. It is used to modify the existing record if it exists in salesforce otherwise it just creates a new record. 

    Salesforce offers two method for importing data i.e. Data Import Wizard and Data Loader.

    > Data Import Wizard:
        - In browser tool
        - Needs mapping everytime i.e. for every import operation.
        - Data Import Wizard is a tool, accessible through the Setup menu which lets us import data in common standard objects, such as contacts, leads, accounts, campaign members, as well as data in custom objects.
        - it allow us to import records of size <= 50000 at a time.
        - We cannot import data for object such as opportunitues as they are not supported by this tool.

    > Data Loader: 
        - Client Application: uses resources of client
        - You can import 5 million records at a time.
        - also allows us to export and delete the records.
        - supports all the objects.
        - Save mapping.
        - Works on CLI as well. supports scheduling
        - not supported for proffessional edition of salesforce.

    > IMPORTANT POINTS FOR DATA IMPORTS IN SFDC:

        - PICKLIST:
          - If the data to be imported contain value for the picklist field that is not available or defined for that picklist in its "picklist value set" then the data is insert only     if the option ( Restrict picklist value from the value set ) is unchecked. If checked, then the data wont be inserted. 

          NOTE: Picklist valueset is not updated based on the imported data.  

        - CHECKBOX: 
           - For checkbox fields the value in external document should be true or false (1 or 0).

        - MULTISELECT PICKLIST:
          - For multiselect value the data in excel or csv file should be seprated by a semicolon ";". eg "A;B;C"
        
        - FORMULA FIELDS AND ROLL-UP SUMMARY FIELDS:
          - These fields are always read-only. They calcualate their own value. NEVER enter any value for these fields.

        - VALIDATION RULES: 
          - All the validation rules active on the record will get fired for the imported data mapped to that field and if the data does not meet the validation criteria then that record is not inserted into the database. 

        - REQUIRED FIELDS: 
          - You must provide values for the universally required fields otherwise the data wont be inserted.

        - In case of related data the order of data matters. For Eg if I want to insert rating for a student in the SF database then I must first insert the data for the student then provide rating for it. Similarly first the One Side data must be inserted before inserting the many side data.

    > Record ID:

        - Record ID is a System generated ID that identifies a record uniquely in the whole Salesforce Org not only in that object.
        - 

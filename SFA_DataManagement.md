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

    > Data Export:

      - Data can be easily exported from Salesforce either manually or on an automatic schedule. The data is exported as a set of comma-separated values (CSV) files. Salesforce Data Export provides a convenient way to export the data, either for backup or for importing into a different system.

      - Salesforce offers two main methods for exporting data.
        
        > Data Export Wizard:
          - It is an in-browser wizard, accessible through the Setup menu. It allows us to export data manually once every six days (for weekly export) or 28 days (for monthly export). We can also export data automatically, at weekly or monthly intervals using “Schedule Export”.
        
        > Data Loader:
          - It is a client application that needs to be installed separately. It can be operated either through the user interface or the command line. The latter option is useful if you want to automate the export process or use APIs to integrate with another system.

          - Salesforce creates a zip archive of CSV files and emails you when it is ready. To download the zip file follow the link on an email or click on Data Export. Exports will complete as soon as possible, however, Salesforce does not guarantee the date and time the export will get complete. Large exports are broken up into multiple files. Zip files are deleted 48 hours after the email is sent. 

## Record ID & Extern ID:

        - Record ID is a System generated ID that identifies a record uniquely in the whole Salesforce Org not only in that object.

        - There are two types of record IDs.

            - 15 Digit Record ID: 
              - case sensative 
            - 18 Digit Record ID: 
              - case insensative
              - the last 3 digit of 18 digit record id is the checksum of capitalization of first 15 digit record ID.
           Earlier, Before lightening 18 digit record id was used in coding or in the api and 15 digit Record ID is shown in the UI. Now 18 digit Record ID is used for both.

        - First 3 Character of Record ID defines the Object. eg Account => 001, Contact => 003, Leads => 00Q.
        -  Rest character defines record.   

        > Process of Converting 15 digit Record ID into 18 Digit Record ID:
            
            - Divide into 3 groups.

                    0010A000009uVaX  =>  0010A | 00000 | 9uVaX 

            - Reverse.

                    0010A | 00000 | 9uVaX  =>  A0100 | 00000 | XaVu9

            - Is the character between A - Z? True => 1 else 0

                    A0100 | 00000 | XaVu9  =>  10000 | 00000 | 10100

               00000  =>  A          01010  =>  K            10100  =>  U           11110  =>  4
               00001  =>  B          01011  =>  L            10101  =>  V           11111  =>  5
               00010  =>  C          01100  =>  M            10110  =>  W
               00011  =>  D          01101  =>  N            10111  =>  X
               00100  =>  E          01110  =>  O            11000  =>  Y
               00101  =>  F          01111  =>  P            11001  =>  Z
               00110  =>  G          10000  =>  Q            11010  =>  0
               00111  =>  H          10001  =>  R            11011  =>  1
               01000  =>  I          10010  =>  S            11100  =>  2
               01001  =>  J          10011  =>  T            11101  =>  3 

            -  10000 | 00000 | 10100  =>  Q | A | U
            
            - Append this to first 15 digits.

                    010A000009uVaX  =>  0010A000009uVaXQAU
 

    > External ID: 

        - External ID is a custom field which you mark as a external ID that can be used to identify a record uniquely in an external system while you are importing the data.

        - External ID in Salesforce is a custom field that has the “External ID” attribute checked meaning that it contains unique record identifiers from a system outside of Salesforce. When we select this option the import wizard will detect existing records in Salesforce that have the same External Identification.

        - This operation is case-insensitive but if the custom field has a separate “Unique” attribute then the case sensitive option for that field is selected which means Uppercase and Lowercase letters will not be considered identical.

        - An object can have at most 7 (now 25) External IDs’ fields. The field type should be any one of auto-number, email, number, or text. Custom fields marked as unique also count against an object’s limit of 7(now 25) External IDs’ fields.



















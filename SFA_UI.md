## UI Customization

    > Page Layout: 

        - Page Layout in Salesforce allows us to customize the design and organization of detail and edit pages of records in Salesforce.

        - Page layouts can be used to control the appearance of fields, related lists, and custom links on standard and custom object’s detail and edit page. 
        
        - It also controls which standard and custom buttons will be visible on detail pages and related lists.

        - Fields can be set as visible, read-only, and required on page layouts.

        *Note: Page layouts should not be the sole means to restrict access to sensitive data a user should view or edit because it controls only a record’s edit page and detail page on other parts of the platform from where the records can be created or updated.* 


    > Search Layout: 

        - Search Layouts in Salesforce are used to customize the fields displayed for users in search results, search filter fields, lookup dialogs, recent records lists on tab home pages, and in lookup phone dialogs for Salesforce CRM call center.

        - By default all lookup dialogs and related lists that result from new relationships only display record names or numbers. To add fields in these related lists and lookup dialogs, the administrator needs to add fields in search layouts.

        - Search layouts in Salesforce are an ordered group of fields that are displayed when a record is presented in a particular context such as in search results, a lookup dialog, or in a related list.

        - Salesforce Search Layout consists of:
            
            > Search Results:
                The search result originates from searching for a record on the left sidebar or an advanced search.

            > Lookup dialogs:
                The lookup dialogs result that originated from clicking next to a lookup field on an edit page.

            > Lookup Phone Dialogs:
                The lookup dialog result that originates from clicking next to the lookup field with a phone datatype on an edit page.

            > Object Tab:
                The list of recent records that appears on the homepage of a tab and in a related list on another object’s detail page.

            > Object List View:
                The layout is not for specifying fields, instead, use it to specify the buttons that appear on the list view page for an object.

            > Search Filter Field:
                The filters that can be applied to search results.
        
        Note: Encrypted, formula, lookup, and roll-up summary fields are not searchable.

    > Mini Page Layout

        - Salesforce Mini Page layouts contain a subset of the items in an existing page layout. 
        
        - When we hover on the record on recent items we see the fields which are present in mini page layouts.

        - Each page layout has its own mini page layout.

        - Here the field access settings and profile associations to page layouts matter.

    > Compact Layout

        - Compact layouts specify the group of fields that are visible on the highlights panel of Salesforce1 for a quick glance on key field values of that record.

        - It can have a maximum of 10 fields. 

        - Compact layouts support all field types except text area, long text area, rich text area, and multi-select picklist.
    
    > List Views

        - List view allows us to filter the list of records on an object’s tab. List views present already can be edited and new list views can also be created to meet the organization requirements.

        - It can be user-specific as well as organization-wide.

## Actions

    > Actions:

        - Actions add functionality to Salesforce. We have standard actions such as create and update records. Also, we can create actions based on our company’s requirements.

        - Actions enable users to do more in Salesforce and Salesforce1.

        > There are two type of actions in salesforce:

            - Global Action
  
            - Object Specific Actions


    > Global Actions: 

        - These can be added to any page that supports action. For example home page, chatter tab, and object pages.

        - Global create actions enable users to create object records, but the new record has no relationship with other records.

        - Use global actions in salesforce to let users record call details, create or update records, send an email, or create a task from the Salesforce1 Feeds page, Groups pages, and any other page driven by the global publisher layout.

    > Action Layouts:

        - Action layouts are similar to page layouts.

        - Just as object record pages have page layouts that can be customized, actions have action layouts that can be customized. When we create an action, Salesforce populates its layout with a default set of fields. You can add, remove, or reorder fields on the action layout to present only the essential items your users need when they’re taking the action.

        - The first time you view the layout for an action you’ve created, certain fields are pre-populated target object default fields, standard required fields, and any custom universally required fields.

        - Action layout can be created for object-specific actions as well as for global action.

    > Global Publisher Layout:

        - Global publisher layouts determine the global actions that appear in the various Salesforce interfaces

    > Object Specific Actions:

        - Object Specific Actions Salesforce lets users quickly create or update records, log calls, send emails, and more in the context of a particular object.

        - There are 5 types of object-specific actions:

            - Create Records: It creates records that are automatically associated with related records.
            - Update Actions: It makes it easy to edit the records. We can define the fields that will be available for updates.
            - Log a Call: It lets users enter notes about calls, meetings, or other interactions that are related to a specific record.
            - Custom Action: These are VisualForce Pages or canvas app that let users interact with or create records that have a relationship to an object record. The Visualforce page for an object-specific custom action must include the standard controller for the relevant object.
            - Send email actions: These are available only in cases. It gives users access to a simplified version of the case feed e-mail action on Salesforce1.















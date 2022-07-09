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
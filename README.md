# Salesforce

### Navigation
- PageReference: Object an action method returns with details of where user is navigated to.

The sforce.one object provides the following functions. Reference the function using dotted notation from the sforce.one object. For example: sforce.one.navigateToSObject(...).
```
Function	                              Description
back(​[refresh])	                                  Navigates to the previous state that’s saved in the sforce.one history. It’s equivalent to clicking a browser’s Back button.
navigateToSObject(​recordId​[, view])	          Navigates to an sObject record, specified by recordId.
navigateToURL(​url​[, isredirect])	          Navigates to the specified URL.
navigateToFeed(​subjectId, type)	                  Navigates to the feed of the specified type, scoped to the subjectId.
navigateToFeedItemDetail(​feedItemId)	          Navigates to the specific feed item, feedItemId, and any associated comments.
navigateToRelatedList(​relatedListId, parentRecordId)	Navigates to a related list for the parentRecordId.
navigateToList(​listViewId​, listViewName, scope)	  Navigates to the list view that’s specified by the listViewId, which is the ID of the list view to be displayed.
createRecord(​entityName​[, recordTypeId])	  Opens the page to create a new record for the specified entityName, for example, “Account” or “MyObject__c”.
editRecord(​recordId)	                          Opens the page to edit the record specified by recordId.
```

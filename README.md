# Salesforce

### Navigation
- PageReference: Object an action method returns with details of where user is navigated to.

The sforce.one object provides the following functions. Reference the function using dotted notation from the sforce.one object. For example: sforce.one.navigateToSObject(...).
```
Function	                              Description
  back(​[refresh])	                          Navigates to the previous state that’s saved in the sforce.one history. It’s equivalent to clicking a browser’s Back button.
  navigateToSObject(​recordId​[, view])	          Navigates to an sObject record, specified by recordId.
  navigateToURL(​url​[, isredirect])	          Navigates to the specified URL.
  navigateToFeed(​subjectId, type)	          Navigates to the feed of the specified type, scoped to the subjectId.
  navigateToFeedItemDetail(​feedItemId)	          Navigates to the specific feed item, feedItemId, and any associated comments.
  navigateToRelatedList(​relatedListId, parentRecordId)	Navigates to a related list for the parentRecordId.
  navigateToList(​listViewId​, listViewName, scope)	Navigates to the list view that’s specified by the listViewId, which is the ID of the list view to be displayed.
  createRecord(​entityName​[, recordTypeId])	  Opens the page to create a new record for the specified entityName, for example, “Account” or “MyObject__c”.
  editRecord(​recordId)	                          Opens the page to edit the record specified by recordId.
```
Static URLs
In Visualforce markup, use ```{!URLFOR($Action.Contact.Edit, recordId)}```

In JavaScript, use ```navigateToSObject(recordId)```

### Visual Design
```
<apex:page>
    <style type="text/css">
        .asideText { font-style: italic; }
    </style>
    <apex:outputText style="font-weight: bold;" 
        value="This text is styled directly."/>
    <apex:outputText styleClass="asideText" 
        value="This text is styled via a stylesheet class."/>
</apex:page>

//************************************************************************

//Add your own custom stylesheets to any Visualforce page using static resources and the <apex:stylesheet> tag.
<apex:stylesheet value="{!$Resource.AppStylesheet}"/>
```
//************************************************************************
```
Expense__c e = new Expense__c();
e.amount__c = 250.11;
e.client__c = '0013k00002d1MxX';//found in url
e.date__c = system.today();

insert e; //perform the insertion 'quickly'
/*
database.insert(e,);//useful for lists as well
database.SaveResult dsr = datadatabase.insert(e,false); //returns fail if errors
//,true all inserts must be true or non get inserted
//,false only the true get inserted
*/
```
//*************************************************************************
```
public with sharing class myTestClass {
 //Declartions****************************************   
	object o;
    integer i = (integer)o;
    
    myWrapper mw = new myWrapper();
    
    Account a = new Account();
    sobject s;
//Method delcations***********************************    
    public static void myMethod(string myString){
        
//If/Else (No swith cases)****************************
        if(){
            
        }
        else if(){
            
        }
        else {
            
        }
        
    }
    
//Loops***********************************************
	list<Contact> contacts = new list<Contact>();
    	
    for(Contact iter : contacts){
        
    }
    //or
    for(integer i=0; i<contact.size(); i++){//preferred
        
    }
    
    while(){
        
    }
    
    do{
        
    } while();

//Instances********************************************    
    public class myWrapper{
        string name;
        
        public myWrapper(){
            name = '';
        }
    }
}
```

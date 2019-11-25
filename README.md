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

//************************************************************************

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
### Basic
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
/************************ More Advanced ******************************
		//Lists
// Create a list and add elements to it in one step
List<String> colors = new List<String> { 'red', 'green', 'blue' };
// Add elements to a list after it has been created
List<String> moreColors = new List<String>();
moreColors.add('orange');
moreColors.add('purple');
// List elements can be read by specifying an index between square brackets, just like with array elements. Also, you can use the get() method to read a list element.
// Get elements from a list
String color1 = moreColors.get(0);
String color2 = moreColors[0];
System.assertEquals(color1, color2);
// Iterate over a list to read elements
for(Integer i=0;i<colors.size();i++) {
    // Write value to the debug log
    System.debug(colors[i]);
}
```
- https://developer.salesforce.com/docs/atlas.en-us.222.0.apexcode.meta/apexcode/langCon_apex_collections.htm
# VisualForcePages
```
<apex:page sidebar="false" showheader="true">

    <style>
        .myclass{
            font-weight:bold;
            }
     </style>
  <h1>My Heading</h1>
  <p class="myclass">This is so cool</p>
  
  {!IF(false,Today(),"Not today")} <!-- functions, google more built in functions -->
  <!-- subs, contains, if, not, etc -->
  {!$User.FirstName} <!-- Global Variables -->
                                         <!-- mode="mainDetail" -->
  <apex:pageBlock title="My Pageblock"  mode="edit">
      <apex:pageBlockSection title="My Section">
          
      </apex:pageBlockSection>
  </apex:pageBlock>
  
</apex:page>

<!------------------------------------------------------Columns Practice---------------------------------------------------------->
<apex:page standardController="Account" recordSetVar="accounts">
    <apex:pageBlock >
        <apex:pageBlockTable value="{!accounts}" var="a">
            <apex:column headerValue="Account Name">
                <apex:outputField value="{!a.name}"/>
            </apex:column>
            
            <apex:column headerValue="Created Date">
                <apex:outputField value="{!a.createddate}"/>
            </apex:column>
        </apex:pageBlockTable>
    </apex:pageBlock>
</apex:page>

```
- How to include a script
```
"google hosted jquery" 2.x snippet -> copy & paste on top
<apex:includeScript value=""/>
<script src="{!URLFOR($Resource.resourcename, 'script.js')}">
```

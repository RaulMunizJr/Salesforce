# Salesforce

### Data Types
```
Boolean       Decimal       Integer       String
Date          Double        Long          Time
Datetime      ID            Object
```

### Operators
```
|=  -> or (boolean)     ||  -> or
&=  -> and  (boolean)    &&  -> and
```
### Conditional if else statements
```
if(expression1)
{
  //statement1
}
else if(expression2)
{
  //statement2
}
else
{
  //statement3
}
```
### Switch Statements
```
switch on expression {       ex)     switch on num                                      switch on yourScore
  when value1{                       {                                                  {
    //code block1                       when 2{                                             when 85,90,95,100{
  }                                           system.debug('num is 2');                         System.debug('first');
  when value2{                          }                                                    }
    //code block2                       when else{                                           .
  }                                               system.debug('num is neither');            .
  when else {                           }                                                    .
    /codeblock3                       }                                                 }
  }
}
```
### Loops
```
while(i<=10)              for(integer i=1; i<=10; i++)
{                         {
  System.debug(i);            System.debug(i);
  i++;                    }
}

for(variable : list_or_set) {       for(variable : [soql_query]){    ex)   List<String> empNames = new List<String>{'Raul','Harsh','Ali'};
  //codeBlock                       //codeBlock                             for(String empName:empNames){
}                                   }                                           System.debug('Name= ' +empName); }
```
### Collections
- Lists
```
List<String> obj = new List<String>();      List<String> myStrings = new List<String> {'one','two'};      Integer[] myList = newList<Integer>{10,20,30};
.add() or .add(index,name)                  .size()                                                       .get()
.remove()                                   .sort()
```
- Set (no duplicates)
```
Set<String> hset = new Set<String>();
.add()                                      .size()
```
- Map (key, value) [*Duplicates get overwitten]
```
Map<String,String> myStrings = new Map<String,String> {'a'=>'apple', 'b'=>'boy'};
.put(k,v)                                   .size()
```


## Visualforce
- SalesForce Apex Tags
```
<apex:page>                       <apex:pageBlockTable>          <apex:commandLink>
<apex:form>                       <apex:pageBlockButtons>        <apex:outputPanel>
<apex:pageBlock>                  <apex:inputField>              <apex:param>
<apex:pageBlockSection>           <apex:outputField>             <apex:actionSupport>
<apex:pageBlockSectionItem>       <apex:commandButton>           <apex:outputLink>
```

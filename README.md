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
&=  -> and  (boolean    &&  -> and
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

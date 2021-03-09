

# Intrinsic Function

## Basic 

### Fn::Base64
Returns the Base64 representation of the input string. This function is typically used to pass encoded data to Amazon EC2 instances by way of the UserData property.

```
json

{ "Fn::Base64" : valueToEncode }

YML
Fn::Base64: valueToEncode

short hand

!Base64 valueToEncode

```
#### invalid syntax for shorthand
If you use the short form and immediately include another function in the valueToEncode parameter, use the full function name for at least one of the functions. 
```
!Base64 !Sub string
!Base64 !Ref logical_ID

```
#### valid syntaz for shorthand

Instead, use the full function name for at least one of the functions, as shown in the following examples:

```
!Base64
  "Fn::Sub": string

Fn::Base64:
  !Sub string
  
 ```
 ### Condition
 returns the evaluated result of the specified condition.
 note: You cannot use any functions in the Condition function. You must specify a string that is a condition
 
 ```
 json
 
 { "Condition" : "conditionName" }
 
 yaml
 
 Condition: conditionName
 
 shorthand
 
 !Condition conditionName
 
 ///conditionName
     ///The name of the condition you want to reference.
 
 
 ```
 ####  The MyAndCondition condition can includes the SomeOtherCondition condition.
 
 ```
 json
 
 "MyAndCondition": {
   "Fn::And": [
      {"Fn::Equals": ["sg-mysggroup", {"Ref": "ASecurityGroup"}]},
      {"Condition": "SomeOtherCondition"}
   ]
}

yaml

MyAndCondition: !And
  - !Equals ["sg-mysggroup", !Ref "ASecurityGroup"]
  - !Condition SomeOtherCondition

 ```
 
 
## Conditional functions 

You can use intrinsic functions, such as Fn::If, Fn::Equals, and Fn::Not, to conditionally create stack resources. These conditions are evaluated based on input parameters that you declare when you create or update a stack. 







# Intrinsic Function


## Fn::Base64
Returns the Base64 representation of the input string. This function is typically used to pass encoded data to Amazon EC2 instances by way of the UserData property.

```
json

{ "Fn::Base64" : valueToEncode }

YML
Fn::Base64: valueToEncode

short hand

!Base64 valueToEncode

```
### invalid syntax for shorthand
If you use the short form and immediately include another function in the valueToEncode parameter, use the full function name for at least one of the functions. 
```
!Base64 !Sub string
!Base64 !Ref logical_ID

```
### valid syntaz for shorthand

Instead, use the full function name for at least one of the functions, as shown in the following examples:

```
!Base64
  "Fn::Sub": string

Fn::Base64:
  !Sub string
  
 ```

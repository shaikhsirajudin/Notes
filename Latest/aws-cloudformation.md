

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

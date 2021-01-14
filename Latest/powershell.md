## PowerShell script
It required you must specify the full path to script even if its in same directory.
which prevents command high-jacking. Extension not required but good to have it
Assuming script is in Lab folder
```
C:\Lab> .\MondayTasks.ps1

```

It has execution policy as follow
  a)  Restricted
  ```
  > Set-ExecutionPolicy Restricted
  ```
  b)  RemoteSinged.
     This can be run as administrator, only needs to be set once per machine
     Can also be set via Group Policy
     
     ```
     --- To set the execution policy of the machine
      > Set-ExecutionPolicy RemoteSigned
      --- To get the execution policy of the machine
      > Get-ExecutionPolicy
      ```
  
  c)  Allsinged : to execute all digitally signed files
  ```
  Set-ExecutionPolicy AllSigned -Force
  ```
  d)  Unrestricted
  
  e)  ByPass

E.g




File extension for powershell scripts

# .ps1
Default application for ps1 files is notepad,
# .psm1
# .ps1xml


# To Read the content of the file

```
> get-content Lab1.ps1

```
# Find the variables
Get-Variable cmdlet is used to list down all built in powershell variables.
```
>Get-Variable
```
# Declaring Variables

You can do so by using New-Variable cmdlet.
```
>New-Variable MyVar -Value 21
>$MyVar

```
or Alternatively, you can create a variable by using $ prefix and assigning some value as shown below

```
> $MyVar= "SomeValue"
> Get-Variable MyVar
```

 Below is the list of all parameters of New-Variable cmdlet:

-Name : Used to specify name of the variable.

-Value : Used to specify value at the time of creation.

-Description : Description for the variable being created. 

-Option : Used to set different options such ReadOnly, Private etc for variable.

-Visibility : Used to specify whether the variable is visible outside the session in which it was created.

-Force : Used to overwrite an existing variable.

-PassThru : Returns an object which currently is in use

-Scope : Specifies the scope of the variable.

-WhatIf : Tells what would happen when the cmdlet is executed.

-Confirm : Prompts a confirmation message before executing cmdlet.


## Reference url 
. https://jdhitsolutions.com/blog
https://powershelltutorial.net/home/Powershell-If-else
http://www.multinet.no/~sentinel/roar/Mastering%20PowerShell-Packt%202015.pdf

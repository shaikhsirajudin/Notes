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



## Reference url 
. https://jdhitsolutions.com/blog
https://powershelltutorial.net/home/Powershell-If-else

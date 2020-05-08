# To remove scrol from the page
```
app.scss


*::-webkit-scrollbar{
  display: none;
}
```
# Ionic doesnt allow to select the text but we can make it by

```
body{
  -webkit-user-select: text;
  user-select: text;
}
```

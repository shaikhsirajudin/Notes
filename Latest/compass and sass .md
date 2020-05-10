## using npm 
```
mkdir sass-demo
cd sass-demo
mkdir -p sass css

```
# Initialize the Project Directory: to create package.json
```

npm init -y

```
# Installing node-sass
```

npm install node-sass --save-dev

```
# Add this script inside the script section of the package.json file.
```
"compile-sass": "node-sass sass/main.scss css/style.css"

"compile-sass-watch": "node-sass sass/main.scss css/style.css --watch"

npm run compile-sass
```


## using only sass
```
gem install sass
```
compiling 

```
sass style.scss style.css
or in watch window
sass --watch style.scss:style.css

default file name

sass --watch style.scss 

```



## using compass
``
gem install compass
``
# creating projects from the command line:
```
compass create sass-test

with paramters
compass create --sass-dir "sass" --css-dir "css" --javascripts-dir "js" --images-dir "img"
```
run the project
```
compass watch
```
# Use the parent selector to create forks

```
Before

.button {
  height: 25px;
}
.touch .button {
  height: 44px;
}
==============================================
After

.button {
    height: 25px;
    .touch & {
      height: 44px;
    }
  }

```
. another way
```
Before

.button {
  height: 25px;
}
.button .touch {
  height: 44px;
}
=========================================
After

.button {
    height: 25px;
    .touch {
      height: 44px;
    }
  }

```

# Extend existing rules

```
Before

.first-selector, .second-selector {
  height: 44px;
}
.second-selector {
  width: auto;
}
==============================================
After

  .first-selector {
    height: 44px;
  }
  .second-selector {
    @extend .first-selector;
    width: auto;
  }

```

# Placeholder selectors

```
.warning-box, .success-box {
  padding: 2em;
  color: #123045;
  background-color: #123045;
}

.warning-box {
  border: 2px dotted #123233;
}

.success-box {
  border: 2px dotted #111111;
}

======================================

$color10: #123045 ;
$color11 : #123045 ;
$color1 : #123233;
$color4: #111111;

%box {
    padding: 2em;
    color: $color10;
    background-color: $color11;
  }
  .warning-box {
    @extend %box;
    border: 2px dotted $color1;
  }
  .success-box {
    @extend %box;
    border: 2px dotted $color4;
  }


```

# Variables

```
$red: #dd0000;
```

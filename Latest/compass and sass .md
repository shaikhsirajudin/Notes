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

## Notes: SASS Cheatsheet

Sass is CSS preprocessor. You can have sass or scss

### 安装
#### | Partials
- _variables.scss 
- _mixins.scss
- _helpers.scss
- _styles.scss
#### | Partial Imports
```SASS
@import 'partials/variables';
```
#### | Basic Command
```SASS
//check version
sass --version

// preprocess scss
sass --watch scss:css
sass --watch input.scss:output.css
```

---
### 变量 Variable
定义：
```SASS
$color-primary:#fff;
$color-btn-primary:#fff;
```
使用：
```SASS
background-color:$color-btn-primary;
```
---
### Map:将key-value pair存放在map里面
```SASS
$themes:(
  'primary':#fff,
  'secondary':#eee,
  'soc':#fefefe,
);
```
使用：
```SASS
map-get($themes,'primary'); 
```

---
### Nesting 
定义：将html子元素放在父元素的css里面去
#### Selectors in Nesting
使用“&”符号
```SASS
//scss
.notecard{
  &:hover{
  }
}
//css
.notecard:hover{
}
```



---
### Mixin
定义：
```SASS
@mixin theme ($variable：default){
}
```
调用：就加@include
```SASS
@include theme(hidden)
```
---
### String Interpolation
定义：使用#{}
```SASS
@mixin photo-content($file){
  content:url(#{$file}.jpg);
}
```
